---
title: 高度なハンティング スキーマの DeviceFileCertificateInfo テーブル
description: 高度なハンティング スキーマの DeviceFileCertificateInfo テーブルのファイル署名情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、デジタル署名、証明書、ファイル署名、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499179"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高度 `DeviceFileCertificateInfo` な検索スキーマ [の表](advanced-hunting-overview.md) には、ファイル署名証明書に関する情報が含まれている。 次の表は、エンドポイント上のファイルで定期的に実行される証明書検証アクティビティから取得したデータを使用します。

高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | 文字列 | サービス内のデバイスの一意の識別子 |
| `DeviceName` | 文字列 | デバイスの完全修飾ドメイン名 (FQDN) |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `IsSigned` | boolean | ファイルが署名されているかどうかを示します。 |
| `SignatureType` | 文字列 | 署名情報をファイル自体に埋め込みコンテンツとして読み取ったか、外部カタログ ファイルから読み取ったかを示します。 |
| `Signer` | 文字列 | ファイルの署名者に関する情報 |
| `SignerHash` | 文字列 | 署名者を識別する一意のハッシュ値 |
| `Issuer` | 文字列 | 発行元証明機関 (CA) に関する情報 |
| `IssuerHash` | 文字列 | 発行元証明機関 (CA) を識別する一意のハッシュ値 |
| `CertificateSerialNumber` | 文字列 | 発行元証明機関 (CA) に固有の証明書の識別子 |
| `CrlDistributionPointUrls` | 文字列 |  証明書と証明書失効リスト (CRL) を含むネットワーク共有の URL を示す JSON 配列 |
| `CertificateCreationTime` | 日付型 | 証明書が作成された日時 |
| `CertificateExpirationTime` | 日付型 | 証明書の有効期限が設定されている日時 |
| `CertificateCountersignatureTime` | 日付型 | 証明書が署名された日時 |
| `IsTrusted` | boolean | 不明なルート証明書情報、無効な署名、失効した証明書、その他の疑いがある属性をチェックする WinVerifyTrust 関数の結果に基づいてファイルが信頼されているかどうかを示します。 |
| `IsRootSignerMicrosoft` | boolean | ルート証明書の署名者が Microsoft であるかどうかを示します。 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |


## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
