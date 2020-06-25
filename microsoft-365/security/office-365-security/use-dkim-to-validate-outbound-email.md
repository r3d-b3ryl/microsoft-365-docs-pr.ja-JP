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
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 で DomainKeys Identified Mail (DKIM) を使用して、カスタム ドメインから送信されたメッセージが送信先のメール システムから信頼されるようにする方法を説明します。
ms.openlocfilehash: 4ec5f7c8779e9d6b6709c8fc3311ec9c0e99b680
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754846"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する

 **概要:** この記事では、Microsoft 365 で DomainKeys Identified Mail (DKIM) を使用して、カスタム ドメインから送信されたメッセージを送信先のメール システムが信頼するようにする方法を説明します。

ドメインから送信されたように見えるメッセージをなりすまし者が送信できないようにするためには、SPF と DMARC に加え、DKIM を使用する必要があります。 DKIM を使用すると、送信電子メールのメッセージ ヘッダー内にデジタル署名を追加できるようになります。 複雑そうですが、実際には複雑ではありません。 DKIM の構成時に、関連付けるドメインを承認するか、または暗号化認証を使用して電子メール メッセージにその名前を署名します。 ドメインから電子メールを受信する電子メール システムでは、このデジタル署名を使用して、受け取った受信メールが正当であるかどうかを判断することができます。

基本的には、秘密キーを使用してドメインの送信メールのヘッダーを暗号化します。 受信側サーバーが署名のデコードに使用できるドメインの DNS レコードに、公開キーを発行します。 公開キーを使用することで、そのメッセージが送信者本人からのものであり、ドメインを*偽装*している他人からのものでないことを確認します。

