---
title: メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: トランスポート層Exchange Onlineセキュリティ (TLS) Microsoft 365転送秘密 (FS) を使用して電子メール通信をセキュリティで保護する方法について学習します。 また、Microsoft によって発行された証明書に関する情報も取得Exchange Online。
ms.openlocfilehash: cc7ca631f9322fdc8a85cfaba197e63d06d08aee
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59175904"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法

トランスポート層Exchange Onlineセキュリティ (TLS) Microsoft 365転送秘密 (FS) を使用して電子メール通信をセキュリティで保護する方法について学習します。 また、Microsoft によって発行された証明書に関する情報も提供Exchange Online。
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>TLS の基本Microsoft 365およびExchange Online

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。 TLS は、Secure Sockets Layer (SSL) に取ってかわるもので、SSL 3.1 と呼ばれます。 Exchange Onlineでは、TLS を使用して、Exchange サーバー間の接続と、Exchange サーバーと、オンプレミスの Exchange サーバーや受信者のメール サーバーなどの他のサーバー間の接続を暗号化します。 接続が暗号化された後、その接続を介して送信されたデータはすべて、暗号化されたチャネルを介して送信されます。 ただし、TLS で暗号化された接続を介して送信されたメッセージを転送する場合、そのメッセージは必ずしも暗号化されません。 これは、簡単に言って、TLS はメッセージを暗号化しないので、接続だけだからです。
  
メッセージを暗号化する場合は、メッセージの内容を暗号化する暗号化テクノロジを使用する必要があります (たとえば、メッセージの暗号化Officeなど)。 メッセージ[暗号化オプションの詳細については、「Office 365](email-encryption.md)および Office 365 Message Encryption [(OME)](ome.md)での電子メールの暗号化」を参照Office 365。 
  
Microsoft とオンプレミス組織、またはパートナーなどの別の組織との間の通信のセキュリティで保護されたチャネルを設定する場合は、TLS を使用することをお勧めします。 Exchange Onlineは常に最初に TLS を使用してメールをセキュリティで保護しますが、相手が TLS セキュリティを提供していない場合は、常にこれを行う必要があります。 コネクタを使用して、オンプレミス サーバーまたは重要なパートナーに対してすべてのメールをセキュリティで保護する方法については、次の記事  *をご覧ください*。 

クラス最高の暗号化をお客様に提供するために、Microsoft は Office 365 および Office 365 GCC でトランスポート層セキュリティ (TLS) バージョン 1.0[](tls-1.0-and-1.1-deprecation-for-office-365.md)および 1.1[を非推奨にしました](tls-1-2-in-office-365-gcc.md)。 ただし、TLS なしで暗号化されていない SMTP 接続を引き続き使用できます。 暗号化なしで電子メールを送信することをお勧めしません。  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>ユーザー Exchange Online間で TLS をExchange Onlineする方法

Exchange Onlineサーバーは、TLS 1.2 を使用Exchange Onlineデータセンター内の他のサーバーへの接続を常に暗号化します。 組織内の受信者にメールを送信すると、そのメールは TLS を使用して暗号化された接続を使用して自動的に送信されます。 また、他の顧客に送信する電子メールはすべて、TLS を使用して暗号化され、Forward Secrecy を使用してセキュリティで保護された接続を使用して送信されます。
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>信頼Microsoft 365パートナーと外部のパートナー Microsoft 365 TLS を使用する方法

