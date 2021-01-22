---
title: 高度な検索スキーマの DeviceFileCertificateInfo テーブル
description: 高度な検索スキーマの DeviceFileCertificateInfo テーブルのファイル署名情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、デジタル署名、証明書、ファイル署名、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931316"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `DeviceFileCertificateInfo` な検索スキーマ [の表には](advanced-hunting-overview.md) 、ファイル署名証明書に関する情報が含まれている。 次の表では、エンドポイント上のファイルに対して定期的に実行される証明書検証アクティビティから取得したデータを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `IsSigned` | ブール値 | ファイルが署名されているかどうかを示します |
| `SignatureType` | string | 署名情報がファイル自体の埋め込みコンテンツとして読み取ったのか、外部カタログ ファイルから読み取ったのかを示します。 |
| `Signer` | string | ファイルの署名者に関する情報 |
| `SignerHash` | string | 署名者を識別する一意のハッシュ値 |
| `Issuer` | string | 発行元証明機関 (CA) に関する情報 |
| `IssuerHash` | string | 発行元証明機関 (CA) を識別する一意のハッシュ値 |
| `CertificateSerialNumber` | string | 発行元証明機関 (CA) に固有の証明書の識別子 |
| `CrlDistributionPointUrls` | string |  証明書と証明書失効リスト (CRL) を含むネットワーク共有の URL を示す JSON 配列 |
| `CertificateCreationTime` | 日付型 | 証明書が作成された日時 |
| `CertificateExpirationTime` | 日付型 | 証明書の有効期限が設定されている日時 |
| `CertificateCountersignatureTime` | 日付型 | 証明書が署名された日時 |
| `IsTrusted` | ブール値 | WinVerifyTrust 関数の結果に基づいてファイルが信頼されているかどうかを示します。WinVerifyTrust 関数は、不明なルート証明書情報、無効な署名、失効した証明書、その他の疑いがある属性をチェックします。 |
| `IsRootSignerMicrosoft` | ブール値 | ルート証明書の署名者が Microsoft かどうかを示します |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 | 

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
