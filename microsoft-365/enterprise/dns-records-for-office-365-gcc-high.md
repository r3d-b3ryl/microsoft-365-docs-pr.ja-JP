---
title: Office 365 GCC High の DNS レコード
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: '概要: 高値の DNS レコードOffice 365 GCCします。'
hideEdit: true
ms.openlocfilehash: ff4a3e9f4711cc61352d1b547f195054eab9b3fb2181280718f386545fea83fe
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53859061"
---
# <a name="dns-records-for-office-365-gcc-high"></a>Office 365 GCC High の DNS レコード

*この記事は、High および Office 365 GCC High にMicrosoft 365 GCCします。*

Office 365 GCC High へのオンボーディングの一環として、SMTP ドメインと SIP ドメインを Online Services テナントに追加する必要があります。  これを行うには、Azure AD PowerShell の New-MsolDomain コマンドレットを使用するか [、Azure Government Portal](https://portal.azure.us) を使用してドメインを追加して所有権を確認するプロセスを開始します。

ドメインをテナントに追加して検証したら、次のガイダンスを使用して、以下のサービスに適切な DNS レコードを追加します。  受信 MX レコードおよび既存の Exchange 自動検出レコードに関して、組織のニーズに合わせて以下の表を変更する必要がある場合があります。  これらの DNS レコードをメッセージング チームと調整して、電子メールの停止や配信の誤りを避けることを強く推奨します。

## <a name="exchange-online"></a>Exchange Online

| Type | Priority | ホスト名 | ポイント先のアドレスまたは値 | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us (詳細については、以下を参照してください) | 1 Hour |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 Hour |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Exchange自動検出レコード

オンプレミスでExchange Server場合は、Exchange Online への移行中に既存のレコードを残し、移行が完了したらそのレコードを更新することをお勧めします。 

### <a name="exchange-online-mx-record"></a>Exchange OnlineMX レコード

受け入れドメインの MX レコード値は、上記の標準形式に従います。テナント *.mail.protection.office365.us* は、テナントを既定のテナント名の最初の部分に置き換えます。

たとえば、テナント名が contoso.onmicrosoft.us、MX レコード contoso.mail.protection.office365.us として使用します。

## <a name="skype-for-business-online"></a>Skype for Business Online

### <a name="cname-records"></a>CNAME レコード

| 種類 | ホスト名 | ポイント先のアドレスまたは値 | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 Hour |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 Hour |

### <a name="srv-records"></a>SRV レコード

| 種類 | サービス | プロトコル | ポート | 太さ | 優先度 | 名前 | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 Hour |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>追加の DNS レコード

> [!IMPORTANT]
> DNS ゾーンに既存の *msoid* CNAME レコードがある場合は、この時点で DNS からレコードを削除する必要があります。  msoid レコードは、Microsoft 365 Enterprise (以前は *Office 365 ProPlus)* と互換性がなく、ライセンス認証が成功しなかれない。
