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
description: Exchange Online と Microsoft 365 がトランスポート層セキュリティ (TLS) と転送秘密 (FS) を使用して電子メール通信をセキュリティで保護する方法について説明します。 また、Microsoft for Exchange Online によって発行された証明書に関する情報も取得します。
ms.openlocfilehash: 67be87bc07399af9469728383af1caf604bf1372
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066830"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法

Exchange Online と Microsoft 365 がトランスポート層セキュリティ (TLS) と転送秘密 (FS) を使用して電子メール通信をセキュリティで保護する方法について説明します。 また、Microsoft for Exchange Online によって発行された証明書に関する情報も提供します。
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>Microsoft 365 および Exchange Online の TLS の基本

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。 TLS は SSL (Secure Sockets Layer)、SSL 3.1 と呼ばれることが多い。 Exchange Online では、TLS を使用して Exchange サーバー間の接続と、Exchange サーバーと、オンプレミスの Exchange サーバーや受信者のメール サーバーなどの他のサーバー間の接続を暗号化します。 接続が暗号化された後、その接続を介して送信されるデータはすべて、暗号化されたチャネル経由で送信されます。 ただし、TLS で暗号化された接続を介して送信されたメッセージを転送する場合、そのメッセージは必ずしも暗号化されません。 これは、簡単に言って、TLS はメッセージを暗号化しないので、接続だけだからです。
  
メッセージを暗号化する場合は、メッセージの内容を暗号化する暗号化テクノロジを使用する必要があります。たとえば、「メッセージの暗号化」Office使用します。 [Office 365](email-encryption.md)のメッセージ暗号化オプションの詳細については、「Office [365 および Office 365 Message Encryption (OME Office)](ome.md)での電子メールの暗号化」を参照してください。 
  
Microsoft とオンプレミス組織、またはパートナーなどの別の組織との間の通信のセキュリティで保護されたチャネルを設定する場合は、TLS を使用することをお勧めします。 Exchange Online は常に TLS を使用して電子メールをセキュリティ保護しますが、相手が TLS セキュリティを提供していない場合は常にこれを行う必要があります。 コネクタを使用して、オンプレミス サーバーまたは重要なパートナーへのすべてのメールをセキュリティで保護する方法については、次の記事を  *参照してください*。 

お客様にクラス最高の暗号化を提供するために、Microsoft は Office 365 および Office [365 GCC](tls-1-2-in-office-365-gcc.md)でトランスポート層セキュリティ (TLS) バージョン 1.0 および[1.1](tls-1.0-and-1.1-deprecation-for-office-365.md)を廃止しました。 ただし、TLS を使用せずに、暗号化されていない SMPT 接続を引き続き使用できます。 暗号化なしで電子メールを送信はお勧めしません。  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Exchange Online のお客様間での Exchange Online の TLS の使用

Exchange Online サーバーは、データセンター内の他の Exchange Online サーバーへの接続を TLS 1.2 で常に暗号化します。 組織内の受信者にメールを送信すると、その電子メールは TLS を使用して暗号化された接続を使用して自動的に送信されます。 また、他のユーザーに送信する電子メールはすべて、TLS を使用して暗号化された接続を使用して送信され、Forward Secrecy を使用してセキュリティ保護されます。
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Microsoft 365 が Microsoft 365 と外部の信頼できるパートナーとの間で TLS を使用する方法

既定では、Exchange Online は常に便利な TLS を使用します。 つまり、Exchange Online は常に最も安全なバージョンの TLS で接続を暗号化しようとしてから、両者が合意できる TLS 暗号を見つけるまで TLS 暗号の一覧を下に移動します。 Exchange Online を構成して、その受信者へのメッセージがセキュリティで保護された接続を通じてのみ送信される場合を限り、既定では、受信者組織が TLS 暗号化をサポートしない場合、メッセージは暗号化されません。 多くの企業では、見合い的な TLS で十分です。 ただし、医療組織、銀行組織、政府機関などのコンプライアンス要件を持つ企業の場合は、TLS を要求 (強制) する Exchange Online を構成できます。 手順については、「Office [365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)でコネクタを使用してメール フローを構成する」を参照してください。
  
組織と信頼できるパートナー組織の間で TLS を構成する場合、Exchange Online は強制的な TLS を使用して、信頼できる通信チャネルを作成できます。 TLS を強制するには、パートナー組織がメールを送信するためにセキュリティ証明書を使用して Exchange Online に認証する必要があります。 これを行うには、パートナーが独自の証明書を管理する必要があります。 Exchange Online では、受信者の電子メール プロバイダーに到着する前に未承認のアクセスから送信したメッセージを保護するためにコネクタを使用します。 コネクタを使用してメール フローを構成する方法については、「Configure [mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)」を参照してください。
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS およびハイブリッドExchange Server展開

