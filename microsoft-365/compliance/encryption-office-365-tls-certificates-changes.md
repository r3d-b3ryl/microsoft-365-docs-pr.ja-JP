---
title: Office TLS 証明書の変更
description: TLS 証明書に対する今後の変更にOfficeする方法。
author: pshelton-skype
ms.author: pshelton
manager: toddbeckett
ms.topic: article
audience: Developer
ms.date: 3/7/2022
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.openlocfilehash: 075fb8f4c27401a4622f4ce639c897f2e98bb3e9
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2022
ms.locfileid: "63450371"
---
# <a name="office-tls-certificate-changes"></a>Office TLS 証明書の変更

Microsoft 365メッセージング、会議、テレフォニー、音声、ビデオに電力を供給するサービスを更新し、異なるルート証明機関 (CA) の TLS 証明書を使用します。 この変更は、現在のルート CA が 2025 年 5 月に期限切れになるので行います。

影響を受ける製品は次のとおりです。
- Microsoft Teams
- Skype
- Skype for Business Online
- Microsoft Dynamics 365
- GroupMe
- Kaizala
- Azure コミュニケーション サービス

影響を受けるエンドポイントには、次のものが含まれます (ただし、これらに限定されません)。
- *.teams.microsoft.com
- *.skype.com
- *.skypeforbusiness.com
- *.groupme.com
- *.communication.azure.com
- *.operatorconnect.microsoft.com

さらに、Teams Skype for Businessの米国政府機関の国内クラウド インスタンスのオンライン エンドポイントと Microsoft 365 エンドポイントは同じ変更を行い、次のようなエンドポイントに影響を与える可能性があります。
- *.gcc.teams.microsoft.com
- *.dod.teams.microsoft.us
- *.gov.teams.microsoft.us
- *.online.dod.skypeforbusiness.us
- *.online.gov.skypeforbusiness.us
- *.um-dod.office365.us
- *.um.office365.us

この変更は、中国またはドイツのクラウド インスタンスで使用される証明書、ドメイン、またはサービスには影響Microsoft 365。

この記事のすべての証明書情報は、2020 [年 10](./encryption-office-365-certificate-chains.md) 月Microsoft 365暗号化チェーンで以前に提供されました。

## <a name="when-will-this-change-happen"></a>この変更がいつ発生しますか?

サービスは 2022 年 1 月に新しいルート CA への移行を開始し、2022 年 10 月まで継続されます。

## <a name="what-is-changing"></a>何が変わるのですか?

今日では、サービスによって使用される TLS 証明書のMicrosoft 365ルート CA まで連鎖しています。

