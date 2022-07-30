---
title: ドメインまたは DNS レコードを追加後に問題を特定して解決する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS レコードが正しく設定されていることを確認して、カスタム ドメインの設定中に発生する問題を追跡する方法について説明します。
ms.openlocfilehash: 2e4f69b19fd87f45017a304414018995e90703a7
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085161"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>ドメインまたは DNS レコードを追加後に問題を特定して解決する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
Microsoft 365 を使用するようにドメインを設定することは困難な場合があります。 DNS システムは、操作するには細かい設定があり、ドメインに対する DNS のセットアップ内容は、メールなどの重要な業務活動にも影響を与えます。

> [!NOTE]
> ドメインの状態を確認することで、ドメインに関する問題を確認できます。 **[セットアップ ドメイン]** >  に移動し **、[****状態]** 列に通知を表示します。 問題が表示された場合は、3 つのドット (その他のアクション) を選択し、[ **正常性の確認**] を選択します。 開いたウィンドウには、ドメインで発生するすべての問題が表示されます。
  
## <a name="whats-going-on"></a>何が起こっているのでしょうか?

- [ドメインを確認できませんか?](#cant-verify-your-domain)
    
- [Outlook が機能していませんか?](#outlook-isnt-working)
    
- [すべてのユーザーのメールが Microsoft 365 に切り替え、メールを切り替える必要がありましたか?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [非営利団体または学校アカウントの状態を確認できませんか?](#cant-confirm-non-profit-or-school-account-status)

- [サービスがドメインで動作していませんか?](#services-not-working-with-your-domain)
    
- [Web サイトへのアクセスが機能していませんか?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>ドメインを確認できませんか?

ドメイン検証が機能しない現象には共通の原因があることが確認されています。
  
1. **検証レコードの値が正しくない。** DNS ホストで正確な値をコピーし、TXT 検証レコードに貼り付けたことを二重に確認してください。共通の原因の 1 つに、レコードの「MS=」部分を含めていないことが挙げられています。この部分も含める必要があります。 
    
2. **レコードが保存されていない。** DNS ホストによっては、インターネット全体で更新されるようにゾーン ファイル (DNS レコードが保存されているファイル) を保存するという作業も必要になります。 Microsoft 365 がレコードを表示して確認できるように、変更を保存したことを確認します。 
    
3. **レコードがインターネット経由で更新されていません。** 通常、ユーザーへの新しいレコードの表示には数分しかかかりませんが、場合によっては、数時間かかることもあります。 
    
## <a name="outlook-isnt-working"></a>Outlook が機能していませんか?

ドメインに MX レコードとその他の DNS レコードを正しく設定しているが、メールが機能しない場合、弊社が [Outlook 問題の解消](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)を支援します。
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>すべてのユーザーのメールが Microsoft 365 に切り替え、メールを切り替える必要がありましたか?
<a name="BKMK_EmailSwitched"> </a>

Microsoft 365 にドメインを追加すると、通常、ドメインの MX レコードが Microsoft 365 を指すように (ユーザーまたは Microsoft 365 によって) 更新され、そのドメインに送信されたすべての電子メールが Microsoft 365 に送信されます。 MX レコードを変更する前に、ドメインにメールを持っているすべてのユーザーに対して、Microsoft 365 でメールボックスを作成したことを確認します。
  
ドメイン内のすべてのユーザーのメールを Microsoft 365 に移動したくない場合はどうなりますか? [代わりに、少数の電子メール アドレスを使用して Microsoft 365 をパイロット](../setup/domains-faq.yml)する手順を実行できます。
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>非営利団体または学校アカウントの状態を確認できませんか?
<a name="BKMK_validateAcct"> </a>

組織のドメインを確認するだけで、サービスを設定しない場合は、いくつかのシナリオがあります。 たとえば、組織が学校サブスクリプションの資格を持っていることを Microsoft 365 に証明します。
  
[所有権、非営利団体、教育機関の状態を証明したり、Yammer をアクティブ化したりして、必要なすべての手順が完了していることを確認するには、「Microsoft 365 ドメインを確認](../setup/domains-faq.yml)する」のガイダンスを参照してください。 状況ごとに少し異なります。 
  
## <a name="services-not-working-with-your-domain"></a>自分のドメインでサービスが機能しませんか?

Microsoft では、ドメインの DNS セットアップに関わる問題を解消するためのサポートを用意しています。 Microsoft 365 のドメイントラブルシューティング ツールでは、修正が必要なレコードと、レコードを設定する必要がある内容が正確に表示されます。 

> [!TIP]
> DNS が正しく設定されましたが、デスクトップ上の Outlook ではメールが機能しませんか? [Microsoft 365 で使用できるさまざまなメール フローのシナリオ](/exchange/mail-flow-best-practices/mail-flow-best-practices)を確認して、ビジネス向けに正しく設定されていることを確認します。 または、メールに関するトラブルシューティングのヘルプについては、 [こちら:Outlook の問題を解決する方法](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)に関するページを参照してください。 
  
## <a name="accessing-your-website-isnt-working"></a>自分の Web サイトにアクセスできませんか?

DNS の問題を解決しても、引き続き問題が発生する場合は、次のいずれかを試してください。
  
- ユーザーが *contoso.com* で Web サイトにアクセスできない: [Web サイトの問題を追跡](../setup/add-domain.md)する
    
- Web サイトを指すように A レコードまたは CNAME レコードを更新することはできません:[Microsoft 365 でカスタム DNS レコードを更新](../setup/add-domain.md)する

## <a name="related-content"></a>関連コンテンツ

[トラブルシューティング: 検証済みのドメイン変更に関するデータの監査](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (記事)\
[ドメインの FAQ](../setup/domains-faq.yml) (記事)

