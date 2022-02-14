---
title: Office 365 GCC High の DNS レコード
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: 80c1a5d4473af0877e67b6bc9e14a9ffd890e3ba
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806818"
---
# <a name="dns-records-for-office-365-gcc-high"></a>Office 365 GCC High の DNS レコード

*この記事は、High および Office 365 GCC High にMicrosoft 365 GCCします。*

Office 365 GCC High へのオンボーディングの一環として、SMTP ドメインと SIP ドメインを Online Services テナントに追加する必要があります。  これを行うには、Azure AD PowerShell の New-MsolDomain コマンドレットを使用するか、[Azure Government Portal](https://portal.azure.us) を使用してドメインを追加して所有権を確認するプロセスを開始します。

ドメインをテナントに追加して検証したら、次のガイダンスを使用して、以下のサービスに適切な DNS レコードを追加します。  受信 MX レコードおよび既存の Exchange 自動検出レコードに関して、組織のニーズに合わせて以下の表を変更する必要がある場合があります。  これらの DNS レコードをメッセージング チームと調整して、電子メールの停止や配信の誤りを避けることを強く推奨します。

## <a name="exchange-online"></a>Exchange Online

| Type | Priority | ホスト名 | アドレスまたは値をポイントする | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant.mail.protection.office365.us* (詳細については、以下を参照してください) | 1 時間 |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 時間 |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 時間 |

### <a name="exchange-autodiscover-record"></a>Exchange検出レコード

オンプレミスでExchange Server場合は、Exchange Online への移行中に既存のレコードを残し、移行が完了したらそのレコードを更新することをお勧めします。 

### <a name="exchange-online-mx-record"></a>Exchange Online MX レコード

受け入れドメインの MX レコード値は、上記の標準形式に従います。*tenant.mail.protection.office365.us* は、テナントを既定のテナント名の最初の部分に置き換えます。

たとえば、テナント名が contoso.onmicrosoft.us、MX レコード **contoso.mail.protection.office365.us として使用** します。

## <a name="skype-for-business-online"></a>Skype for Business Online

### <a name="cname-records"></a>CNAME レコード

| 種類 | ホスト名 | アドレスまたは値をポイントする | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 時間 |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 時間 |

### <a name="srv-records"></a>SRV レコード

| 種類 | サービス | プロトコル | ポート | 太さ | 優先度 | 名前 | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 時間 |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 時間 |

## <a name="other-dns-records"></a>その他の DNS レコード

> [!IMPORTANT]
> DNS ゾーンに既存の *msoid* CNAME レコードがある場合は、この時点で DNS  からレコードを削除する必要があります。  msoid レコードは、Microsoft 365 Enterprise (以前はOffice 365 ProPlus *)* と互換性がありません。ライセンス認証が成功しません。