Microsoft 365 では、初期ドメインの 'onmicrosoft.com' に対応する DKIM が自動的にセットアップされます。 つまり、初期ドメイン名に対応する DKIM のセットアップに関して、ユーザーは何もする必要がないということです (例: litware.onmicrosoft.com)。 ドメインの詳細については、「[ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。

カスタム ドメインの DKIM に関しても、何も操作しなくて構いません。 カスタム ドメインに対応する DKIM をセットアップしていないと、Microsoft 365 が秘密キーと公開キーのペアを作成して、DKIM 署名を有効にし、カスタム ドメインに対応する Microsoft 365 の既定ポリシーを構成します。 ほとんどのユーザーの場合はこれで十分ですが、次の状況ではカスタム ドメインの DKIM を手動で構成する必要があります。

- Microsoft 365 に複数のカスタム ドメインがある場合

- DMARC も設定する場合 (推奨)

- 秘密キーを制御する場合

- CNAME レコードをカスタマイズする場合

- たとえば、サード パーティ製の大容量メーラーを使用する場合、サードパーティのドメインから発信される電子メールに DKIM キーを設定することがあります。

この記事の内容:

- [悪意のあるスプーフィング防止の点で DKIM のしくみが SPF 単独よりも優れているといえる理由](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [手動で 1024 ビット キーを 2048 ビット DKIM 暗号化キーにアップグレードする](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [DKIM を手動でセットアップする手順](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [DKIM の複数のドメインを構成するには](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [カスタム ドメインの DKIM 署名ポリシーを無効にする](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [DKIM と Microsoft 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [サードパーティのサービスがカスタム ドメインに代わって電子メールを送信つまり偽装できるように DKIM を設定する](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [次の手順: Microsoft 365 に SPF をセットアップした後](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>悪意のあるスプーフィング防止の点で DKIM のしくみが SPF 単独よりも優れているといえる理由
<a name="HowDKIMWorks"> </a>

SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.

![SPF チェックが失敗したときに DKIM 認証を通過した転送されたメッセージを示す図](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.

The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>手動で 1024 ビット キーを 2048 ビット DKIM 暗号化キーにアップグレードする
<a name="1024to2048DKIM"> </a>

DKIM キーでは 1024 ビットと 2048 ビットの両方がサポートされています。次の手順では、1024 ビット キーを 2048 ビットにアップグレードする方法について説明します。 次の手順は、2 つのユース ケースに向けたものです。目的の構成に最適なものを選択してください。

1. **DKIM の構成が済んでいる**場合は、次のようにしてビットを転換します。

   1. [PowerShell で Office 365 のワークロードに接続します](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)。 (このコマンドレットは、Exchange Online のものです)。
   1. 次のコマンドを実行します。

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. **DKIM の新規実装**の場合は、次のようにします。

   1. [PowerShell で Office 365 のワークロードに接続します](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)。 (これは、Exchange Online コマンドレットです)。
   1. 次のコマンドを実行します。

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

Microsoft 365 への接続状態を維持して、構成を*検証*します。

1. 次のコマンドを実行します。

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> この新しい 2048 ビット キーは RotateOnDate の時点で有効になります。それまでの間は、1024 ビット キーの電子メールが送信されます。 4 日後に、2048 ビット キーで再度テストしてください (つまり、2 番目のセレクターへの転換が有効になってからテストします)。

2 番目のセレクターに転換する場合は、a) Microsoft 365 にセレクターの転換を任せて、6 か月以内に 2048 ビットへのアップグレードを実行するか、b) 4 日後に 2048 ビットが使用されていることを確認して、前述の該当するコマンドレットを使用して 2 番目のセレクター キーを手動で転換します。

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a>DKIM を手動でセットアップする手順
<a name="SetUpDKIMO365"> </a>

DKIM を構成するには、次の手順を完了します。

- [DNS でカスタム ドメインに対して 2 つの CNAME レコードを発行する](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [カスタム ドメインに対して DKIM 署名を有効にする](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>DNS でカスタム ドメインに対して 2 つの CNAME レコードを発行する
<a name="Publish2CNAME"> </a>

DNS の DKIM 署名を追加する各ドメインに対して、2 つの CNAME レコードを発行する必要があります。

以下のコマンドを実行してセレクター レコードを作成します。

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

Microsoft 365 の初期ドメインに加えてプロビジョニングされたカスタム ドメインがある場合には、追加の各ドメインに対して 2 つの CNAME レコードを発行する必要があります。 したがって、2 つのドメインがある場合は、2 つの追加 CNAME レコードなどを発行する必要があります。

CNAME レコードには次の形式を使用します。

> [!IMPORTANT]
> GCC High のお客様の場合、_domainGuid_ の計算方法が異なります。 _domainGuid_ を計算するために _initialDomain_ の MX レコードを参照する代わりに、カスタム ドメインから直接計算します。 たとえば、カスタム ドメインが "contoso.com" の場合、domainGuid は "contoso-com" となり、ピリオドはすべてダッシュに置き換えられます。 したがって、initialDomain が指し示す MX レコードに関係なく、CNAME レコードで使用する domainGuid は、常に上記の方法を使用して計算します。

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

ここで、

- Microsoft 365 では、セレクターは常に "selector1" または "selector2" になります。

- _domainGUID_ は、mail.protection.outlook.com の前に表示される、カスタム ドメインのカスタム MX レコードの _domainGUID_ と同じです。 たとえば、次に示すドメイン contoso.com の MX レコードでは、_domainGUID_ は contoso-com です。

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ は、Microsoft 365 へのサインアップ時に使用したドメインです。 初期ドメインの末尾は常に onmicrosoft.com です。 初期ドメインを決定する方法の詳細については、「 [ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。

たとえば、初期ドメイン (cohovineyardandwinery.onmicrosoft.com) と 2 つのカスタム ドメイン (cohovineyard.com と cohowinery.com) がある場合は、追加のそれぞれのドメインに対して 2 つの CNAME レコードをセットアップして、合計で 4 つの CNAME レコードをセットアップする必要があります。

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
> 2 番目のレコードを作成することは重要ですが、作成時に使用できるのはセレクターのうち 1 つのみである場合があります。 本質的に、2 番目のセレクターはまだ作成されていないアドレスを指している可能性があります。 それでも、キーの交換がシームレスに行われるようになるため、2 番目の CNAME レコードを作成することをお勧めします。

> [!CAUTION]
> キーを作成する方法のいくつかのデザイン変更実装するため、自動キーのローテーションは一時的に無効になっています。 複数のキーを持つことで、定期的にローテーションさせることができます。 解読するのは困難ですが、なりすましなどから保護するための実用的な対策戦略です。 「[Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)」ドキュメントを参考にして、組織でこれを行うことができます。 自動ローテーションは 2020 年 8月より再度有効になる予定です。

### <a name="enable-dkim-signing-for-your-custom-domain"></a>カスタム ドメインに対して DKIM 署名を有効にする
<a name="EnableDKIMinO365"> </a>

DNS に CNAME レコードを発行したら、Microsoft 365 で DKIM 署名を有効にする準備が整ったことになります。 これは、Microsoft 365 管理センターか、PowerShell を使用して行うことができます。

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>管理センター経由でカスタム ドメインの DKIM 署名を有効にするには

1. 職場または学校のアカウントを使用して、[Microsoft 365 にサインイン](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)します。

2. 左上にあるアプリ起動ツールのアイコンを選択して、**[管理]** をクリックします。

3. 左下のナビゲーションで、**[管理者]** を展開し、**[Exchange]** を選択します。

4. **[保護]** \> **[dkim]** の順に移動します。

5. Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>PowerShell を使用してカスタム ドメインの DKIM 署名を有効にするには

1. [Exchange Online PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. 次のコマンドを実行します。

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   ここで、 _domain_ は DKIM 署名を有効にするカスタム ドメインの名前です。

   たとえば、ドメイン名 contoso.com の場合は次のようになります。

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>DKIM 署名が Microsoft 365 に対して適切に構成されていることを確認するには

Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.

- Microsoft 365 の DKIM が有効になっているドメイン内のアカウントから、Outlook.com や Hotmail.com などの別の電子メール アカウントにメッセージを送信します。

- Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.

- Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

  The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>DKIM の複数のドメインを構成するには
<a name="DKIMMultiDomain"> </a>

後で別のカスタム ドメインを追加して、その新しいドメインに対して DKIM を有効にする場合は、各ドメインに対してこの記事の手順を完了する必要があります。 具体的には、「[DKIM を手動でセットアップする方法](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)」のすべての手順を完了します。

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>カスタム ドメインの DKIM 署名ポリシーを無効にする 
<a name="DisableDKIMSigningPolicy"> </a>

署名ポリシーを無効にしても、DKIM は完全には無効になりません。 一定の期間が経過すると、Microsoft 365 はドメインの既定のポリシーを自動的に適用します。 詳細については「[DKIM と Microsoft 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)」をご覧ください。

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Windows PowerShell を使用して DKIM 署名ポリシーを無効にするには

1. [Exchange Online PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. DKIM 署名を無効にする各ドメインに対して次のいずれかのコマンドを実行します。

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   次に例を示します。

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   または

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   ここで、 _number_ はポリシーのインデックスです。 以下に例を示します。

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>DKIM と Microsoft 365 の既定の動作
<a name="DefaultDKIMbehavior"> </a>

DKIM を有効にしない場合、Microsoft 365 は既定のドメインに対して 1024 ビットの DKIM 公開キーと、それに関連する秘密キー (これはデータセンターに内部的に保存されます) を作成します。 既定では、Microsoft 365 は、所定のポリシーを持たないドメインに対して既定の署名構成を使用します。 これは、ユーザーが DKIM をセットアップしなければ、Microsoft 365 が、その既定のポリシーと、自らが作成するキーを使用して、そのドメインに対して DKIM を有効にすることを意味しています。

また、DKIM 署名を有効にしてから無効にした場合にも、一定の期間が過ぎると、Microsoft 365 が自動的にドメインに対して既定のポリシーを適用します。

次の例では、fabrikam.com の DKIM が、ドメインの管理者ではなく、Microsoft 365 によって有効にされていることを想定しています。 これは、必須の CNAME が DNS に存在しないことを意味します。 このドメインからのメールの DKIM 署名は、次のようなものになります。

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

この例のホスト名とドメインには、fabrikam.com の DKIM 署名がドメイン管理者によって有効にされた場合に CNAME が指し示す値が含まれています。 最終的には、Microsoft 365 から送信されるすべてのメッセージは DKIM 署名されたメッセージになります。 自分で DKIM を有効にしている場合、ドメインは From: アドレス内のドメインと同じになります (この場合は fabrikam.com)。 自分で DKIM を有効にしない場合は、ドメインは同じにならず、代わりに組織の初期ドメインが使用されます。 初期ドメインを決定する方法の詳細については、「 [ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>サードパーティのサービスがカスタム ドメインに代わって電子メールを送信つまり偽装できるように DKIM を設定する
<a name="SetUp3rdPartyspoof"> </a>

Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.

contoso.com および bulkemailprovider.com 用に適切に構成された DKIM を示すメッセージの例は、次のようになります。

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

この例では、この結果を達成するために、次を実行しました。

1. 一括電子メール プロバイダーは、Contosoc に DKIM の公開キーを付与しました。

2. Contoso は、その DNS レコードに DKIM キーを発行しました。

3. When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.

4. 受信側の電子メールシステムでは、メッセージの From: (5322.from) アドレスのドメインに対して DKIM-Signature d=\<domain\> 値を認証することによって DKIM チェックを実行します。 この例では、次の値が一致します。

   > sender@**contoso.com**

   > d=**contoso.com**

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>次の手順: Microsoft 365 に SPF をセットアップした後
<a name="DKIMNextSteps"> </a>

DKIM はスプーフィングを防止するように設計されていますが、SPF と DMARC を併用すると DKIM はより有効に機能します。 DKIM をセットアップした後、まだ SPF を構成していなければ、SPF を構成する必要があります。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Microsoft 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。 次は、「[DMARC を使用してメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。 [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)には、Microsoft 365 が KIM チェックに使用する構文とヘッダー フィールドが含まれています。
