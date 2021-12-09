---
title: トランスポートExchange Onlineセキュリティ (TLS) を使用して電子メール接続をセキュリティで保護する方法
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/08/2021
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: トランスポート層Exchange Onlineセキュリティ (TLS) Microsoft 365転送秘密 (FS) を使用して電子メール通信をセキュリティで保護する方法について学習します。 また、Microsoft によって発行された証明書に関する情報も取得Exchange Online。
ms.openlocfilehash: 1caf4a8425f4a8e7c340e8a52d785027e99a1618
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371498"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法

トランスポート層Exchange Onlineセキュリティ (TLS) Microsoft 365転送秘密 (FS) を使用して電子メール通信をセキュリティで保護する方法について学習します。 また、Microsoft によって発行された証明書に関する情報も提供Exchange Online。
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>TLS の基本Microsoft 365およびExchange Online

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。 TLS は、Secure Sockets Layer (SSL) に取ってかわるもので、SSL 3.1 と呼ばれます。 Exchange Online TLS を使用して、Exchange サーバー間の接続と、Exchange サーバーと、オンプレミスの Exchange サーバーや受信者のメール サーバーなどの他のサーバー間の接続を暗号化します。 接続が暗号化された後、その接続を介して送信されたデータはすべて、暗号化されたチャネルを介して送信されます。 ただし、TLS で暗号化された接続を介して送信されたメッセージを転送する場合、そのメッセージは必ずしも暗号化されません。 TLS はメッセージを暗号化し、接続を暗号化します。
  
メッセージを暗号化する場合は、メッセージの内容を暗号化する暗号化テクノロジを使用します。 たとえば、メッセージ暗号化または S/MIME Office使用できます。 メッセージ[暗号化の詳細については、「Office 365](email-encryption.md)および Office 365 Message Encryption [(OME)](ome.md)での電子メールの暗号化」を参照Office 365。
  
Microsoft とオンプレミス組織またはパートナーなどの別の組織との間の通信のセキュリティで保護されたチャネルを設定する場合は、TLS を使用します。 Exchange Onlineは常に最初に TLS を使用してメールをセキュリティで保護しますが、相手が TLS セキュリティを提供していない場合は使用することはできません。 コネクタを使用して、オンプレミス サーバーまたは重要なパートナーに対してすべてのメールをセキュリティで保護する方法については、次の記事 *をご覧ください*。

クラス最高の暗号化をお客様に提供するために、Microsoft は Office 365 および Office 365 GCC でトランスポート層セキュリティ (TLS) バージョン 1.0[](tls-1.0-and-1.1-deprecation-for-office-365.md)および 1.1[を非推奨にしました](tls-1-2-in-office-365-gcc.md)。 ただし、TLS なしで暗号化されていない SMTP 接続を引き続き使用できます。 暗号化なしで電子メールを送信することをお勧めしません。  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>ユーザー Exchange Online間で TLS をExchange Onlineする方法

Exchange Onlineサーバーは、TLS 1.2 を使用Exchange Onlineデータセンター内の他のサーバーへの接続を常に暗号化します。 組織内の受信者にメッセージを送信すると、TLS をExchange Online暗号化された接続を使用してメッセージが自動的に送信されます。 Exchange Online転送秘密を使用してセキュリティで保護された TLS を使用して、暗号化された接続を使用して他の顧客に送信する電子メールも送信します。
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>信頼Microsoft 365パートナーと外部のパートナー Microsoft 365 TLS を使用する方法

既定では、Exchange Onlineは常に *日和見 TLS を使用します*。 日和見 TLS とは、Exchange Online が最も安全なバージョンの TLS との接続を常に暗号化しようとし、その後、両者が合意できる TLS 暗号を見つけるまで、TLS 暗号のリストを下に移動します。 Exchange Online を構成して、その受信者へのメッセージが安全な接続を使用する必要がある場合を限り、既定では、受信者組織が TLS 暗号化をサポートしない場合、メッセージは暗号化なしで送信されます。 ほとんどの企業では、日和見 TLS で十分です。 ただし、医療、銀行、政府機関などのコンプライアンス要件を持つ企業では、TLS を要求または強制するExchange Onlineを構成できます。 手順については、「メール フローの構成」の「コネクタを使用してメール フローを[構成する」をOffice 365。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
  
組織と信頼できるパートナー組織の間で TLS を構成する場合は、Exchange Online *TLS* を使用して信頼できる通信チャネルを作成できます。 強制 TLS では、パートナー組織がセキュリティ証明書を使用Exchange Onlineを認証してメールを送信する必要があります。 パートナーは独自の証明書を管理する必要があります。 Exchange Onlineコネクタを使用して、受信者の電子メール プロバイダーに到着する前に、承認されていないアクセスから送信するメッセージを保護します。 コネクタを使用してメール フローを構成する方法については、「Configure mail flow using connectors in Office 365」[を参照してください](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS およびハイブリッド Exchange Server展開

ハイブリッド Exchange 展開を管理している場合、オンプレミスの Exchange サーバーは、セキュリティ証明書を使用して Microsoft 365 に対して認証を行い、メールボックスが Office 365 内にある受信者にメールを送信する必要があります。 その結果、オンプレミスのサーバー用の独自のセキュリティ証明書を管理Exchangeがあります。 また、これらのサーバー証明書を安全に保存および保守する必要があります。 ハイブリッド展開での証明書の管理の詳細については、「ハイブリッド展開の [証明書要件」を参照してください](/exchange/certificate-requirements)。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>ユーザーのサーバーに強制的な TLS をExchange OnlineするOffice 365

ユーザー Exchange Online、送信および受信メールのセキュリティを確保するために TLS を強制的に動作するには、TLS を必要とする複数のコネクタをセットアップする必要があります。 ユーザー メールボックスに送信されるメッセージには 1 つのコネクタ、ユーザー メールボックスから送信されるメッセージには別のコネクタが必要です。 これらのコネクタは、Exchangeの管理センターにOffice 365。 手順については、「メール フローの構成」の「コネクタを使用してメール フローを[構成する」をOffice 365。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

## <a name="tls-certificate-information-for-exchange-online"></a>サーバーの TLS 証明書Exchange Online

次の表に、Exchange Onlineによって使用される証明書情報について説明します。 ビジネス パートナーがメール サーバーで強制的な TLS を設定している場合は、この情報をユーザーに提供する必要があります。 セキュリティ上の理由から、証明書は変更されます。 現在の証明書は、2020 年 9 月 24 日から有効です。

### <a name="current-certificate-information-valid-from-september-24-2020"></a>2020 年 9 月 24 日から有効な現在の証明書情報
  
| 属性 | 値 |
|:-----|:-----|
|証明機関のルート発行者|DigiCert CA – 1|
|証明書名|mail.protection.outlook.com|
|組織|Microsoft Corporation|
|組織単位|www.digicert.com|
|証明書キーの強さ|2048|

## <a name="get-more-information-about-tls-certificates-and-microsoft-365-and-download-certificates"></a>TLS、証明書、および証明書の詳細Microsoft 365ダウンロードする

[Microsoft 365チェーンと証明書のダウンロード](encryption-office-365-certificate-chains.md)

[Microsoft 365チェーンと証明書のダウンロード - DOD と GCC High](encryption-office-365-certificate-chains-itar.md)

サポートされている暗号スイートの一覧については、「暗号化に関する [テクニカル リファレンスの詳細」を参照してください](technical-reference-details-about-encryption.md)。
  
[パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[電子メール セキュリティを強化したコネクタ](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Microsoft 365 での暗号化](encryption.md)
