---
title: Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS レコードが正しく設定されていることを確認して、カスタムドメインのセットアップ中に発生した問題を追跡する方法について説明します。
ms.openlocfilehash: 277e87ad6b06db0b1ef3b3cb5eaaa45a2e77ed6f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255140"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a>Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
Office 365 と連携するようにドメインをセットアップすることは、骨の折れる作業になる場合があります。 DNS システムは、操作するには細かい設定があり、ドメインに対する DNS のセットアップ内容は、メールなどの重要な業務活動にも影響を与えます。

> [!NOTE]
> ドメインに問題があるかどうかは、その状態を確認することで確認できます。 [**設定** > ] の [**ドメイン**] に移動し、[**状態**] 列に通知を表示します。 問題が発生した場合は、[その他のアクション (3 つのドット)] を選択して、[**状態の確認**] を選択します。 開いているウィンドウには、ドメインで発生している問題が表示されます。
  
## <a name="whats-going-on"></a>何が起こっているのでしょうか?

- [ドメインを確認できませんか?](#cant-verify-your-domain)
    
- [Outlook が動作していませんか?](#outlook-isnt-working)
    
- [すべてのユーザーのメールが Office 365 に切り替えられ、メールの切り替えのみが必要になりましたか?](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [非営利団体または学校のアカウントの状態を確認できませんか?](#cant-confirm-non-profit-or-school-account-status)

- [ドメインでサービスが動作していませんか?](#services-not-working-with-your-domain)
    
- [Web サイトへのアクセスが機能しない場合](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>ドメインを確認できませんか?
<a name="BKMK_verify"> </a>

ドメイン検証が機能しない現象には共通の原因があることが確認されています。
  
1. **検証レコードの値が正しくない。** DNS ホストで正確な値をコピーし、TXT 検証レコードに貼り付けたことを二重に確認してください。共通の原因の 1 つに、レコードの「MS=」部分を含めていないことが挙げられています。この部分も含める必要があります。 
    
2. **レコードが保存されていない。** DNS ホストによっては、インターネット全体で更新されるようにゾーン ファイル (DNS レコードが保存されているファイル) を保存するという作業も必要になります。Office 365 がレコードを表示し、確認できるように、変更内容を必ず保存してください。 
    
3. **レコードはインターネット経由で更新されていません。** 通常、ユーザーへの新しいレコードの表示には数分しかかかりませんが、場合によっては、数時間かかることもあります。 
    
## <a name="outlook-isnt-working"></a>Outlook が機能していませんか?
<a name="BKMK_OutlookBroken"> </a>

ドメインに MX レコードとその他の DNS レコードを正しく設定しているが、メールが機能しない場合、弊社が [Outlook 問題の解消](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx)を支援します。
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a>すべてのユーザーのメールが Office 365 に切り替えられ、メールの切り替えのみが必要になりましたか?
<a name="BKMK_EmailSwitched"> </a>

Office 365 にドメインを追加すると、通常は、ドメインの MX レコードが (ユーザーまたは Office 365 によって) Office 365 をポイントするように更新され、そのドメインに送信されるすべての電子メールが Office の365に送られ始めます。 MX レコードを変更する前に、自分のドメインにメールを持っているすべてのユーザーに対して Office 365 でメールボックスを作成していることを確認してください。
  
ドメイン上のすべてのユーザーのメールを Office 365 に移動したくない場合は、どうすればよいですか? [代わりに、少数のメールアドレスで Office 365 のパイロット](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx)を実施するための手順を実行することができます。
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>非営利団体または学校のアカウントの状態を確認できませんか?
<a name="BKMK_validateAcct"> </a>

組織のドメインを検証するだけで、サービスをセットアップしない場合は、いくつかのシナリオがあります。 たとえば、組織が学校のサブスクリプションを認定していることを Office 365 に証明する場合などです。
  
[「Office 365 ドメインの確認」を参照して、所有権、非営利団体または教育機関の状態を証明するか、Yammer を有効](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590)にして必要なすべての手順を完了したことを確認してください。 状況によって、これは少し異なります。 
  
## <a name="services-not-working-with-your-domain"></a>自分のドメインでサービスが機能しませんか?
<a name="BKMK_Test"> </a>

Microsoft では、ドメインの DNS セットアップに関わる問題を解消するためのサポートを用意しています。 Office 365 でドメインのトラブルシューティング ツールを起動すると、修正が必要なすべてのレコードと、レコードに設定する必要がある内容そのものが表示されます。 

> [!TIP]
> DNS は正しくセットアップされたが、デスクトップの Outlook でメールが機能しない場合は、「 [different mail flow scenarios you can have with Office 365 (Office 365 で実現できるその他のメール フローのシナリオ)](https://go.microsoft.com/fwlink/?LinkId=787530)」を参照して、お客様のビジネスに合わせて正しく設定されていることをご確認ください。または、次のサイトでメールに関するトラブルシューティングを参照してください。[Outlook でのエラーを修正する](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx) 
  
## <a name="accessing-your-website-isnt-working"></a>自分の Web サイトにアクセスできませんか?
<a name="BKMK_Website"> </a>

DNS の問題を解決しても、引き続き問題が発生する場合は、次のいずれかを試してください。
  
- 他のユーザーが Web サイト (www.mydomain.com) にアクセスできない場合: [Web サイトの問題を特定する](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- A レコードまたは CNAME レコードが Web サイトを示すように更新できない場合: [Office 365 でカスタムの DNS レコードを更新する](../dns/add-or-edit-custom-dns-records.md)
    
