---
title: ドメインに関する FAQ
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: よく寄せられる質問に対する回答を探して、ドメインの詳細についてご確認ください。
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845846"
---
# <a name="domains-faq"></a>ドメイン FAQ

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

この記事には、Microsoft 365 のドメインに関してよく寄せられる質問に対する回答が含まれます。

質問の回答が見つからない場合は、コメントを残してお知らせください。ご質問を FAQ の一覧に追加します。

この記事の内容

- [MX 優先度とは](#what-is-mx-priority)
- [自分のドメインの SPF レコードを検証するにはどうすればよいですか?](#how-can-i-validate-spf-records-for-my-domain)
- [ドメイン名とは何ですか?](#what-is-a-domain-name)
- [自分の DNS プロバイダーが特定のレコードの種類をサポートしていない場合はどうなりますか?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [Microsoft 365 の既定のドメインを設定または変更する方法](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [カスタム サブドメインまたは複数のドメインを Microsoft 365 に追加できますか。](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Microsoft 365 から別のホストにドメインを移行するにはどうしますか?](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- ["onmicrosoft.com" ドメインがあるのはなぜですか?](#why-do-i-have-an-onmicrosoftcom-domain)
- ["onmicrosoft.de" ドメインがあるのはなぜですか?](#why-do-i-have-an-onmicrosoftde-domain)
- [非営利団体または教育機関のステータスを確認するにはどうすればよいですか?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>MX 優先度とは何ですか?

メールは最も小さい優先順位番号 (最高の優先順位) でメール交換サーバーに配信されるので、メールのルーティングに使用する MX レコードは、最も小さい優先順位番号 (通常は 0 または *高い*  優先順位) が指定されている必要があります。 
  
- MX レコードを作成するときには、ほとんどの DNS ホスティング プロバイダーで、優先度順位を設定する必要があります。
    
- ボックスのラベルは [ *優先度*  ] の場合もあれば、[  *優先順位*  ] の場合もあります。 
    
- 数値を要求される場合もあれば、[ *低*  ]、[  *中*  ]、または [  *高*  ] を選択するように要求される場合もあります。 
    
- MX レコードが 1 つだけの場合は、任意の値を優先順位に指定できます。
    
- 複数の MX レコードがある場合は、メールのルーティングの MX レコードがドメインを所有していることを検証するために使用されるレコードより高い優先度になっていることを確認します。
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>SPF レコードはどうやって検証できますか?

重要なのは、SPF に対して  **TXT レコードを 1 つだけ持っており、作成だけです**。 既に SPF レコードがある場合は、新規に作成するのではなく、新しい Microsoft 365 の値を追加します。 Microsoft メール用の SPF レコードを追加または更新した後、次のツールのいずれかを使用して構文が正しいことを確認してください。 
  
- [SPF レコード テスト ツール](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [Dig Web インターフェイス](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>ドメイン名とは何ですか?

ドメインとは、メール アドレスの **@** 記号の後や、Web アドレスの **www.** の後に表示される固有の名前です。通常は、  *yourbusiness.com*  や  *stateuniversity.edu*  のように、組織の名前と標準的なインターネット サフィックスの形式を取ります。 
  
**"rob \@ contoso.com" のようなカスタム ドメインを**Microsoft 365 で使用すると、ブランドの要件や確認の度合いや認識の構築に役立ちます。 
  
Microsoft [365 でドメインを購入して自動的](../get-help-with-domains/buy-a-domain-name.md)に設定するか、ドメイン レジストラーから購入や所有しているドメインの持続を行えます。
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>DNS プロバイダーで特定のレコードの種類がサポートされない場合はどうなりますか?

独自の DNS レコードを管理している場合、DNS ホストが Microsoft 365 に必要な DNS レコードの一部しかサポートしていないと、Microsoft 365 の一部の機能は動作しません。 必要な DNS レコードをすべてサポートしているレジストラーにドメインを移行することをお勧めします。
  
すべての必須の DNS レコードをサポートするプロバイダー。
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Hover
    
- MyHosting.com
    
- Name.com
    
- Nearly Free Speech
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Microsoft 365 の既定のドメインを設定または変更する方法

既定のドメインを選択するには、その前に、少なくとも 1 つのカスタム ドメインが Microsoft 365 に追加されている必要があります。

::: moniker range="o365-worldwide"

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end
    
2. [**ドメイン**] ページで、新しいメール アドレスの既定として設定するドメインを選択します。 
    
3. [**既定に設定**] を選択します。
    
::: moniker range="o365-worldwide"

*.onmicrosoft.com* ドメインの最初の部分の名前を変更することはできません。 

::: moniker-end

::: moniker range="o365-germany"

*.onmicrosoft.de* ドメインの最初の部分の名前を変更することはできません。 

::: moniker-end

::: moniker range="o365-21vianet"

*.partner.onmschina.cn* ドメインの最初の部分の名前を変更することはできません。 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>カスタム サブドメインまたは複数のドメインを Microsoft 365 に追加できますか。

::: moniker range="o365-worldwide"

はい。 サブドメインを追加するには、レジストラーの Web サイトでの DNS 設定を自分で管理する必要があります。 NS レコードの DNS 設定の管理を Microsoft が許可している場合や、Microsoft からドメインを購入した場合は、サブドメインを追加できません。

::: moniker-end

::: moniker range="o365-germany"

はい。サブドメインを追加するには、レジストラーの Web サイトでの DNS 設定を自分で管理する必要があります。NS レコードの DNS 設定の管理を Microsoft が行っている場合または Microsoft からドメインを購入した場合は、サブドメインを追加できません。

::: moniker-end

::: moniker range="o365-21vianet"

はい。サブドメインを追加するには、レジストラーの Web サイトでの DNS 設定を自分で管理する必要があります。NS レコードの DNS 設定の管理を 21Vianet が行っている場合は、サブドメインを追加できません。

::: moniker-end

通常、最大 900 のドメインを Microsoft 365 サブスクリプションに追加できます。
  
例えば、contoso.com と contosomaketing.com の各ドメインを追加し、その後に www.contoso.com、www.partners.contoso.com、www.partners.marketing.contoso.com などのサブドメインを追加することができます。
  
サブドメインを追加すると、確認が行われる親ドメインでの確認に基づき、自動的に確認されます。
  
複数のドメインを Microsoft 365 に追加すると、追加した任意のドメインで任意のサービス (メールなど) をホストできます。  *ドメインの MX レコードを更新してメールを Microsoft 365 に変更すると、そのドメインに送信されたすべてのメールが Microsoft 365 に送信されるはずです。* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Microsoft 365 サブスクリプションcontoso.com追加した場合は、サブドメイン アクセスxyz.contoso.com別の Microsoft 365 組織に追加することもできます。 サブドメインを追加すると、DNS ホスティング プロバイダーに TXT レコードを追加するように求めるメッセージが表示されます。

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>Microsoft 365 から別のホストにドメインを移行するにはどうしますか?

ドメインを移行する手順については、「Microsoft から別 [のホストへのドメインの移行」を参照してください](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)。

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>カスタム ドメインから Microsoft 365 をパイロットする

カスタム ドメインから Microsoft 365 メールボックスに Microsoft 365 の電子メール機能をパイロットする手順については、カスタム [ドメインから Microsoft 365 のパイロットを行う手順を参照してください](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)。

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>"onmicrosoft.com" ドメインがあるのはなぜですか?

サービスにサインアップすると、Microsoft 365 *contoso.onmicrosoft.com*ドメインは、お使いのドメインを作成します。 サインアップ時に作成するユーザー ID には、ユーザー ID のようなドメイン*がalan@contoso.onmicrosoft.com。* 
  
 **メールを * \@ 他*の contoso.com**と同じメールにしたい場合は、 [ドメイン](../get-help-with-domains/buy-a-domain-name.md) を購入するか、または既に [ドメインを所有している場合は、Microsoft 365](add-domain.md) にユーザーとドメインを追加する手順だけに従ってください。 
  
- **サインアップ後に onmicrosoft ドメインの名前は変更できません** 。 たとえば、選んだ初期ドメインが fourthcoffee.onmicrosoft.com の場合、fabrikam.onmicrosoft.com に変更することはできません。 別のメールボックス メールボックスonmicrosoft.comするには、Microsoft 365 で新しいサブスクリプションを開始する必要があります。 
    
- **チーム サイトの URL の名前を変更することはできません。** チーム サイトの URL は onmicrosoft.com ドメイン名に基づいています。SharePoint Online のアーキテクチャの動作方法のため、残念ながらチーム サイトの名前は変更できません。 
    
- **onmicrosoft ドメインは、削除できません。** Microsoft 365 では、サブスクリプションの処理に必要な処理でこの機能が使用されるので、保持する必要があります。 カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。 
    
ドメインを追加した後でも、初期の onmicrosoft.com ドメインを使うことができます。初期ドメインは、メールやその他のサービスでも引き続き利用できます。
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>"onmicrosoft.de" ドメインがあるのはなぜですか?

サービスにサインアップすると、Microsoft 365 *では、contoso.onmicrosoft.de*ようなドメインが作成されます。 サインアップ時に作成するユーザー ID には、ユーザーのドメイン*などalan@contoso.onmicrosoft.de。* 
  
 **メールを alan@contoso.de のように表示する場合は、*ドメイン*を**[購入](../get-help-with-domains/buy-a-domain-name.md)するか、または[既にドメインを所有している場合は、Microsoft 365](add-domain.md)にユーザーとドメインを追加する手順に従ってください。 
  
- **サインアップ後に onmicrosoft ドメインの名前は変更できません** 。 たとえば、選択した初期ドメインが作成されたfourthcoffee.onmicrosoft.deドメインを変更してリストにfabrikam.onmicrosoft.de。 別のメールボックス メールボックスonmicrosoft.deするには、Microsoft 365 で新しいサブスクリプションを開始する必要があります。 
    
- **チーム サイトの URL の名前を変更することはできません。** チーム サイトの URL は onmicrosoft.de ドメイン名に基づいています。SharePoint Online のアーキテクチャの動作方法のため、残念ながらチーム サイトの名前は変更できません。 
    
- **onmicrosoft ドメインは、削除できません。** Microsoft 365 では、サブスクリプションの処理に必要な処理でこの機能が使用されるので、保持する必要があります。 カスタム ドメインを追加した場合は、初期ドメインを使う必要はありません。 
    
ドメインを追加した後でも、初期の onmicrosoft.de ドメインを使うことができます。初期ドメインは、メールやその他のサービスでも引き続き利用できます。
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>非営利団体または教育機関のステータスを確認するにはどうすればよいですか?

1. [管理センター](https://docs.microsoft.com/microsoft-365/admin/admin-home)で [**セットアップ**] を選択してウィザードを開始します。 (最初に Microsoft 365 にサインインしてください。) 
    
2. 学校の管理者になるには、Microsoft 365 の [  **管理者** になる] オプションを選択します。 
    
3. TXT DNS レコードをドメインの DNS ホスト Web サイトで追加するように求めるメッセージが表示されます。 それはなぜでしょうか。 DNS ホストからサインインしてドメインのレコードを追加すると、Microsoft 365 でドメイン名の所有者であることが証明されます。
    
4. レコードを追加したら Microsoft 365 ポータルに戻り、レコードを追加したことを確認します。これにより、Microsoft 365 で確認が行えます。
    
非営利団体で Microsoft 365 の取得を計画している場合 [組織がサービスに関してライセンス](https://www.microsoft.com/en-us/nonprofits/eligibility) を設定し、サインアップしたことを確認します。 
  
学校の管理者になる方法の詳細については、 [こちらのヘルプ記事をご覧ください](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)。