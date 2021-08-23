---
title: ドメインまたは DNS レコードを追加後に問題を特定して解決する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS レコードが正しく設定されていることを確認して、カスタム ドメインのセットアップ中に発生した問題を追跡する方法について説明します。
ms.openlocfilehash: 5dd84e829ed1cd8ea1cc9738ac88eaabcba52648
ms.sourcegitcommit: d792743bc21eec87693ebca51d7307a506d0bc43
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2021
ms.locfileid: "58450096"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>ドメインまたは DNS レコードを追加後に問題を特定して解決する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
ドメインをセットアップしてユーザーと一緒にMicrosoft 365は難しい場合があります。 DNS システムは、操作するには細かい設定があり、ドメインに対する DNS のセットアップ内容は、メールなどの重要な業務活動にも影響を与えます。

> [!NOTE]
> ドメインの状態を確認することで、ドメインに関する問題を確認できます。 [ドメインの **セットアップ**  >  **] に移動** し、[状態] 列に通知 **を表示** します。 問題が発生した場合は、3 つのドット (その他のアクション) を選択し、[正常性の確認] **を選択します**。 開くウィンドウは、ドメインで発生する問題について説明します。
  
## <a name="whats-going-on"></a>何が起こっているのでしょうか?

- [ドメインを確認できない場合](#cant-verify-your-domain)
    
- [Outlookが動作していませんか?](#outlook-isnt-working)
    
- [すべてのユーザーのメールがメールに切り替Microsoft 365メールのみを切り替えたかったのですか?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [非営利団体または学校のアカウントの状態を確認できませんか?](#cant-confirm-non-profit-or-school-account-status)

- [サービスがドメインで動作しない場合](#services-not-working-with-your-domain)
    
- [Web サイトへのアクセスが機能していませんか?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>ドメインを確認できませんか?

ドメイン検証が機能しない現象には共通の原因があることが確認されています。
  
1. **検証レコードの値が正しくない。** DNS ホストで正確な値をコピーし、TXT 検証レコードに貼り付けたことを二重に確認してください。共通の原因の 1 つに、レコードの「MS=」部分を含めていないことが挙げられています。この部分も含める必要があります。 
    
2. **レコードが保存されていない。** DNS ホストによっては、インターネット全体で更新されるようにゾーン ファイル (DNS レコードが保存されているファイル) を保存するという作業も必要になります。 レコードを表示および確認するために、変更Microsoft 365保存済みである必要があります。 
    
3. **レコードがインターネット上で更新されません。** 通常、ユーザーへの新しいレコードの表示には数分しかかかりませんが、場合によっては、数時間かかることもあります。 
    
## <a name="outlook-isnt-working"></a>Outlook が機能していませんか?

ドメインに MX レコードとその他の DNS レコードを正しく設定しているが、メールが機能しない場合、弊社が [Outlook 問題の解消](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)を支援します。
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>すべてのユーザーのメールがメールに切り替Microsoft 365メールのみを切り替えたかったのですか?
<a name="BKMK_EmailSwitched"> </a>

ドメインを Microsoft 365 に追加すると、通常、ドメインの MX レコードが (ユーザーまたは Microsoft 365 によって) Microsoft 365 をポイントして更新され、そのドメインに送信されたメールはすべて Microsoft 365 に送信されます。 MX レコードを変更する前に、ドメインMicrosoft 365メールを持つすべてのユーザーにメールボックスを作成してください。
  
ドメイン上のすべてのユーザーのメールをユーザーに移動しない場合は、Microsoft 365。 代わりに、いくつかの電子メール[アドレスMicrosoft 365をパイロットする手順を実行できます](../setup/domains-faq.yml)。
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>非営利団体または学校のアカウントの状態を確認できませんか?
<a name="BKMK_validateAcct"> </a>

組織のドメインを確認し、サービスを設定しない場合は、いくつかのシナリオがあります。 たとえば、組織が学校Microsoft 365資格を持っていることを証明します。
  
「Microsoft 365 ドメインを確認して所有権、非営利団体、または教育の状態を証明する、または[Yammer](../setup/domains-faq.yml)をアクティブ化する」のガイダンスを参照して、必要なすべての手順を完了してください。 状況ごとに少し異なります。 
  
## <a name="services-not-working-with-your-domain"></a>自分のドメインでサービスが機能しませんか?

Microsoft では、ドメインの DNS セットアップに関わる問題を解消するためのサポートを用意しています。 [ドメインのトラブルシューティング] Microsoft 365、修正が必要なレコードと、レコードを設定する必要があるレコードが正確に表示されます。 

> [!TIP]
> DNS が正しく設定されましたが、メールはデスクトップ上のOutlook機能しませんか? ビジネス向[けに適切な](/exchange/mail-flow-best-practices/mail-flow-best-practices)設定がMicrosoft 365メール フローのシナリオを確認してください。 または、電子メールに関するトラブルシューティングのヘルプの詳細については、以下を参照してください。[問題Outlook修正します](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。 
  
## <a name="accessing-your-website-isnt-working"></a>自分の Web サイトにアクセスできませんか?

DNS の問題を解決しても、引き続き問題が発生する場合は、次のいずれかを試してください。
  
- ユーザーが Web サイトにアクセスできない *場合:contoso.com* の問題 [を追跡する](../setup/add-domain.md)
    
- Web サイトを指す A レコードまたは CNAME レコードを更新[Microsoft 365](../setup/add-domain.md)

## <a name="related-content"></a>関連コンテンツ

[トラブルシューティング: 検証済みのドメイン変更に関するデータの監査](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (記事)\
[ドメインの FAQ](../setup/domains-faq.yml) (記事)

