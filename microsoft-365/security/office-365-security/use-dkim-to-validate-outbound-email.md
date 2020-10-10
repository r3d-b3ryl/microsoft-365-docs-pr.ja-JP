---
title: カスタム ドメインで DKIM をメールに使用する方法
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 で DomainKeys Identified Mail (DKIM) を使用して、カスタム ドメインから送信されたメッセージが送信先のメール システムから信頼されるようにする方法を説明します。
ms.openlocfilehash: a83b2363a6cd6e53283804881289dd22e81c793c
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412492"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="81ba6-103">DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する</span><span class="sxs-lookup"><span data-stu-id="81ba6-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="81ba6-104">**概要:** この記事では、Microsoft 365 で DomainKeys Identified Mail (DKIM) を使用して、カスタム ドメインから送信されたメッセージを送信先のメール システムが信頼するようにする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="81ba6-105">ドメインから送信されたように見えるメッセージをなりすまし者が送信できないようにするためには、SPF と DMARC に加え、DKIM を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="81ba6-106">DKIM を使用すると、送信電子メールのメッセージ ヘッダー内にデジタル署名を追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="81ba6-107">複雑そうですが、実際には複雑ではありません。</span><span class="sxs-lookup"><span data-stu-id="81ba6-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="81ba6-108">DKIM の構成時に、関連付けるドメインを承認するか、または暗号化認証を使用して電子メール メッセージにその名前を署名します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="81ba6-109">ドメインから電子メールを受信する電子メール システムでは、このデジタル署名を使用して、受け取った受信メールが正当であるかどうかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="81ba6-110">基本的には、秘密キーを使用してドメインの送信メールのヘッダーを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="81ba6-111">受信側サーバーが署名のデコードに使用できるドメインの DNS レコードに、公開キーを発行します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="81ba6-112">公開キーを使用することで、そのメッセージが送信者本人からのものであり、ドメインを*偽装*している他人からのものでないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="81ba6-113">Microsoft 365 では、初期ドメインの 'onmicrosoft.com' に対応する DKIM が自動的にセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-113">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="81ba6-114">つまり、初期ドメイン名に対応する DKIM のセットアップに関して、ユーザーは何もする必要がないということです (例: litware.onmicrosoft.com)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="81ba6-115">ドメインの詳細については、「[ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="81ba6-116">カスタム ドメインの DKIM に関しても、何も操作しなくて構いません。</span><span class="sxs-lookup"><span data-stu-id="81ba6-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="81ba6-117">カスタム ドメインに対応する DKIM をセットアップしていないと、Microsoft 365 が秘密キーと公開キーのペアを作成して、DKIM 署名を有効にし、カスタム ドメインに対応する Microsoft 365 の既定ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-117">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="81ba6-118">ほとんどのユーザーの場合はこれで十分ですが、次の状況ではカスタム ドメインの DKIM を手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-118">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="81ba6-119">Microsoft 365 に複数のカスタム ドメインがある場合</span><span class="sxs-lookup"><span data-stu-id="81ba6-119">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="81ba6-120">DMARC も設定する場合 (推奨)</span><span class="sxs-lookup"><span data-stu-id="81ba6-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="81ba6-121">秘密キーを制御する場合</span><span class="sxs-lookup"><span data-stu-id="81ba6-121">You want control over your private key</span></span>

- <span data-ttu-id="81ba6-122">CNAME レコードをカスタマイズする場合</span><span class="sxs-lookup"><span data-stu-id="81ba6-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="81ba6-123">たとえば、サード パーティ製の大容量メーラーを使用する場合、サードパーティのドメインから発信される電子メールに DKIM キーを設定することがあります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="81ba6-124">この記事の内容:</span><span class="sxs-lookup"><span data-stu-id="81ba6-124">In this article:</span></span>

- [<span data-ttu-id="81ba6-125">悪意のあるスプーフィング防止の点で DKIM のしくみが SPF 単独よりも優れているといえる理由</span><span class="sxs-lookup"><span data-stu-id="81ba6-125">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="81ba6-126">手動で 1024 ビット キーを 2048 ビット DKIM 暗号化キーにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="81ba6-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="81ba6-127">DKIM を手動でセットアップする手順</span><span class="sxs-lookup"><span data-stu-id="81ba6-127">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="81ba6-128">DKIM の複数のドメインを構成するには</span><span class="sxs-lookup"><span data-stu-id="81ba6-128">To configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="81ba6-129">カスタム ドメインの DKIM 署名ポリシーを無効にする</span><span class="sxs-lookup"><span data-stu-id="81ba6-129">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="81ba6-130">DKIM と Microsoft 365 の既定の動作</span><span class="sxs-lookup"><span data-stu-id="81ba6-130">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="81ba6-131">サードパーティのサービスがカスタム ドメインに代わって電子メールを送信つまり偽装できるように DKIM を設定する</span><span class="sxs-lookup"><span data-stu-id="81ba6-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="81ba6-132">次の手順: Microsoft 365 に SPF をセットアップした後</span><span class="sxs-lookup"><span data-stu-id="81ba6-132">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="81ba6-133">悪意のあるスプーフィング防止の点で DKIM のしくみが SPF 単独よりも優れているといえる理由</span><span class="sxs-lookup"><span data-stu-id="81ba6-133">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="81ba6-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="81ba6-p105">SPF ではメッセージ エンベロープに情報を追加しますが、DKIM は実際にメッセージ ヘッダー内の署名を暗号化します。メッセージを転送すると、そのメッセージのエンベロープの一部が転送サーバーによって取り除かれる可能性があります。デジタル署名は、電子メール ヘッダーの一部であるため、電子メール メッセージと共に残ります。したがって、DKIM はメッセージが転送された場合にも機能します。次の例で説明します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![SPF チェックが失敗したときに DKIM 認証を通過した転送されたメッセージを示す図](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="81ba6-p106">この例で、ドメインに対して SPF TXT レコードしか発行しなかったとしたら、受信者のメール サーバーによってメールがスパムとしてマークされ、誤検知の結果になる可能性があります。このシナリオでは DKIM を追加することによって、誤検知のスパム報告が減少しています。DKIM は、IP アドレスだけではなく、公開キー暗号化を使って認証を行うので、SPF よりもはるかに強力な認証形態といえます。展開では DMARC だけでなく、SPF と DKIM の両方を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="81ba6-p107">基本事項:DKIM では秘密キーを使用して、暗号化された署名をメッセージ ヘッダーに挿入します。署名ドメイン、つまり送信ドメインは、**d=** フィールドの値としてヘッダーに挿入されます。確認ドメイン、つまり受信者のドメインは、**d=** フィールドを使用して、DNS から公開キーを検索し、メッセージを認証します。メッセージが確認されれば、DKIM チェックは合格です。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="81ba6-147">手動で 1024 ビット キーを 2048 ビット DKIM 暗号化キーにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="81ba6-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="81ba6-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="81ba6-149">DKIM キーでは 1024 ビットと 2048 ビットの両方がサポートされています。次の手順では、1024 ビット キーを 2048 ビットにアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="81ba6-150">次の手順は、2 つのユース ケースに向けたものです。目的の構成に最適なものを選択してください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="81ba6-151">**DKIM の構成が済んでいる**場合は、次のようにしてビットを転換します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>

   1. <span data-ttu-id="81ba6-152">[PowerShell で Office 365 のワークロードに接続します](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="81ba6-153">(このコマンドレットは、Exchange Online のものです)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-153">(The cmdlet comes from Exchange Online.)</span></span>
   1. <span data-ttu-id="81ba6-154">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-154">Run the following command:</span></span>

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. <span data-ttu-id="81ba6-155">**DKIM の新規実装**の場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="81ba6-155">Or for a **new implementation of DKIM**:</span></span>

   1. <span data-ttu-id="81ba6-156">[PowerShell で Office 365 のワークロードに接続します](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-156">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="81ba6-157">(これは、Exchange Online コマンドレットです)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-157">(This is an Exchange Online cmdlet.)</span></span>
   1. <span data-ttu-id="81ba6-158">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-158">Run the following command:</span></span>

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

<span data-ttu-id="81ba6-159">Microsoft 365 への接続状態を維持して、構成を*検証*します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-159">Stay connected to Microsoft 365 to *verify* the configuration.</span></span>

1. <span data-ttu-id="81ba6-160">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-160">Run the following command:</span></span>

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> <span data-ttu-id="81ba6-161">この新しい 2048 ビット キーは RotateOnDate の時点で有効になります。それまでの間は、1024 ビット キーの電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-161">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="81ba6-162">4 日後に、2048 ビット キーで再度テストしてください (つまり、2 番目のセレクターへの転換が有効になってからテストします)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-162">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="81ba6-163">2 番目のセレクターに転換する場合は、a) Microsoft 365 にセレクターの転換を任せて、6 か月以内に 2048 ビットへのアップグレードを実行するか、b) 4 日後に 2048 ビットが使用されていることを確認して、前述の該当するコマンドレットを使用して 2 番目のセレクター キーを手動で転換します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-163">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="81ba6-164">DKIM を手動でセットアップする手順</span><span class="sxs-lookup"><span data-stu-id="81ba6-164">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="81ba6-165"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-165"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="81ba6-166">DKIM を構成するには、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-166">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="81ba6-167">DNS でカスタム ドメインに対して 2 つの CNAME レコードを発行する</span><span class="sxs-lookup"><span data-stu-id="81ba6-167">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="81ba6-168">カスタム ドメインに対して DKIM 署名を有効にする</span><span class="sxs-lookup"><span data-stu-id="81ba6-168">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="81ba6-169">DNS でカスタム ドメインに対して 2 つの CNAME レコードを発行する</span><span class="sxs-lookup"><span data-stu-id="81ba6-169">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="81ba6-170"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-170"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="81ba6-171">DNS の DKIM 署名を追加する各ドメインに対して、2 つの CNAME レコードを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-171">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

<span data-ttu-id="81ba6-172">以下のコマンドを実行してセレクター レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-172">Run the following commands to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="81ba6-173">Microsoft 365 の初期ドメインに加えてプロビジョニングされたカスタム ドメインがある場合には、追加の各ドメインに対して 2 つの CNAME レコードを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-173">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="81ba6-174">したがって、2 つのドメインがある場合は、2 つの追加 CNAME レコードなどを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-174">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="81ba6-175">CNAME レコードには次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-175">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81ba6-176">GCC High のお客様の場合、_domainGuid_ の計算方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-176">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="81ba6-177">_domainGuid_ を計算するために _initialDomain_ の MX レコードを参照する代わりに、カスタム ドメインから直接計算します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-177">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="81ba6-178">たとえば、カスタム ドメインが "contoso.com" の場合、domainGuid は "contoso-com" となり、ピリオドはすべてダッシュに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-178">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="81ba6-179">したがって、initialDomain が指し示す MX レコードに関係なく、CNAME レコードで使用する domainGuid は、常に上記の方法を使用して計算します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-179">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="81ba6-180">ここで、</span><span class="sxs-lookup"><span data-stu-id="81ba6-180">Where:</span></span>

- <span data-ttu-id="81ba6-181">Microsoft 365 では、セレクターは常に "selector1" または "selector2" になります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-181">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="81ba6-182">_domainGUID_ は、mail.protection.outlook.com の前に表示される、カスタム ドメインのカスタム MX レコードの _domainGUID_ と同じです。</span><span class="sxs-lookup"><span data-stu-id="81ba6-182">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="81ba6-183">たとえば、次に示すドメイン contoso.com の MX レコードでは、_domainGUID_ は contoso-com です。</span><span class="sxs-lookup"><span data-stu-id="81ba6-183">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="81ba6-184">contoso.com.</span><span class="sxs-lookup"><span data-stu-id="81ba6-184">contoso.com.</span></span>  <span data-ttu-id="81ba6-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="81ba6-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="81ba6-186">_initialDomain_ は、Microsoft 365 へのサインアップ時に使用したドメインです。</span><span class="sxs-lookup"><span data-stu-id="81ba6-186">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="81ba6-187">初期ドメインの末尾は常に onmicrosoft.com です。</span><span class="sxs-lookup"><span data-stu-id="81ba6-187">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="81ba6-188">初期ドメインを決定する方法の詳細については、「 [ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-188">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="81ba6-189">たとえば、初期ドメイン (cohovineyardandwinery.onmicrosoft.com) と 2 つのカスタム ドメイン (cohovineyard.com と cohowinery.com) がある場合は、追加のそれぞれのドメインに対して 2 つの CNAME レコードをセットアップして、合計で 4 つの CNAME レコードをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-189">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="81ba6-190">2 番目のレコードを作成することは重要ですが、作成時に使用できるのはセレクターのうち 1 つのみである場合があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-190">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="81ba6-191">本質的に、2 番目のセレクターはまだ作成されていないアドレスを指している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-191">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="81ba6-192">それでも、キーの交換がシームレスに行われるようになるため、2 番目の CNAME レコードを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="81ba6-192">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>

> [!CAUTION]
> <span data-ttu-id="81ba6-193">キーを作成する方法のいくつかのデザイン変更実装するため、自動キーのローテーションは一時的に無効になっています。</span><span class="sxs-lookup"><span data-stu-id="81ba6-193">Automatic key rotation has been temporarily disabled as we implement some design changes in how we create keys.</span></span> <span data-ttu-id="81ba6-194">複数のキーを持つことで、定期的にローテーションさせることができます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-194">It's a good practice to have multiple keys so that you can rotate them periodically.</span></span> <span data-ttu-id="81ba6-195">解読するのは困難ですが、なりすましなどから保護するための実用的な対策戦略です。</span><span class="sxs-lookup"><span data-stu-id="81ba6-195">Although it's hard to crack, it's still a practical mitigation strategy to protect against things like impersonation.</span></span> <span data-ttu-id="81ba6-196">「[Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)」ドキュメントを参考にして、組織でこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-196">You can follow the [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig) document to help do this for your organization.</span></span> <span data-ttu-id="81ba6-197">自動ローテーションは 2020 年 8月より再度有効になる予定です。</span><span class="sxs-lookup"><span data-stu-id="81ba6-197">We expect that automatic rotation will be enabled again by August 2020.</span></span>

### <a name="enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="81ba6-198">カスタム ドメインに対して DKIM 署名を有効にする</span><span class="sxs-lookup"><span data-stu-id="81ba6-198">Enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="81ba6-199"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-199"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="81ba6-200">DNS に CNAME レコードを発行したら、Microsoft 365 で DKIM 署名を有効にする準備が整ったことになります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-200">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="81ba6-201">これは、Microsoft 365 管理センターか、PowerShell を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-201">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="81ba6-202">管理センター経由でカスタム ドメインの DKIM 署名を有効にするには</span><span class="sxs-lookup"><span data-stu-id="81ba6-202">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="81ba6-203">職場または学校のアカウントを使用して、[Microsoft 365 にサインイン](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-203">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="81ba6-204">左上にあるアプリ起動ツールのアイコンを選択して、**[管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81ba6-204">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="81ba6-205">左下のナビゲーションで、**[管理者]** を展開し、**[Exchange]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-205">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="81ba6-206">**[保護]** \> **[dkim]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-206">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="81ba6-p120">DKIM を有効にするドメインを選択してから、**[このドメインのメッセージに DKIM 署名で署名する]** で **[有効]** を選択します。各カスタム ドメインにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p120">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="81ba6-209">PowerShell を使用してカスタム ドメインの DKIM 署名を有効にするには</span><span class="sxs-lookup"><span data-stu-id="81ba6-209">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="81ba6-210">[Exchange Online PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-210">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="81ba6-211">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-211">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="81ba6-212">ここで、 _domain_ は DKIM 署名を有効にするカスタム ドメインの名前です。</span><span class="sxs-lookup"><span data-stu-id="81ba6-212">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="81ba6-213">たとえば、ドメイン名 contoso.com の場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-213">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="81ba6-214">DKIM 署名が Microsoft 365 に対して適切に構成されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="81ba6-214">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="81ba6-p121">数分待ってから、これらの手順に従って、DKIM が適切に構成されていることを確認してください。待っている間に、ドメインに関する DKIM 情報がネットワーク全体に広まります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p121">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="81ba6-217">Microsoft 365 の DKIM が有効になっているドメイン内のアカウントから、Outlook.com や Hotmail.com などの別の電子メール アカウントにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-217">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="81ba6-p122">テスト目的には .aol.com アカウントは使用しないでください。AOL は SPF チェックに合格すると、DKIM チェックをスキップする場合があります。この場合、テストは成り立ちません。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p122">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="81ba6-p123">メッセージを開き、ヘッダーを確認します。メッセージのヘッダーを表示する方法は、メッセージング クライアントによって異なります。Outlook でメッセージ ヘッダーを表示する方法については、「[電子メール メッセージ ヘッダーを表示する](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p123">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="81ba6-p124">DKIM 署名されたメッセージには、CNAME エントリの発行時に定義したホスト名とドメインが含まれます。メッセージは、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p124">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="81ba6-p125">認証結果のヘッダーを確認します。各受信側のサービスでは受信メールのスタンプに若干異なる形式が使用されますが、結果には **DKIM=pass** や **DKIM=OK** などが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p125">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="81ba6-228">DKIM の複数のドメインを構成するには</span><span class="sxs-lookup"><span data-stu-id="81ba6-228">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="81ba6-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-229"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="81ba6-230">後で別のカスタム ドメインを追加して、その新しいドメインに対して DKIM を有効にする場合は、各ドメインに対してこの記事の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-230">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="81ba6-231">具体的には、「[DKIM を手動でセットアップする方法](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)」のすべての手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-231">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="81ba6-232">カスタム ドメインの DKIM 署名ポリシーを無効にする</span><span class="sxs-lookup"><span data-stu-id="81ba6-232">Disabling the DKIM signing policy for a custom domain</span></span> 
<span data-ttu-id="81ba6-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-233"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="81ba6-234">署名ポリシーを無効にしても、DKIM は完全には無効になりません。</span><span class="sxs-lookup"><span data-stu-id="81ba6-234">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="81ba6-235">一定の期間が経過すると、Microsoft 365 はドメインの既定のポリシーを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-235">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="81ba6-236">詳細については「[DKIM と Microsoft 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-236">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="81ba6-237">Windows PowerShell を使用して DKIM 署名ポリシーを無効にするには</span><span class="sxs-lookup"><span data-stu-id="81ba6-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="81ba6-238">[Exchange Online PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-238">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="81ba6-239">DKIM 署名を無効にする各ドメインに対して次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="81ba6-240">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-240">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="81ba6-241">または</span><span class="sxs-lookup"><span data-stu-id="81ba6-241">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="81ba6-242">ここで、 _number_ はポリシーのインデックスです。</span><span class="sxs-lookup"><span data-stu-id="81ba6-242">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="81ba6-243">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-243">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="81ba6-244">DKIM と Microsoft 365 の既定の動作</span><span class="sxs-lookup"><span data-stu-id="81ba6-244">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="81ba6-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-245"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="81ba6-246">DKIM を有効にしない場合、Microsoft 365 は既定のドメインに対して 1024 ビットの DKIM 公開キーと、それに関連する秘密キー (これはデータセンターに内部的に保存されます) を作成します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-246">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="81ba6-247">既定では、Microsoft 365 は、所定のポリシーを持たないドメインに対して既定の署名構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-247">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="81ba6-248">これは、ユーザーが DKIM をセットアップしなければ、Microsoft 365 が、その既定のポリシーと、自らが作成するキーを使用して、そのドメインに対して DKIM を有効にすることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="81ba6-248">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="81ba6-249">また、DKIM 署名を有効にしてから無効にした場合にも、一定の期間が過ぎると、Microsoft 365 が自動的にドメインに対して既定のポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-249">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="81ba6-250">次の例では、fabrikam.com の DKIM が、ドメインの管理者ではなく、Microsoft 365 によって有効にされていることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="81ba6-250">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="81ba6-251">これは、必須の CNAME が DNS に存在しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-251">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="81ba6-252">このドメインからのメールの DKIM 署名は、次のようなものになります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-252">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="81ba6-253">この例のホスト名とドメインには、fabrikam.com の DKIM 署名がドメイン管理者によって有効にされた場合に CNAME が指し示す値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81ba6-253">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="81ba6-254">最終的には、Microsoft 365 から送信されるすべてのメッセージは DKIM 署名されたメッセージになります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-254">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="81ba6-255">自分で DKIM を有効にしている場合、ドメインは From: アドレス内のドメインと同じになります (この場合は fabrikam.com)。</span><span class="sxs-lookup"><span data-stu-id="81ba6-255">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="81ba6-256">自分で DKIM を有効にしない場合は、ドメインは同じにならず、代わりに組織の初期ドメインが使用されます。</span><span class="sxs-lookup"><span data-stu-id="81ba6-256">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="81ba6-257">初期ドメインを決定する方法の詳細については、「 [ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-257">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="81ba6-258">サードパーティのサービスがカスタム ドメインに代わって電子メールを送信つまり偽装できるように DKIM を設定する</span><span class="sxs-lookup"><span data-stu-id="81ba6-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="81ba6-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-259"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="81ba6-p132">一部の一括電子メール サービス プロバイダー、または Software-as-a-Service プロバイダーでは、サービスから送信される電子メールに DKIM キーを設定できます。この場合、必要な DNS レコードを設定するために自分とサードパーティの間で調整が必要です。まったく同じ方法を用いる組織は 2 つとありません。それどころか、プロセスは完全に組織に依存します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p132">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="81ba6-264">contoso.com および bulkemailprovider.com 用に適切に構成された DKIM を示すメッセージの例は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-264">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="81ba6-265">この例では、この結果を達成するために、次を実行しました。</span><span class="sxs-lookup"><span data-stu-id="81ba6-265">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="81ba6-266">一括電子メール プロバイダーは、Contosoc に DKIM の公開キーを付与しました。</span><span class="sxs-lookup"><span data-stu-id="81ba6-266">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="81ba6-267">Contoso は、その DNS レコードに DKIM キーを発行しました。</span><span class="sxs-lookup"><span data-stu-id="81ba6-267">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="81ba6-p133">電子メールを送信する場合、一括電子メール プロバイダーは対応する秘密キーを使用してキーに署名しました。これにより、一括電子メール プロバイダーはメッセージ ヘッダーに DKIM 署名を添付します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-p133">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="81ba6-270">受信側の電子メールシステムでは、メッセージの From: (5322.from) アドレスのドメインに対して DKIM-Signature d=\<domain\> 値を認証することによって DKIM チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-270">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="81ba6-271">この例では、次の値が一致します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-271">In this example, the values match:</span></span>

   > <span data-ttu-id="81ba6-272">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="81ba6-272">sender@**contoso.com**</span></span>

   > <span data-ttu-id="81ba6-273">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="81ba6-273">d=**contoso.com**</span></span>
   
## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="81ba6-274">メールを送信しないドメインを特定する</span><span class="sxs-lookup"><span data-stu-id="81ba6-274">Identify domains that do not send email</span></span>

<span data-ttu-id="81ba6-275">組織は、ドメインのDKIM レコードで`v=DKIM1; p=`を指定して、そのドメインがメールを送信しないことを明示的に述べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-275">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="81ba6-276">これにより、そのドメインには有効な公開鍵が存在しないことをメール受信サーバーに知らせ、そのドメインからのメールを拒否するように、要求します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-276">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="81ba6-277">ワイルドカード DKIM を使用して、ドメインとサブドメインごとにこの操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-277">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="81ba6-278">たとえば、DKIM レコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-278">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="81ba6-279">次の手順: Microsoft 365 に SPF をセットアップした後</span><span class="sxs-lookup"><span data-stu-id="81ba6-279">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="81ba6-280"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="81ba6-280"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="81ba6-281">DKIM はスプーフィングを防止するように設計されていますが、SPF と DMARC を併用すると DKIM はより有効に機能します。</span><span class="sxs-lookup"><span data-stu-id="81ba6-281">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="81ba6-282">DKIM をセットアップした後、まだ SPF を構成していなければ、SPF を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ba6-282">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="81ba6-283">SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-283">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="81ba6-284">Microsoft 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-284">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="81ba6-285">次は、「[DMARC を使用してメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ba6-285">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="81ba6-286">[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)には、Microsoft 365 が KIM チェックに使用する構文とヘッダー フィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="81ba6-286">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>
