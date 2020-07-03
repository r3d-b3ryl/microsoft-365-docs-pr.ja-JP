---
title: 暗号化に関するテクニカルリファレンスの詳細
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 06/15/2020
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Office 365 で暗号化に使用されるさまざまな証明書、テクノロジ、および TLS 暗号スイートについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91fa21fff12c429032af6468ff3024acfc6ca2ab
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024543"
---
# <a name="technical-reference-details-about-encryption"></a>暗号化に関するテクニカルリファレンスの詳細

この記事では、 [Office 365 の暗号化](encryption.md)に使用される証明書、テクノロジ、および TLS 暗号スイートについて説明します。 この記事では、計画した deprecations の詳細についても説明します。
  
- 概要情報を探している場合は、「 [Encryption In Office 365](encryption.md)」を参照してください。
- セットアップ情報を探している場合は、「 [Office 365 Enterprise で暗号化を設定](set-up-encryption.md)する」を参照してください。
- 特定のバージョンの Windows でサポートされている暗号スイートの詳細については、「 [TLS/SSL (SCHANNEL SSP)」の「Cipher suite](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)」を参照してください。

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 証明書の所有権と管理

Microsoft は独自の証明書を使用するため、お客様が Office 365 用の証明書を購入したり保持したりする必要はありません。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>現在の暗号化標準と予定されている deprecations

Office 365 のクラス最高の暗号化を引き続き提供するために、Microsoft は、サポートされている暗号化基準を定期的にレビューします。 古い標準は古くなっており、セキュリティが低いため、廃止する必要があります。 このトピックでは、現在サポートされている暗号スイートとその他の標準、および計画した deprecations に関する詳細について説明します。 

## <a name="fips-compliance-for-office-365"></a>Office 365 の FIPS コンプライアンス

Office 365 でサポートされているすべての暗号スイートは、FIPS 140-2 で使用可能なアルゴリズムを使用します。 Office 365 は、Windows (Schannel 経由) から FIPS 検証を継承します。 Schannel の詳細については、「 [TLS/SSL (SCHANNEL SSP)」の「Cipher suite](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)」を参照してください。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 でサポートされる TLS のバージョン

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。 Office 365 は TLS バージョン 1.2 (TLS 1.2) をサポートしています。

TLS バージョン 1.3 (TLS 1.3) は現在サポートされていません。
  
## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>TLS 1.0 および1.1 のサポートが廃止され、これが何を意味するのかを説明します。

2018年10月31日以降、Office 365 は TLS 1.0 および1.1 をサポートしなくなりました。 これは、Microsoft が、TLS 1.0 および1.1 を使用して Office 365 に接続するクライアント、デバイス、またはサービスに関する新しい問題を修正しないことを意味します。

これは、Office 365 が TLS 1.0 および1.1 の接続をブロックすることを意味するわけではありません。

最初は、2020年6月1日の日付を設定していますが、世界規模および GCC 環境ではの TLS 1.0 および TLS 1.1 は廃止されていますが、この日付は無効になりました。 これは COVID-19 のためです。 この廃止予定に新しい日付がある場合は、ここで公開します。 

GCC High および DoD 環境では、2020年1月15日に公式の廃止が行われました。

すべてのクライアントサーバーとブラウザーのサーバーの組み合わせが TLS 1.2 と最新の暗号スイートを使用して、Office 365 および Microsoft 365 サービスへのセキュリティで保護された接続を維持するようにする必要があります。 クライアントとサーバー間、ブラウザーとサーバー間の特定の組み合わせについては、更新が必要になる場合があります。 この影響の詳細については、「 [Office 365 での TLS 1.2 の必須使用の準備](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)」を参照してください。
  
## <a name="deprecating-support-for-3des"></a>3DES の廃止サポート

2018年10月31日以降、Office 365 は office 365 への通信に3DES 暗号化スイートの使用をサポートしなくなりました。 具体的には、Office 365 は TLS_RSA_WITH_3DES_EDE_CBC_SHA 暗号スイートをサポートしなくなりました。 2019年2月28日以降、この暗号スイートは Office 365 で無効になっています。 この日付の後に Office 365 と通信するクライアントおよびサーバーは、このトピックに記載されている、より安全な暗号の少なくとも1つをサポートする必要があります (「 [Office 365 でサポートされている TLS 暗号スイート](#tls-cipher-suites-supported-by-office-365)」を参照してください)。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 における SHA-1 証明書サポートの廃止

2016年6月の時点で、Office 365 は、送信接続または受信接続に対して SHA-1 証明書を受け入れなくなりました。 現在、証明書チェーンの SHA-1 で証明書を使用している場合は、SHA-1 (Secure Hash Algorithm 2) またはより強力なハッシュアルゴリズムを使用するようにチェーンを更新する必要があります。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 でサポートされている TLS 暗号スイート

Cipher suite は、セキュリティで保護された接続を確立するために TLS が使用する暗号化アルゴリズムの集合です。 Office 365 でサポートされている暗号スイートについては、次の表に、最強の暗号スイートを最初に示しています。 Office 365 が接続要求を受信すると、Office 365 は最初に最上位の暗号スイートを使用して接続しようとします。 成功しなかった場合、Office 365 は、リスト内の2番目の暗号スイートを、リストの下に試行します。 Office 365 が別のサーバーまたはクライアントに接続要求を送信する場合は、受信側のサーバーまたはクライアントが暗号スイートを選択するか、TLS を使用するかを選択します。

> [!IMPORTANT]
> TLS のバージョンが廃止され、使用され*なく*なったバージョンを使用して新しいバージョンを入手できないことに注意してください。 TLS 1.3 は現在サポートされていません。 従来のサービスが TLS 1.0 または1.1 を必要としない場合は、それらを無効にする必要があります。
  
|**プロトコル**|**暗号スイート名**|**キー交換アルゴリズム/強度**|**完全なフォワード機密サポート**|**認証アルゴリズム/強度**|**暗号/強度**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |いいえ  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>関連トピック
[Windows 10 v1903 の TLS 暗号スイート](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 での暗号化](encryption.md)
  
[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md)
  
[Windows セキュリティ状態更新プログラムでの TLS 1.0 の Schannel 実装:11 月24日、2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 暗号化の強化 (Windows IT センター)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
 [Office 365 および Office 365 GCC での TLS 1.2 の準備](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