既定では、Exchange Onlineは常に日和見 TLS を使用します。 つまり、Exchange Online最も安全なバージョンの TLS との接続を常に暗号化し、その後、両方の当事者が同意できる TLS 暗号を見つけるまで、TLS 暗号の一覧を下に移動します。 Exchange Online を構成して、その受信者へのメッセージが安全な接続のみを介して送信される必要がない限り、既定では、受信者組織が TLS 暗号化をサポートしない場合、メッセージは暗号化されていない状態で送信されます。 ほとんどの企業では、日和見 TLS で十分です。 ただし、医療、銀行、政府機関などのコンプライアンス要件があるビジネスの場合は、TLS を要求または強制するExchange Onlineを構成できます。 手順については、「メール フローの構成」の「コネクタを使用してメール フローを[構成する」をOffice 365。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
  
組織と信頼できるパートナー組織の間で TLS を構成する場合は、Exchange Online TLS を使用して信頼できる通信チャネルを作成できます。 強制 TLS では、パートナー組織がメールを送信するためにExchange Online証明書を使用して認証を行う必要があります。 これを行うには、パートナーが独自の証明書を管理する必要があります。 このExchange Onlineコネクタを使用して、受信者の電子メール プロバイダーに到着する前に、承認されていないアクセスから送信するメッセージを保護します。 コネクタを使用してメール フローを構成する方法については、「Configure mail flow using connectors in Office 365」[を参照してください](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS およびハイブリッド Exchange Server展開

ハイブリッド Exchange 展開を管理している場合は、メールボックスが Office 365 内にしかない受信者にメールを送信するために、セキュリティ証明書を使用して、オンプレミスの Exchange サーバーが Microsoft 365 に対して認証する必要があります。 その結果、オンプレミスのサーバー用の独自のセキュリティ証明書を管理Exchangeがあります。 また、これらのサーバー証明書を安全に保存および保守する必要があります。 ハイブリッド展開での証明書の管理の詳細については、「ハイブリッド展開の [証明書要件」を参照してください](/exchange/certificate-requirements)。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>ユーザーのサーバーに強制的な TLS をExchange OnlineするOffice 365

ユーザー Exchange Online、送信および受信メールのセキュリティを確保するために TLS を強制的に動作するには、TLS を必要とする複数のコネクタをセットアップする必要があります。 ユーザー メールボックスに送信される電子メールには 1 つのコネクタ、ユーザー メールボックスから送信される電子メールには別のコネクタが必要です。 これらのコネクタは、Exchangeの管理センターにOffice 365。 手順については、「メール フローの構成」の「コネクタを使用してメール フローを[構成する」をOffice 365。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
  
## <a name="tls-certificate-information-for-exchange-online"></a>サーバーの TLS 証明書Exchange Online

次の表に、Exchange Onlineによって使用される証明書情報について説明します。 ビジネス パートナーがメール サーバーで強制 TLS を設定している場合は、この情報をユーザーに提供する必要があります。 セキュリティ上の理由から、証明書は変更される場合があります。 データセンター内で証明書の更新プログラムを展開しました。 新しい証明書は、2018 年 9 月 3 日から有効です。
  
 **2018 年 9 月 3 日から有効な現在の証明書情報**
  
| 属性 | 値 |
|:-----|:-----|
|証明機関のルート発行者  <br/> |GlobalSign ルート CA – R1 <br/> |
|証明書名  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織単位  <br/> |  <br/> |
|証明書キーの強さ  <br/> |2048  <br/> |
   
 **2018 年 9 月 3 日まで有効な非推奨の証明書情報**
  
スムーズな移行を実現するために、引き続き、参照用の古い証明書情報を提供しますが、今後は現在の証明書情報を使用する必要があります。
  
****

| 属性 | 値 |
|:-----|:-----|
|証明機関のルート発行者  <br/> |Baltimore CyberTrust Root  <br/> |
|証明書名  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織単位  <br/> |Microsoft Corporation  <br/> |
|証明書キーの強さ  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>新しい証明書のExchange Onlineする

新しい証明書は、認証機関が使用した以前の証明書とは異なる証明機関 (CA) によってExchange Online。 その結果、新しい証明書を使用するためにいくつかのアクションを実行する必要がある場合があります。

新しい証明書では、証明書の検証の一環として、新しい CA のエンドポイントに接続する必要があります。 そうしない場合、メール フローに悪影響が及ぶ可能性があります。 メール サーバーが特定の宛先に接続できるファイアウォールでメール サーバーを保護する場合は、サーバーが新しい証明書を検証できるのか確認する必要があります。 サーバーが新しい証明書を使用できると確認するには、次の手順を実行します。

1. Connectを使用してローカル Exchange ServerにWindows PowerShellし、次のコマンドを実行します。  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. 表示されるウィンドウで、[取得] を **選択します**。

1. ユーティリティがチェックを完了すると、状態が返されます。 状態が **[OK] と表示された** 場合、メール サーバーは新しい証明書を正常に検証できます。 接続が失敗する原因を特定する必要があります。 ほとんどの場合、ファイアウォールの設定を更新する必要があります。 アクセスする必要があるエンドポイントの完全な一覧は次のとおりです。
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

通常、ルート証明書の更新プログラムは、[更新] を使用して自動的Windows受け取ります。 ただし、一部の展開ではセキュリティが強化され、これらの更新プログラムが自動的に発生しなくなります。 Windows Update でルート証明書を自動的に更新できないこれらのロックダウン展開では、次の手順を実行して、正しいルート CA 証明書がインストールされていることを確認する必要があります。
1.  Connectを使用してローカル Exchange ServerにWindows PowerShellし、次のコマンドを実行します。  
  `certmgr.msc`

2. [ **信頼されたルート証明機関/証明書] で**、新しい証明書が一覧に表示されます。

## <a name="get-more-information-about-tls-and-microsoft-365"></a>TLS と TLS の詳細については、Microsoft 365

サポートされている暗号スイートの一覧については、「暗号化に関する [テクニカル リファレンスの詳細」を参照してください](technical-reference-details-about-encryption.md)。
  
[パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)
  
[電子メール セキュリティを強化したコネクタ](/previous-versions/exchange-server/exchange-150/dn942516(v=exchg.150))
  
[Microsoft 365 での暗号化](encryption.md)
