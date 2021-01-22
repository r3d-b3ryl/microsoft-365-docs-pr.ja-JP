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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS レコードが正しく設定されていることを確認して、カスタム ドメインのセットアップ中に発生した問題を追跡する方法について説明します。
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926392"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>ドメインまたは DNS レコードを追加後に問題を特定して解決する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
Microsoft 365 と一緒に動作するためにドメインをセットアップする作業は、難しい場合があります。 DNS システムは、操作するには細かい設定があり、ドメインに対する DNS のセットアップ内容は、メールなどの重要な業務活動にも影響を与えます。

> [!NOTE]
> ドメインの状態を確認することで、ドメインに関する問題を確認できます。 [セットアップ **ドメイン]**  >  **に移動し**、[状態] 列に通知 **を表示** します。 If you see an issue, select More actions (three dots), and then choose **Check health**. 開くウィンドウには、ドメインで発生している問題が表示されます。
  
## <a name="whats-going-on"></a>何が起こっているのでしょうか?

- [ドメインを確認できない場合](#cant-verify-your-domain)
    
- [Outlook が動作していませんか?](#outlook-isnt-working)
    
- [すべてのユーザーのメールが Microsoft 365 に切り替わると、メールの切り替えだけが必要ですか?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [非営利団体または学校のアカウントの状態を確認できない場合](#cant-confirm-non-profit-or-school-account-status)

- [サービスがドメインで機能しない場合](#services-not-working-with-your-domain)
    
- [Web サイトにアクセスできない場合](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>ドメインを確認できませんか?
<a name="BKMK_verify"> </a>

ドメイン検証が機能しない現象には共通の原因があることが確認されています。
  
1. **検証レコードの値が正しくない。** DNS ホストで正確な値をコピーし、TXT 検証レコードに貼り付けたことを二重に確認してください。共通の原因の 1 つに、レコードの「MS=」部分を含めていないことが挙げられています。この部分も含める必要があります。 
    
2. **レコードが保存されていない。** DNS ホストによっては、インターネット全体で更新されるようにゾーン ファイル (DNS レコードが保存されているファイル) を保存するという作業も必要になります。 Microsoft 365 がレコードを表示して確認できるよう、変更内容が保存済みである必要があります。 
    
3. **レコードがインターネット上で更新されません。** 通常、ユーザーへの新しいレコードの表示には数分しかかかりませんが、場合によっては、数時間かかることもあります。 
    
## <a name="outlook-isnt-working"></a>Outlook が機能していませんか?
<a name="BKMK_OutlookBroken"> </a>

ドメインに MX レコードとその他の DNS レコードを正しく設定しているが、メールが機能しない場合、弊社が [Outlook 問題の解消](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)を支援します。
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>すべてのユーザーのメールが Microsoft 365 に切り替わると、メールの切り替えだけが必要ですか?
<a name="BKMK_EmailSwitched"> </a>

ドメインを Microsoft 365 に追加すると、通常、ドメインの MX レコードが (お客様または Microsoft 365 によって) Microsoft 365 を指し示す更新され、そのドメインに送信されるメールはすべて Microsoft 365 に届きます。 MX レコードを変更する前に、ドメインにメールを持つすべてのユーザーのメールボックスが Microsoft 365 に作成されている必要があります。
  
ドメイン上のすべてのユーザーのメールを Microsoft 365 に移動したくない場合は、 You can take steps to [pilot Microsoft 365 with just a few email addresses instead.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>非営利団体または学校のアカウントの状態を確認できない場合
<a name="BKMK_validateAcct"> </a>

組織のドメインを確認し、サービスを設定しない場合は、いくつかのシナリオがあります。 たとえば、組織が学校のサブスクリプションの資格を持っていることを Microsoft 365 に証明する場合です。
  
所有権、非営利団体、または教育のステータスを証明したり、Yammer をアクティブ化して必要なすべての手順を完了したりするには [、「Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) ドメインを確認する」のガイダンスを参照してください。 状況ごとに少し異なります。 
  
## <a name="services-not-working-with-your-domain"></a>自分のドメインでサービスが機能しませんか?
<a name="BKMK_Test"> </a>

Microsoft では、ドメインの DNS セットアップに関わる問題を解消するためのサポートを用意しています。 Microsoft 365 のドメイン トラブルシューティング ツールには、修正が必要なレコードと、レコードを設定する必要があるレコードが正確に表示されます。 

> [!TIP]
> DNS が正しくセットアップされましたが、デスクトップ上の Outlook でメールが機能しない場合 [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices)で使用できるさまざまなメール フロー シナリオを確認して、ビジネスに合った設定が正しく行されていることを確認してください。 または、ここでメールに関するトラブルシューティングのヘルプを表示: [Outlook の問題を解決します](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)。 
  
## <a name="accessing-your-website-isnt-working"></a>自分の Web サイトにアクセスできませんか?
<a name="BKMK_Website"> </a>

DNS の問題を解決しても、引き続き問題が発生する場合は、次のいずれかを試してください。
  
- 他のユーザーが Web サイト (www.mydomain.com) にアクセスできない場合: [Web サイトの問題を特定する](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- A レコードまたは CNAME レコードを更新して Web サイトをポイントできない: [Microsoft 365](../dns/add-or-edit-custom-dns-records.md)でカスタム DNS レコードを更新する

## <a name="related-content"></a>関連コンテンツ

[トラブルシューティング: 確認済みドメインの変更に関するデータを監査する](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