| CA の共通名 | 拇印 (SHA1) |
|--|--|
| [Baltimore CyberTrust Root](https://cacerts.digicert.com/BaltimoreCyberTrustRoot.crt) | d4de20d05e66fc53fe1a50882c78db2852cae474 |

次のいずれかの中間 CA を使用します。

| CA の共通名 | 拇印 (SHA1) |
|--|--|
| [Microsoft RSA TLS CA 01](https://www.microsoft.com/pki/mscorp/Microsoft%20RSA%20TLS%20CA%2001.crt) | 703d7a8f0ebf55aaa59f98eaf4a206004eb2516a |
| [Microsoft RSA TLS CA 02](https://www.microsoft.com/pki/mscorp/Microsoft%20RSA%20TLS%20CA%2002.crt) | b0c2d2d13cdd56cdaa6ab6e2c04440be4a429c75 |

サービスで使用される新Microsoft 365 TLS 証明書は、次のルート CA の 1 つまでチェーンされます。

| CA の共通名 | 拇印 (SHA1) |
|--|--|
| [DigiCert グローバル ルート G2](https://cacerts.digicert.com/DigiCertGlobalRootG2.crt) | df3c24f9bfd666761b268073fe06d1cc8d4f82a4 |
| [Microsoft RSA ルート証明機関 2017](https://www.microsoft.com/pkiops/certs/Microsoft%20RSA%20Root%20Certificate%20Authority%202017.crt) | 73a5e64a3bff8316ff0edccc618a906e4eae4d74 | 
| [Microsoft ECC ルート証明機関 2017](https://www.microsoft.com/pkiops/certs/Microsoft%20ECC%20Root%20Certificate%20Authority%202017.crt) | 999a64c37ff47d9fab95f14769891460eec4c3c5 |

次のいずれかの中間 CA を使用します。

| CA の共通名 | 拇印 (SHA1) |
|--|--|
| [Microsoft Azure TLS 発行 CA 01](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2001%20-%20xsign.crt) | 2f2877c5d778c31e0f29c7e371df5471bd673173 |
| [Microsoft Azure TLS 発行 CA 02](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2002%20-%20xsign.crt) | e7eea674ca718e3befd90858e09f8372ad0ae2aa |
| [Microsoft Azure TLS 発行 CA 05](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2005%20-%20xsign.crt) | 6c3af02e7f269aa73afd0eff2a88a4a1f04ed1e5 |
| [Microsoft Azure TLS 発行 CA 06](https://www.microsoft.com/pkiops/certs/Microsoft%20Azure%20TLS%20Issuing%20CA%2006%20-%20xsign.crt) | 30e01761ab97e59a06b41ef20af6f2de7ef4f7b0 |

例として、これは新しい証明書チェーンのいずれかを持つ有効な証明書です。

![Teams TLS 証明書チェーン](../media/teams-tls-certificate-chain.png)

## <a name="will-this-change-affect-me"></a>この変更は影響しますか?

ルート CA "DigiCert Global Root G2" は、Windows、macOS、Android、iOS などのオペレーティング システム、および Microsoft Edge、Chrome、Safari、Firefox などのブラウザーによって広く信頼されています。 お客様 **の多Microsoft 365影響を受けない可能性があります**。 

ただし、アプリケーションが受け入れ可能な AS の一覧を明示的に指定した場合、アプリケーションが影響 **を受け取る可能性があります**。 この方法は"証明書のピン留め" と呼ばれる。 受け入れ可能な CA の一覧に新しいルート CA をお持ちではないお客様は、証明書の検証エラーを受け取り、アプリケーションの可用性または機能に影響を与える可能性があります。

アプリケーションが影響を受け得る可能性を検出する方法を次に示します。

- ソース コードで、拇印、共通名、またはここで見つかった中間 CA のその他のプロパティを検索 [します](https://www.microsoft.com/pki/mscorp/cps/default.htm)。 一致する場合は、アプリケーションに影響が及びかねない。 この問題を解決するには、ソース コードを更新して、新しい CAs のプロパティを追加します。 ベスト プラクティスとして、短い通知で、CAs を追加または編集できます。 業界の規制では、状況によっては 7 日以内に CA 証明書を交換する必要があります。そのため、証明書のピン留めを実装するアプリケーションは、これらの変更に迅速に対応する必要があります。

- .NET は、`System.Net.ServicePointManager.ServerCertificateValidationCallback``System.Net.HttpWebRequest.ServerCertificateValidationCallback`標準の証明書ストアに依存するのではなく、カスタム ロジックを使用して証明書が有効かどうかを判断するコールバック関数とコールバック関数Windowsします。 開発者は、特定の共通名または拇印をチェックするロジックを追加したり、特定のルート CA ("Baltimore CyberTrust Root" など) のみを許可したりできます。 アプリケーションでこれらのコールバック関数を使用する場合は、古い CA と新しいルート CA と中間 CA の両方を受け入れる必要があります。

- ネイティブ アプリケーションが使用されている場合があります `WINHTTP_CALLBACK_STATUS_SENDING_REQUEST`。これにより、ネイティブ アプリケーションはカスタム証明書検証ロジックを実装できます。 この通知の使用はまれであり、実装にはかなりの量のカスタム コードが必要です。 上記と同様に、アプリケーションが新しいルート CA と中間 CA の両方を受け入れる必要があります。 

- Microsoft Teams、Skype、Skype for Business Online、または Microsoft Dynamics API と統合するアプリケーションを使用し、証明書のピン留めを使用している場合は、アプリケーション ベンダーに確認してください。

- Azure サービスと通信する異なるオペレーティング システムと言語ランタイムでは、新しい証明書チェーンを正しく構築して検証するために他の手順が必要な場合があります。
   - **Linux**: 多くのディストリビューションでは、CAs を追加する必要があります `/etc/ssl/certs`。 具体的な手順については、配布のドキュメントを参照してください。
   - **Java**: キー ストアに上記Javaの一覧が含まれているか確認します。
   - **Windows環境** で実行されている場合: 切断された環境で実行されているシステムには、新しいルート CA `Trusted Root Certification Authorities` がストアに追加され、新しい中間 CA がストアに追加されている必要`Intermediate Certification Authorities`があります。
   - **Android**: デバイスと Android のバージョンのドキュメントを確認します。
   - **IoT または埋** め込みデバイス: テレビ セットのトップ ボックスなどの埋め込みデバイスは、多くの場合、制限されたルート機関証明書セットと一緒に出荷され、証明書ストアを簡単に更新できません。 カスタム埋め込みデバイスまたは IoT デバイスのコードを記述したり、展開を管理したりする場合は、デバイスが新しいルート CA を信頼してください。 デバイスの製造元に問い合わせが必要な場合があります。

- ファイアウォールルールで特定のエンドポイントへの発信呼び出しのみを許可する環境がある場合は、次の証明書失効リスト (CRL) またはオンライン証明書状態プロトコル (OCSP) URL を許可します。
   - `http://crl3.digicert.com`
   - `http://crl4.digicert.com`
   - `http://ocsp.digicert.com`
   - `http://crl.microsoft.com`
   - `http://oneocsp.microsoft.com`
   - `http://ocsp.msocsp.com`
   - `http://www.microsoft.com/pkiops`

- この変更の影響を受け、実行中の環境の種類と影響を受け取るシナリオによってエラー メッセージが表示される場合があります。 次Windowsアプリケーション イベント ログ、CAPI2 イベント ログ、カスタム アプリケーション ログを確認します。
   ```output
   An operation failed because the following certificate has validation errors:
   
   Subject Name: CN=teams.microsoft.com
   Issuer Name: CN=Microsoft Azure TLS Issuing CA 01, O=Microsoft Corporation, C=US
   
   Errors:
   
   The root of the certificate chain is not a trusted root authority.
   ```

## <a name="when-can-i-retire-the-old-ca-information"></a>古い CA 情報をいつ廃止できますか?

現在のルート CA、中間 CA、およびリーフ証明書は取り消されません。 既存の CA 共通名または拇印は、既存の証明書の有効期間に基づいて、少なくとも 2023 年 10 月までに必要になります。
