---
title: Microsoft Threat Protection の高度な捜索スキーマのデータ テーブル
description: 高度な捜索スキーマのテーブルについて学習し、脅威の捜索クエリを実行できるデータを理解します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、データ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aa2fbeebed10bcb1f0c4078a161be99d16d3b97b
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210322"
---
# <a name="understand-the-advanced-hunting-schema"></a>高度な捜索スキーマの概要

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度な捜索](advanced-hunting-overview.md)スキーマは、イベント情報またはマシンとエンティティに関する情報を提供する複数のテーブルで構成されます。 複数のテーブルにまたがるクエリを効果的に構築するには、高度な捜索スキーマのテーブルと列を理解する必要があります。

## <a name="schema-tables"></a>スキーマ テーブル

次の参照は、スキーマ内のすべてのテーブルを一覧表示します。 各テーブル名は、そのテーブルの列名を説明するページにリンクします。 テーブル名と列名は、高度な捜索画面のスキーマ表現の一部として、セキュリティ センターにも一覧表示されます。

| テーブル名 | 説明 |
|------------|-------------|
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | OS 情報を含むマシン情報 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | アダプタ、IP アドレス、MAC アドレス、および接続されたネットワークとドメインを含むマシンのネットワーク プロパティ |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | プロセスの作成と関連イベント |
| **[DeviceNetworkEvents 孔](advanced-hunting-devicenetworkevents-table.md)** | ネットワーク接続と関連イベント |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | ファイルの作成、変更、およびその他のファイル システム イベント |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | レジストリ エントリの作成と変更 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | サインインとその他の認証イベント |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL の読み込みイベント |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Windows Defender ウイルス対策や Exploit Protection などのセキュリティ制御によりトリガーされたイベントを含むさまざまな種類のイベント  |
| **[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)** | エンドポイントの証明書検証イベントから取得された署名済みファイルの証明書情報 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | メール配信やブロック イベントを含む Office 365 のメール イベント |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Office 365 メールに添付されたファイルに関する情報 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Office 365 メールの URL に関する情報 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | デバイス上のソフトウェアのインベントリ、およびこれらのソフトウェア製品の既知の脆弱性 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | 悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理の評価イベント |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | 脅威および脆弱性管理によってデバイスを評価するために使用されるさまざまなセキュリティ構成に関するサポート技術情報 (さまざまな標準およびベンチマークへのマッピングを含む)　  |

## <a name="related-topics"></a>関連項目
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)