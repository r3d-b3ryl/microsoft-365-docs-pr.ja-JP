---
title: 暗号化についてのテクニカル リファレンスの詳細
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Office 365 および Microsoft 365 の暗号化に使用されるさまざまな証明書、テクノロジ、およびトランスポート層セキュリティ (TLS) 暗号スイートについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919353"
---
# <a name="technical-reference-details-about-encryption"></a>暗号化についてのテクニカル リファレンスの詳細

この記事を参照して [、365](encryption.md)の暗号化に使用される証明書、テクノロジ、および TLS 暗号スイートOfficeしてください。 この記事では、計画された廃止に関する詳細も説明します。
  
- 概要情報をお探しの場合は、「[暗号化」を参照Office 365 .](encryption.md)
- セットアップ情報を探している場合は [、「Set up encryption in Office 365 Enterprise 」を参照してください](set-up-encryption.md)。
- 特定のバージョンの Windows でサポートされる暗号スイートの詳細については [、「Cipher Suites in TLS/SSL (Schannel SSP)」を参照してください](/windows/desktop/SecAuthN/cipher-suites-in-schannel)。

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 証明書の所有権と管理

365 の証明書を購入または保守する必要Office。 代わりに、Office 365 は独自の証明書を使用します。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>現在の暗号化標準と予定されている非推奨

クラス最高の暗号化を提供するために、365 Officeサポートされている暗号化標準を定期的に確認します。 古い標準は古く、安全性が低くなると廃止される場合があります。 この記事では、現在サポートされている暗号スイート、その他の標準、および計画された廃止に関する詳細について説明します。

## <a name="fips-compliance-for-office-365"></a>FIPS コンプライアンス Office 365

FIPS 140-2 でOffice 365 でサポートされる暗号スイートはすべて、アルゴリズムを使用します。 Office 365 は Windows (Schannel 経由) から FIPS 検証を継承します。 Schannel の詳細については [、「TLS/SSL の暗号スイート (Schannel SSP)」を参照してください](/windows/desktop/SecAuthN/cipher-suites-in-schannel)。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 でサポートされる TLS のバージョン

TLS、および TLS より前の SSL は、セキュリティ証明書を使用してコンピューター間の接続を暗号化することでネットワーク上の通信をセキュリティで保護する暗号化プロトコルです。 Office 365 は TLS バージョン 1.2 (TLS 1.2) をサポートしています。

TLS バージョン 1.3 (TLS 1.3) は現在サポートされていません。
  
## <a name="support-for-tls-10-and-11-deprecation"></a>TLS 1.0 および 1.1 の非推奨のサポート

Office 365 は、2018 年 10 月 31 日に TLS 1.0 および 1.1 のサポートを停止しました。 GCC High および DoD 環境での TLS 1.0 と 1.1 の無効化が完了しました。 2020 年 10 月 15 日からワールドワイド環境および GCC 環境で TLS 1.0 および 1.1 を無効にし始め、今後数週間から数か月の間、ロールアウトを続行します。

Office 365 および Microsoft 365 サービスへの安全な接続を維持するために、すべてのクライアント サーバーとブラウザー サーバーの組み合わせで TLS 1.2 と最新の暗号スイートを使用します。 クライアントとサーバー間、ブラウザーとサーバー間の特定の組み合わせについては、更新が必要になる場合があります。 この変更がユーザーに与える影響の詳細については [、「365 の TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)の必須使用の準備」を参照Officeしてください。
  
## <a name="deprecating-support-for-3des"></a>3DES のサポートの廃止

2018 年 10 月 31 日以降、Office 365 は 3DES 暗号スイートを 365 から 365 への通信に使用Officeなくなりました。 具体的には、Office 365 は暗号化スイートTLS_RSA_WITH_3DES_EDE_CBC_SHAサポートしなくなりました。 2019 年 2 月 28 日以降、この暗号スイートは 365 でOfficeされています。 クライアントと 365 と通信するOfficeは、サポートされている 1 つ以上の暗号をサポートする必要があります。 サポートされている暗号の一覧については [、「365](#tls-cipher-suites-supported-by-office-365)でサポートされる TLS 暗号スイートOffice参照してください。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Office 365 における SHA-1 証明書サポートの廃止

2016 年 6 月以降、Office 365 は送信接続または受信接続の SHA-1 証明書を受け入れなくなりました。 証明書チェーンで SHA-2 (Secure Hash Algorithm 2) またはより強力なハッシュ アルゴリズムを使用します。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>TLS 暗号スイートは、Office 365 でサポートされています

TLS では、 *暗号化アルゴリズムの* コレクションである暗号スイートを使用して、セキュリティで保護された接続を確立します。 Office 365 は、次の表に示す暗号スイートをサポートしています。 次の表に、最も強力な暗号スイートを最初に示す、強度の順に暗号スイートの一覧を示します。

Office 365 は、最初に最も安全な暗号スイートを使用して接続を試み、接続要求に応答します。 接続が機能しない場合、Office 365 はリスト内で 2 番目に安全な暗号スイートを試行します。 サービスは、接続が受け入れられるまでリストの下に続きます。 同様に、Office 365 が接続を要求すると、受信側サービスは TLS を使用するかどうか、使用する暗号スイートを選択します。

> [!IMPORTANT]
> TLS バージョンは非推奨であり、新しいバージョンが利用可能な場合は非推奨のバージョンを使用しなくな点に注意してください。 TLS 1.3 は現在サポートされていません。 従来のサービスで TLS 1.0 または 1.1 が必要ない場合は、それらを無効にする必要があります。

| 暗号スイート | キー交換アルゴリズム/強さ | Forward Secrecy | 暗号/強度 | 認証アルゴリズム |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|はい <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|はい <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|はい <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|はい <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|はい <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|はい <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |いいえ <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |いいえ <br/> |AES/256 <br/>|RSA/112 <br/> |

これらの暗号スイートは、廃止日まで TLS 1.0 および 1.1 プロトコルをサポートしました。 非推奨日が 2020 年 1 月 15 日の GCC High 環境と DoD 環境、およびワールドワイド環境と GCC 環境の場合、その日付は 2020 年 10 月 15 日でした。

| プロトコル | 暗号スイート名 | キー交換アルゴリズム/強さ | 前方秘密のサポート | 認証アルゴリズム/強度 | 暗号/強度 |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |はい  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |はい  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |いいえ  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |いいえ  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |いいえ   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |いいえ   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>関連記事

[Windows 10 v1903 の TLS 暗号スイート](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Office 365 での暗号化](encryption.md)
  
[Office 365 Enterprise で暗号化を設定する](set-up-encryption.md)
  
[Windows セキュリティ状態更新プログラムでの TLS 1.0 の Schannel 実装: 2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 暗号化拡張機能 (Windows IT センター)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Office 365 および Office 365 GCC での TLS 1.2 の準備](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)