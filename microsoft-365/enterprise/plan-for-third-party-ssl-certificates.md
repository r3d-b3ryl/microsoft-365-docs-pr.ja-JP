---
title: Microsoft 365 のサードパーティの SSL 証明書の計画
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: '概要: Exchange オンプレミスおよびハイブリッド、AD FS、Exchange Online サービス、および Exchange Web サービスを使用する SSO に必要な SSL 証明書について説明します。'
ms.openlocfilehash: f2ad14bd35d68067cdc462706bed763e894455f8
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58355930"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Microsoft 365 のサードパーティの SSL 証明書の計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

クライアントとサーバー環境間の通信を暗号化Microsoft 365、サード パーティ製の Secure Socket Layer (SSL) 証明書をインフラストラクチャ サーバーにインストールする必要があります。

この記事は、ネットワークの計画[とパフォーマンスの調整の一](./network-planning-and-performance.md)部Microsoft 365。
   
証明書は、次のコンポーネントにMicrosoft 365です。
  
- オンプレミスの Exchange
    
- シングル サインオン (SSO) (Active Directory フェデレーション サービス (AD FS) フェデレーション サーバーと FS フェデレーション サーバー プロキシAD両方)
    
- Exchange Online、自動検出、Anywhere、Outlook Web サービスなどのExchangeサービス
    
- Exchangeハイブリッド サーバー
    
## <a name="certificates-for-exchange-on-premises"></a>オンプレミスExchange証明書

デジタル証明書を使用して、オンプレミスの Exchange 組織と Exchange Online の間の通信をセキュリティで保護する方法の概要については、「TechNet の記事 証明書の要件について」を参照[してください](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141))。
  
## <a name="certificates-for-single-sign-on"></a>シングル サインオンの証明書

堅牢なセキュリティを含む簡単なシングル サインオン エクスペリエンスをユーザーに提供するには、フェデレーション サーバーまたはフェデレーション サーバー プロキシで次の表に示す証明書が必要です。 次の表では、Active Directory フェデレーション サービス (AD FS) に焦点を当て、サードパーティ ID プロバイダーの使用に関する詳細 [も説明します](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)。
  
| 証明書の種類 | 説明 | 展開する前に知る必要がある情報 |
|:-----|:-----|:-----|
|**SSL 証明書 (サーバー認証証明書とも呼ばれる)** <br/> |これは、フェデレーション サーバー、クライアント、およびフェデレーション サーバー プロキシ コンピューター間の通信をセキュリティで保護するために使用される標準的な SSL 証明書です。  <br/> |AD FS には SSL 証明書が必要です。 既定では、AD FS は、既定の Web サイト (IIS) 用に構成された SSL 証明書インターネット インフォメーション サービス使用します。  <br/> この SSL 証明書のサブジェクト名は、展開する FS の各インスタンスのフェデレーション サービス (FS) ADに使用されます。 組織または組織の名前を最も適切に表す、新しい証明機関 (CA) が発行した証明書のサブジェクト名を選択Microsoft 365。 この名前は、Internet-routable である必要があります。  <br/>**注意:** AD FS では、この SSL 証明書にドットレス (短い名前) のサブジェクト名が必要です。          <br/> **推奨事項:** この証明書は AD FS のクライアントによって信頼されている必要があります。たとえば、VeriSign または Thawte などです。  <br/> |
|**トークン署名証明書** <br/> |これは標準の X.509 証明書で、フェデレーション サーバーが発行するトークンと、フェデレーション サーバーが受け入れて検証するMicrosoft 365署名するために使用されます。  <br/> |トークン署名証明書には、FS の信頼されたルートにチェーンするプライベート キーが含まれている必要があります。 既定では、AD FS は自己署名証明書を作成します。 ただし、組織のニーズに応じて、この証明書を CA 発行の証明書に変更するには、AD FS 管理スナップインを使用します。  <br/>**注意:** トークン署名証明書は、FS の安定性にとって重要です。 証明書が変更された場合は、Microsoft 365の通知を受け取る必要があります。 通知が提供されていない場合、ユーザーは自分のサービスサービスにMicrosoft 365できます。<br/>**推奨事項:** FS によって生成される自己署名証明書を使用することをおADします。 これにより、既定でこの証明書が管理されます。 たとえば、この証明書の有効期限が近い場合、AD FS は新しい自己署名証明書を生成します。  <br/> |
   
フェデレーション サーバー プロキシには、次の表に示す証明書が必要です。
  
| 証明書の種類 | 説明 | 展開する前に知る必要がある情報 |
|:-----|:-----|:-----|
|SSL 証明書  <br/> |これは、フェデレーション サーバー、フェデレーション サーバー プロキシ、およびインターネット クライアント コンピューター間の通信をセキュリティで保護するために使用される標準的な SSL 証明書です。  <br/> |FS フェデレーション サーバー プロキシ構成ウィザードを正常に実行するには、この SSL 証明書を IIS の既定の web ADバインドする必要があります。  <br/> この証明書には、企業ネットワーク内のフェデレーション サーバーで構成された SSL 証明書と同じサブジェクト名が必要です。  <br/> **推奨事項:** このフェデレーション サーバー プロキシが接続するフェデレーション サーバーで構成されているのと同じサーバー認証証明書を使用することをお勧めします。  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>自動検出、任意の場所Outlook Active Directory 同期の証明書

外部向け Exchange 2013、Exchange 2010、Exchange 2007、および Exchange 2003 クライアント アクセス サーバー (CAS) には、自動検出、Outlook Anywhere、Active Directory 同期サービス用のセキュリティで保護された接続用のサードパーティ SSL 証明書が必要です。 この証明書は、オンプレミス環境に既にインストールされている可能性があります。
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>ハイブリッド サーバー Exchange証明書

ハイブリッド サーバーまたはサーバー Exchange外部に接続する場合は、サードパーティの SSL 証明書が必要で、セキュリティで保護された接続Exchange Onlineされます。 この証明書は、サード パーティの SSL プロバイダーから取得する必要があります。
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365証明書チェーン

この記事では、インフラストラクチャにインストールする必要がある可能性がある証明書について説明します。 サーバーにインストールされている証明書の詳細については、「Microsoft 365証明書チェーン[Microsoft 365参照してください](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb)。
  
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)