ハイブリッド Exchange 展開を管理している場合、メールボックスが Office 365 内のみにある受信者にメールを送信するには、オンプレミスの Exchange サーバーがセキュリティ証明書を使用して Microsoft 365 に対して認証する必要があります。 その結果、オンプレミスの Exchange サーバー用に独自のセキュリティ証明書を管理する必要があります。 また、これらのサーバー証明書を安全に保存して維持する必要があります。 ハイブリッド展開での証明書の管理の詳細については、「ハイブリッド展開の証明書要件」 [を参照してください](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)。
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Office 365 で Exchange Online の強制 TLS を設定する方法

Exchange Online のお客様は、すべての送信および受信電子メールをセキュリティで保護するために TLS を強制的に動作するために、TLS を必要とする複数のコネクタを設定する必要があります。 ユーザー のメールボックスに送信される電子メールには 1 つのコネクタが必要です。もう 1 つのコネクタは、ユーザーのメールボックスから送信された電子メールに必要です。 これらのコネクタは、Office 365 の Exchange 管理センターで作成します。 手順については、「Office [365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)でコネクタを使用してメール フローを構成する」を参照してください。
  
## <a name="tls-certificate-information-for-exchange-online"></a>Exchange Online の TLS 証明書情報

Exchange Online で使用される証明書情報を次の表に示します。 ビジネス パートナーが電子メール サーバーに強制的に TLS を設定している場合は、そのパートナーにこの情報を提供する必要があります。 セキュリティ上の理由から、証明書は時に変わる点に注意してください。 データセンター内の証明書に対する更新プログラムを展開しました。 新しい証明書は、2018 年 9 月 3 日から有効です。
  
 **2018 年 9 月 3 日から有効な現在の証明書情報**
  
| 属性 | 値 |
|:-----|:-----|
|証明機関のルート発行者  <br/> |GlobalSign ルート CA – R1 <br/> |
|証明書名  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織単位  <br/> |  <br/> |
|証明書キーの強度  <br/> |2048  <br/> |
   
 **2018 年 9 月 3 日まで有効な非推奨の証明書情報**
  
スムーズな移行を実現するために、引き続き参照用の古い証明書情報を提供しますが、今後は現在の証明書情報を使用する必要があります。
  
****

| 属性 | 値 |
|:-----|:-----|
|証明機関のルート発行者  <br/> |Baltimore CyberTrust Root  <br/> |
|証明書名  <br/> |mail.protection.outlook.com  <br/> |
|組織  <br/> |Microsoft Corporation  <br/> |
|組織単位  <br/> |Microsoft Corporation  <br/> |
|証明書キーの強度  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>新しい Exchange Online 証明書の準備

新しい証明書は、Exchange Online で使用されている以前の証明書とは異なる証明機関 (CA) によって発行されます。 その結果、新しい証明書を使用するためにいくつかの操作を実行する必要がある場合があります。

新しい証明書では、証明書の検証の一環として、新しい CA のエンドポイントに接続する必要があります。 そうしない場合、メール フローに悪影響が及ぶ可能性があります。 メール サーバーが特定の宛先にのみ接続できるファイアウォールでメール サーバーを保護する場合は、サーバーが新しい証明書を検証できるのか確認する必要があります。 サーバーが新しい証明書を使用できると確認するには、次の手順を実行します。

1. 次のコマンドを使用Exchange Serverローカル Windows PowerShellに接続し、次のコマンドを実行します。  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. 表示されるウィンドウで、[取得] を **選択します**。

1. ユーティリティがチェックを完了すると、状態が返されます。 状態が **[OK]** と表示された場合、メール サーバーは新しい証明書を正常に検証できます。 失敗した場合は、接続が失敗する原因を特定する必要があります。 ほとんどの場合、ファイアウォールの設定を更新する必要があります。 アクセスする必要があるエンドポイントの完全な一覧は次のとおりです。
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

通常、ルート証明書の更新プログラムは Windows Update を通じて自動的に受信します。 ただし、一部の展開では、これらの更新プログラムが自動的に実行されるのを防ぐ追加のセキュリティが設定されています。 Windows Update がルート証明書を自動的に更新できないロックダウンされた展開では、次の手順を実行して、正しいルート CA 証明書がインストールされていることを確認する必要があります。
1.  次のコマンドを使用Exchange Serverローカル Windows PowerShellに接続し、次のコマンドを実行します。  
  `certmgr.msc`

2. [ **信頼されたルート証明機関/** 証明書] で、新しい証明書が一覧に表示されます。

## <a name="get-more-information-about-tls-and-microsoft-365"></a>TLS と Microsoft 365 の詳細を取得する

サポートされている暗号スイートの一覧については、暗号化に関する [テクニカル リファレンスの詳細を参照してください](technical-reference-details-about-encryption.md)。
  
[パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[電子メール セキュリティを強化したコネクタ](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Microsoft 365 での暗号化](encryption.md)
  

