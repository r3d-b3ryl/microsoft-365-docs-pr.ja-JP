---
title: 高度な検索スキーマの DeviceFileCertificateInfo テーブル
description: 高度な検索スキーマの DeviceFileCertificateInfo テーブルにあるファイルの署名情報について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、digital signature、certificate、file signature、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9291d9f113fdc1c082b38d92399c1dee646b523d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846172"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`DeviceFileCertificateInfo`[高度な](advanced-hunting-overview.md)検索スキーマの表には、ファイル署名証明書に関する情報が含まれています。 この表では、エンドポイントのファイルで定期的に実行される証明書の検証アクティビティから取得したデータを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `IsSigned` | ブール値 | ファイルが署名されているかどうかを示します |
| `SignatureType` | string | 署名情報がファイル自体の埋め込みコンテンツとして読み取られたか、外部カタログファイルから読み取られたかを示します |
| `Signer` | string | ファイルの署名者に関する情報 |
| `SignerHash` | string | 署名者を識別する一意のハッシュ値 |
| `Issuer` | string | 発行元の証明機関 (CA) に関する情報 |
| `IssuerHash` | string | 発行証明機関 (CA) を識別する一意のハッシュ値 |
| `CertificateSerialNumber` | string | 発行元の証明機関 (CA) に固有の証明書の識別子 |
| `CrlDistributionPointUrls` | string |  証明書と証明書失効リスト (Crl) を含むネットワーク共有の Url を一覧表示する JSON 配列 |
| `CertificateCreationTime` | 日付型 | 証明書が作成された日付と時刻 |
| `CertificateExpirationTime` | 日付型 | 証明書が期限切れに設定された日付と時刻 |
| `CertificateCountersignatureTime` | 日付型 | 証明書が副署名された日付と時刻 |
| `IsTrusted` | ブール値 | WinVerifyTrust 関数の結果に基づいてファイルが信頼されているかどうかを示します。この関数は、不明なルート証明書情報、無効な署名、失効した証明書、およびその他の疑わしい属性をチェックします。 |
| `IsRootSignerMicrosoft` | ブール値 | ルート証明書の署名者が Microsoft であるかどうかを示します |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。 | 

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
