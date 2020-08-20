---
title: 暗号化についてのテクニカル リファレンスの詳細
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
description: Office 365 での暗号化に使用されるさまざまな証明書、テクノロジ、TLS 暗号化スイートOffice説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e4b2923d2b250e85efa7fdc50a995db397d670
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814369"
---
# <a name="technical-reference-details-about-encryption"></a>暗号化についてのテクニカル リファレンスの詳細

Office 365 での暗号化に使用される証明書、テクノロジ、および TLS シピート [については、この記事を参照してください](encryption.md)。 この記事では、計画された廃止に関する詳細も取り上が示されています。
  
- 概要については、「Office [365 での暗号化」を参照してください](encryption.md)。
- セットアップ情報を検索するには [、「Office 365 Enterprise で暗号化のセットアップ」を参照してください](set-up-encryption.md)。
- 特定のバージョンの Windows でサポートされている周辺機関の詳細については [、「TLS/SSL (Schannel SSP)」の Cipher Suite を参照してください](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 証明書の所有権と管理

Microsoft は独自の証明書を使用するため、お客様が Office 365 用の証明書を購入したり保持したりする必要はありません。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>現在の暗号化標準と計画された廃止

Microsoft では、Microsoft 365 に向けなけら、クラス最高の暗号化をOffice維持するために、サポートされる暗号化の基準を定期的に確認します。 場合によっては、古い標準が古いとら安全性が低下するときに非推奨とする必要があります。 このトピックでは、現在サポートされている暗号化スイートやその他の基準と、計画されている廃止に関する詳細について説明します。 

## <a name="fips-compliance-for-office-365"></a>Office 365 Office FIPS コンプライアンス

FIPS 140-2 で Office 365 使用アルゴリズムでサポートされているすべてのシピッダー スイート。 Office 365 は Windows から (Schannel 経由で) FIPS 検証を継承します。 Schannel の詳細については [、「TLS/SSL (Schannel SSP)」の Cipher Suites を参照してください](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 でサポートされる TLS のバージョン

トランスポート層セキュリティ (TLS) と、TLS に先立つ SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することによって、ネットワークを介した通信のセキュリティを確保する暗号化プロトコルです。 Office 365 は TLS バージョン 1.2 (TLS 1.2) をサポートします。

TLS バージョン 1.3 (TLS 1.3) は現在サポートされていません。
  
## <a name="support-for-tls-10-and-11-deprecation-and-what-this-means-for-you"></a>TLS 1.0 および 1.1 の推奨要件とその意味

2018 年 10 月 31 日以降、Office 365 は TLS 1.0 および 1.1 をサポートしなくなりしています。 つまり、Microsoft は TLS 1.0 および 1.1 を使用して Office 365 に接続するサービスで見つかった新しい問題を解決しません。 GCC High および DoD 環境は 2020 年 1 月 15 日に開始された非正規廃止。 ワールドワイドおよび GCC 環境向けの TLS 1.0 および 1.1 の非推奨と、GCC 環境は 2020 年 10 月 15 日から開始されます。 

クライアント サーバーとブラウザー サーバーを組み合わせたすべてで、必ず TLS 1.2 と最新のシンプル シートを使用し、Office 365 および Microsoft 365 サービスへのセキュリティで保護された接続を維持する必要があります。 クライアントとサーバー間、ブラウザーとサーバー間の特定の組み合わせについては、更新が必要になる場合があります。 この影響の影響については [、「Office 365 での TLS 1.2 の必須使用に関する準備Officeを参照してください](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。
  
## <a name="deprecating-support-for-3des"></a>3DES のサポートの廃止

2018 年 10 月 31 日以降、Office 365 は、Office 365 への通信で 3DES の暗号化スイートを使用する操作をサポートしなくなりしています。 具体的には、365 OfficeスイートはサポートTLS_RSA_WITH_3DES_EDE_CBC_SHA提供しなけたときです。 2019 年 2 月 28 日以降、このシンボルは 2019 年 2 月 28 日以降、Office 365 で無効になっています。 この日付の後、Office 365 と通信するクライアントとサーバーは、このトピックに記載されているより安全なページ (Office 365 でサポートされている TLS 暗号化スイ [ートを参照) を少なくとも 1 つサポートしている必要があります](#tls-cipher-suites-supported-by-office-365)。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 における SHA-1 証明書サポートの廃止

2016 年 6 Office 365 では、送信接続または受信接続の SHA-1 証明書が受け入れられなくなりません。 現在、証明書チェーンで SHA-1 を含む証明書を使用している場合は、SHA-2 (セキュア ハッシュ アルゴリズム 2) またはさらに強力なハッシュ アルゴリズムを使用するには、チェーンを更新する必要があります。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 でサポートされている TLS Office イランダイサー

暗号化スイートは、TLS がセキュリティで保護された接続を確立するために使用する暗号化アルゴリズムのコレクションです。 次の表は、Office 365 でサポートされているシンクロッパー スイートを、最も強力なチェーンの順に記載しています。 365 Officeが接続要求を受信すると、Office 365 は最初に一番上のシリッパー スイートを使用して接続を試行します。 次に、処理が成功した場合Office 365 がリスト内の 2 番目のシンクリッパー スイートを試行し、リストを下に移動します。 Office 365 が別のサーバーまたはクライアントに接続要求を送信すると、受信側サーバーまたはクライアントが Cipher Suite または TLS を使用するかどうか。

> [!IMPORTANT]
> TLS バージョンは非推奨になり、新しいバージョンが使用可能な場合にはそのバージョンを使用*should not be used*しないことを確認してください。 TLS 1.3 は現在サポートされていません。 従来のサービスで TLS 1.0 または 1.1 を必要としない場合は、それらを無効にする必要があります。

| シンハードスイート | キー交換アルゴリズム/強度 | 完全な転送の秒数 | シンフア/強度 | 認証アルゴリズム |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|はい <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|はい <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|はい <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|はい <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|はい <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|はい <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |いいえ <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |いいえ <br/> |AES/256 <br/>|RSA/112 <br/> |

次のシリアルは、TLS 1.0 プロトコルと 1.1 プロトコルを廃止まで続けたものです。 非推奨の GCC High および DoD 環境で、2020 年 1 月 15 日で、国際環境および GCC 環境で、この日付が 2020 年 10 月 15 日の GCC 環境の場合。

| プロトコル | 暗号スイート名 | キー交換アルゴリズム/強度ンガ | 完全な転送のセキュリティのサポート | 認証アルゴリズム/強度 | シンピア/強度 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |いいえ  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |いいえ  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |いいえ   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |いいえ   <br/> |RSA/112  <br/> |AES/256  <br/> |
   
## <a name="related-topics"></a>関連トピック
[Windows 10 v1903 の TLS Cipher Suites](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 での暗号化](encryption.md)
  
[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md)
  
[Windows での TLS 1.0 の Schannel 実装: 2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 暗号化機能 (Windows IT センター)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Office 365 および Office 365 GCC での TLS 1.2 の準備](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
