---
title: 高度なハンティング スキーマの DeviceFileCertificateInfo テーブル
description: 高度なハンティング スキーマの DeviceFileCertificateInfo テーブルでファイル署名情報について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, デジタル署名, 証明書, ファイル署名, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: 71a2e57abe26ebb84954fda0ab0867a2ec7e23d1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483544"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

`DeviceFileCertificateInfo` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、ファイル署名証明書に関する情報が含まれています。 この表では、エンドポイント上のファイルで定期的に実行される証明書検証アクティビティから取得したデータを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `DeviceId` | `string` | コンピューターの一意識別子 |
| `DeviceName` | `string` | コンピューターの完全修飾ドメイン名 (FQDN) |
| `SHA1` | `string` | 記録されたアクションが適用されたファイルの SHA-1 |
| `IsSigned` | `boolean` | ファイルが署名されているかどうかを示します |
| `SignatureType` | `string` | 署名情報がファイル自体の埋め込みコンテンツとして読み取られたか、外部カタログ ファイルから読み取られたかを示します |
| `Signer` | `string` | ファイルの署名者に関する情報 |
| `SignerHash` | `string` | 署名者を識別する一意のハッシュ値 |
| `Issuer` | `string` | 発行元証明機関 (CA) に関する情報 |
| `IssuerHash` | `string` | 発行元証明機関 (CA) を識別する一意のハッシュ値 |
| `CertificateSerialNumber` | `string` | 発行元証明機関 (CA) に固有の証明書の識別子 |
| `CrlDistributionPointUrls` | `string` |  証明書と証明書失効リスト (CRL) を含むネットワーク共有の URL を一覧表示する JSON 配列 |
| `CertificateCreationTime` | `datetime` | 証明書が作成された日時 |
| `CertificateExpirationTime` | `datetime` | 証明書の有効期限が切れる日付と時刻 |
| `CertificateCountersignatureTime` | `datetime` | 証明書の署名が取り消された日時 |
| `IsTrusted` | `boolean` | 不明なルート証明書情報、無効な署名、失効した証明書、およびその他の疑問の属性をチェックする WinVerifyTrust 関数の結果に基づいて、ファイルが信頼されているかどうかを示します。 |
| `IsRootSignerMicrosoft` | `boolean` | ルート証明書の署名者が Microsoft であるか、ファイルが Windows オペレーティング システムに含まれているかどうかを示します。 |
| `ReportId` | `long` | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列とタイムスタンプ列と組み合わせて使用する必要があります。 | 

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
