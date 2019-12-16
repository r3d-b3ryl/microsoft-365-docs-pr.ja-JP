---
title: Microsoft Threat Protection の高度な捜索スキーマのデータ テーブル
description: 高度な捜索スキーマのテーブルについて学習し、脅威の捜索クエリを実行できるデータを理解します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、データ
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
ms.openlocfilehash: 1803445dfd9b46fce23b0dcc9585ea543f1b0347
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911308"
---
# <a name="understand-the-advanced-hunting-schema"></a>高度な捜索スキーマの概要

**適用対象:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

[高度な捜索](advanced-hunting-overview.md)スキーマは、イベント情報またはマシンとエンティティに関する情報を提供する複数のテーブルで構成されます。 複数のテーブルにまたがるクエリを効果的に構築するには、高度な捜索スキーマのテーブルと列を理解する必要があります。

## <a name="schema-tables"></a>スキーマ テーブル

次の参照は、スキーマ内のすべてのテーブルを一覧表示します。 各テーブル名は、そのテーブルの列名を説明するページにリンクします。 テーブル名と列名は、高度な捜索画面のスキーマ表現の一部として、セキュリティ センターにも一覧表示されます。

| テーブル名 | 説明 |
|------------|-------------|
| **[MachineInfo](advanced-hunting-machineinfo-table.md)** | OS 情報を含むマシン情報 |
| **[MachineNetworkInfo](advanced-hunting-machinenetworkinfo-table.md)** | アダプタ、IP アドレス、MAC アドレス、および接続されたネットワークとドメインを含むマシンのネットワーク プロパティ |
| **[ProcessCreationEvents](advanced-hunting-processcreationevents-table.md)** | プロセスの作成と関連イベント |
| **[NetworkCommunicationEvents](advanced-hunting-networkcommunicationevents-table.md)** | ネットワーク接続と関連イベント |
| **[FileCreationEvents](advanced-hunting-filecreationevents-table.md)** | ファイルの作成、変更、およびその他のファイル システム イベント |
| **[RegistryEvents](advanced-hunting-registryevents-table.md)** | レジストリ エントリの作成と変更 |
| **[LogonEvents](advanced-hunting-logonevents-table.md)** | サインインとその他の認証イベント |
| **[ImageLoadEvents](advanced-hunting-imageloadevents-table.md)** | DLL の読み込みイベント |
| **[MiscEvents](advanced-hunting-miscevents-table.md)** | Windows Defender ウイルス対策や Exploit Protection などのセキュリティ制御によりトリガーされたイベントを含むさまざまな種類のイベント  |
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
