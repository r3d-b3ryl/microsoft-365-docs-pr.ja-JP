---
title: Microsoft 365 のサードパーティの SSL 証明書の計画
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: '概要: オンプレミスとハイブリッドのExchange、AD FS を使用した SSO、Exchange Online サービス、Exchange Web サービスに必要な SSL 証明書について説明します。'
ms.openlocfilehash: 0cd7cce2cd5f0aba8baecab7048d86d629d30427
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100305"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Microsoft 365 のサードパーティの SSL 証明書の計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

クライアントとMicrosoft 365環境間の通信を暗号化するには、サード パーティの Secure Socket Layer (SSL) 証明書をインフラストラクチャ サーバーにインストールする必要があります。

この記事は、[Microsoft 365のネットワーク計画とパフォーマンスのチューニングの](./network-planning-and-performance.md)一部です。
   
証明書は、次のMicrosoft 365 コンポーネントに必要です。
  
- オンプレミスの Exchange
    
- シングル サインオン (SSO) (Active Directory フェデレーション サービス (AD FS) (AD FS) フェデレーション サーバーと AD FS フェデレーション サーバー プロキシの両方)
    
- 自動検出、Outlook Anywhere、Exchange Web サービスなどのExchange Online サービス
    
- ハイブリッド サーバー Exchange
    
## <a name="certificates-for-exchange-on-premises"></a>Exchange オンプレミスの証明書

デジタル証明書を使用して、オンプレミスのExchange組織とExchange Onlineの間の通信をセキュリティで保護する方法の概要については、TechNet の記事「[証明書の要件について](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141))」を参照してください。
  
## <a name="certificates-for-single-sign-on"></a>シングル サインオンの証明書

堅牢なセキュリティを含むシンプルなシングル サインオン エクスペリエンスをユーザーに提供するために、次の表に示す証明書は、フェデレーション サーバーまたはフェデレーション サーバー プロキシのいずれかで必要です。 次の表では、Active Directory フェデレーション サービス (AD FS) (AD FS) に重点を置いています。[また、サード パーティの ID プロバイダーの使用](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)に関する詳細についても説明します。
  
| 証明書の種類 | 説明 | デプロイする前に知っておくべきこと |
|:-----|:-----|:-----|
|**SSL 証明書 (サーバー認証証明書とも呼ばれます)** <br/> |これは、フェデレーション サーバー、クライアント、およびフェデレーション サーバー プロキシ コンピューター間の通信をセキュリティで保護するために使用される標準 SSL 証明書です。  <br/> |AD FS には SSL 証明書が必要です。 既定では、AD FS では、インターネット インフォメーション サービス (IIS) の既定の Web サイト用に構成された SSL 証明書が使用されます。  <br/> この SSL 証明書のサブジェクト名は、展開する AD FS の各インスタンスのフェデレーション サービス (FS) 名を決定するために使用されます。 Microsoft 365する会社または組織の名前を最もよく表す、新しい証明機関 (CA) で発行された証明書のサブジェクト名を選択することを検討してください。 この名前は、インターネットルーティング可能である必要があります。  <br/>**注意：** AD FS では、この SSL 証明書にドットレス (短い名前) のサブジェクト名が含まれていないことが必要です。          <br/> **推薦：** この証明書は AD FS のクライアントによって信頼される必要があるため、パブリック (サード パーティ) CA またはパブリックに信頼されたルートに従属する CA によって発行された SSL 証明書を使用することをお勧めします。たとえば、VeriSign や Thawte などです。  <br/> |
|**トークン署名証明書** <br/> |これは、フェデレーション サーバーが発行するすべてのトークンを安全に署名するために使用され、Microsoft 365が受け入れて検証するために使用される標準の X.509 証明書です。  <br/> |トークン署名証明書には、FS の信頼されたルートにチェーンする秘密キーが含まれている必要があります。 既定では、AD FS は自己署名証明書を作成します。 ただし、組織のニーズに応じて、AD FS 管理スナップインを使用して、この証明書を CA 発行の証明書に変更できます。  <br/>**注意：** トークン署名証明書は、FS の安定性にとって重要です。 証明書が変更された場合は、Microsoft 365に変更を通知する必要があります。 通知が提供されない場合、ユーザーはMicrosoft 365サービスオファリングにサインインできません。<br/>**推薦：** AD FS によって生成される自己署名証明書を使用することをお勧めします。 これにより、この証明書が既定で管理されます。 たとえば、この証明書の有効期限が切れそうになると、AD FS によって新しい自己署名証明書が生成されます。  <br/> |
   
フェデレーション サーバー プロキシには、次の表に示す証明書が必要です。
  
| 証明書の種類 | 説明 | デプロイする前に知っておくべきこと |
|:-----|:-----|:-----|
|SSL 証明書  <br/> |これは、フェデレーション サーバー、フェデレーション サーバー プロキシ、インターネット クライアント コンピューター間の通信をセキュリティで保護するために使用される標準 SSL 証明書です。  <br/> |AD FS フェデレーション サーバー プロキシ構成ウィザードを正常に実行するには、この SSL 証明書を IIS の既定の Web サイトにバインドする必要があります。  <br/> この証明書には、企業ネットワーク内のフェデレーション サーバーで構成された SSL 証明書と同じサブジェクト名が必要です。  <br/> **推薦：** このフェデレーション サーバー プロキシが接続するフェデレーション サーバーで構成されているのと同じサーバー認証証明書を使用することをお勧めします。  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>自動検出、Outlook Anywhere、Active Directory 同期の証明書

外部向けExchange 2013、Exchange 2010、Exchange 2007、Exchange 2003 クライアント アクセス サーバー (CAS) では、自動検出、Outlook Anywhere、Active Directory 同期サービス用のセキュリティで保護された接続にサードパーティの SSL 証明書が必要です。 オンプレミス環境にこの証明書が既にインストールされている可能性があります。
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Exchange ハイブリッド サーバーの証明書

外部向けExchangeハイブリッド サーバーまたはサーバーには、Exchange Online サービスとの安全な接続のためにサードパーティの SSL 証明書が必要です。 この証明書は、サード パーティの SSL プロバイダーから取得する必要があります。
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365証明書チェーン

この記事では、インフラストラクチャにインストールするために必要な証明書について説明します。 Microsoft 365 サーバーにインストールされている証明書の詳細については、「[Microsoft 365証明書チェーン](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)