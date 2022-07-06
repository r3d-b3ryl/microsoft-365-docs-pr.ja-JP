---
title: メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法
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
description: Exchange Onlineと Microsoft 365 がトランスポート層セキュリティ (TLS) と Forward Secrecy (FS) を使用して電子メール通信をセキュリティで保護する方法について説明します。 Microsoft for Exchange Onlineによって発行された証明書に関する情報も取得します。
ms.openlocfilehash: 93f71e38e3063aeec0c423dbfea25ac463a3e46f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66641562"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法

Exchange Onlineと Microsoft 365 がトランスポート層セキュリティ (TLS) と Forward Secrecy (FS) を使用して電子メール通信をセキュリティで保護する方法について説明します。 Microsoft for Exchange Onlineによって発行された証明書に関する情報も提供されます。
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Microsoft 365 と Exchange Online の TLS の基本

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。 TLS は Secure Sockets Layer (SSL) に取って代わるものであり、多くの場合、SSL 3.1 と呼ばれます。 Exchange Online TLS を使用して、Exchange サーバー間の接続と、Exchange サーバーと、オンプレミスの Exchange サーバーや受信者のメール サーバーなどの他のサーバー間の接続を暗号化します。 接続が暗号化されると、その接続を介して送信されたすべてのデータは、暗号化されたチャネルを介して送信されます。 ただし、TLS で暗号化された接続を介して送信されたメッセージを転送する場合、そのメッセージは必ずしも暗号化されるとは限りません。 TLS はメッセージを暗号化せず、接続のみを暗号化します。
  
メッセージを暗号化する場合は、メッセージの内容を暗号化する暗号化テクノロジを使用します。 たとえば、Microsoft Purview Message Encryptionまたは S/MIME を使用できます。 [Office 365でのメッセージの暗号化については、「Office 365の電子メール](email-encryption.md)[暗号化](ome.md)」と「メッセージ暗号化」を参照してください。
  
Microsoft とオンプレミスの組織、またはパートナーなどの別の組織間の通信のセキュリティで保護されたチャネルを設定する場合は、TLS を使用します。 Exchange Online常に最初に TLS を使用してメールをセキュリティで保護しようとしますが、相手が TLS セキュリティを提供していない場合は使用できません。 *コネクタ* を使用して、オンプレミス サーバーまたは重要なパートナーに対するすべてのメールをセキュリティで保護する方法を確認してください。

お客様にクラス最高の暗号化を提供するために、Microsoft は、[Office 365および Office 365 GCC](tls-1-2-in-office-365-gcc.md) [でトランスポート](tls-1.0-and-1.1-deprecation-for-office-365.md)層セキュリティ (TLS) バージョン 1.0 および 1.1 を非推奨にしました。 ただし、TLS なしで暗号化されていない SMTP 接続を引き続き使用できます。 暗号化なしで電子メールを送信することはお勧めしません。  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online顧客間で TLS を使用Exchange Online方法

Exchange Online サーバーは、TLS 1.2 を使用して、データ センター内の他のExchange Online サーバーへの接続を常に暗号化します。 組織内の受信者にメッセージを送信すると、TLS を使用して暗号化された接続経由でメッセージが自動的に送信Exchange Online。 Exchange Onlineは、転送秘密を使用してセキュリティで保護された TLS を使用して、暗号化された接続を介して他の顧客に送信する電子メールも送信します。
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Microsoft 365 が Microsoft 365 と外部の信頼できるパートナーの間で TLS を使用する方法

既定では、Exchange Onlineは常に *日和見的 TLS を使用します*。 日和見 TLS とは、Exchange Online常に最も安全なバージョンの TLS で接続を暗号化しようとし、その後、両方の当事者が同意できる TLS 暗号が見つかるまで TLS 暗号の一覧を下に移動することを意味します。 受信者へのメッセージがセキュリティで保護された接続を使用する必要があることを確認するようにExchange Onlineを構成していない限り、既定では、受信者組織が TLS 暗号化をサポートしていない場合、メッセージは暗号化なしで送信されます。 ほとんどの企業では、日和見 TLS で十分です。 ただし、医療、銀行、政府機関などのコンプライアンス要件を持つ企業の場合は、TLS を要求または強制するようにExchange Onlineを構成できます。 手順については、「[Office 365のコネクタを使用してメール フローを構成する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」を参照してください。
  
組織と信頼できるパートナー組織の間で TLS を構成する場合、Exchange Online *強制的に TLS* を使用して信頼できる通信チャネルを作成できます。 強制的な TLS を使用するには、パートナー組織がセキュリティ証明書を使用してExchange Onlineに対して認証を行い、メールを送信する必要があります。 パートナーは、独自の証明書を管理する必要があります。 Exchange Onlineでは、コネクタを使用して、受信者の電子メール プロバイダーに到着する前に、未承認のアクセスから送信したメッセージを保護します。 コネクタを使用してメール フローを構成する方法については、「[Office 365のコネクタを使用したメール フローの構成](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」を参照してください。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS とハイブリッド Exchange Serverのデプロイ

ハイブリッド Exchange 展開を管理している場合、オンプレミスの Exchange サーバーは、セキュリティ証明書を使用して Microsoft 365 に対して認証を行い、メールボックスがOffice 365内にある受信者にメールを送信する必要があります。 その結果、オンプレミスの Exchange サーバー用に独自のセキュリティ証明書を管理する必要があります。 また、これらのサーバー証明書を安全に格納して管理する必要があります。 ハイブリッド展開での証明書の管理の詳細については、「 [ハイブリッド展開の証明書要件」を](/exchange/certificate-requirements)参照してください。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Office 365でExchange Onlineに強制 TLS を設定する方法

Exchange Online顧客の場合、送信および受信したすべての電子メールをセキュリティで保護するために TLS を強制動作させるには、TLS を必要とする複数のコネクタを設定する必要があります。 ユーザー メールボックスに送信されるメッセージ用のコネクタと、ユーザー メールボックスから送信されたメッセージ用のコネクタが必要です。 Office 365の Exchange 管理センターでこれらのコネクタを作成します。 手順については、「[Office 365のコネクタを使用してメール フローを構成する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」を参照してください。

## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Onlineの TLS 証明書情報

Exchange Onlineで使用される証明書情報を次の表に示します。 ビジネス パートナーがメール サーバーに強制的に TLS を設定している場合は、この情報をユーザーに提供する必要があります。 セキュリティ上の理由から、証明書は随時変更されます。 現在の証明書は、2020 年 9 月 24 日から有効です。

### <a name="current-certificate-information-valid-from-september-24-2020"></a>2020 年 9 月 24 日から有効な現在の証明書情報
  
| 属性 | 値 |
|:-----|:-----|
|証明機関のルート発行者|DigiCert CA - 1|
|証明書名|mail.protection.outlook.com|
|Organization|Microsoft Corporation|
|組織単位|www.digicert.com|
|証明書キーの強度|2048|

## <a name="get-more-information-about-tls-certificates-and-microsoft-365-and-download-certificates"></a>TLS、証明書、Microsoft 365 の詳細を取得し、証明書をダウンロードする

[Microsoft 365 暗号化チェーンと証明書のダウンロード](encryption-office-365-certificate-chains.md)

[Microsoft 365 暗号化チェーンと証明書のダウンロード - DOD と GCC High](encryption-office-365-certificate-chains-itar.md)

サポートされている暗号スイートの一覧については、 [暗号化に関するテクニカル リファレンスの詳細を参照してください](technical-reference-details-about-encryption.md)。
  
[パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[電子メール セキュリティを強化したコネクタ](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Microsoft 365 での暗号化](encryption.md)
