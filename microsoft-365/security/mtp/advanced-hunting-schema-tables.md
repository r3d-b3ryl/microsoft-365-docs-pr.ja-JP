---
title: Microsoft 365 Defender 高度な検索スキーマのデータ テーブル
description: 高度な捜索スキーマのテーブルについて学習し、脅威の捜索クエリを実行できるデータを理解します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、データ
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
ms.openlocfilehash: b335ba90479c670d918226caa18f80ee5535f0a1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925059"
---
# <a name="understand-the-advanced-hunting-schema"></a>高度な捜索スキーマの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高度 [な検索スキーマ](advanced-hunting-overview.md) は、イベント情報またはデバイス、アラート、ID、その他のエンティティの種類に関する情報を提供する複数のテーブルで構成されています。 複数のテーブルにまたがるクエリを効果的に構築するには、高度な捜索スキーマのテーブルと列を理解する必要があります。

## <a name="get-schema-information-in-the-security-center"></a>セキュリティ センターでスキーマ情報を取得する
クエリを作成する場合は、組み込みのスキーマ参照を使用して、スキーマ内の各テーブルに関する次の情報をすばやく取得します。

- **テーブルの** 説明 — テーブルに含まれるデータの種類と、そのデータのソース。
- **列**- テーブル内のすべての列。
- **アクションの** 種類 — テーブルでサポートされているイベントの種類を表す列 `ActionType` の可能な値。 この情報は、イベント情報を含むテーブルに対してだけ提供されます。
- **サンプル クエリ**— テーブルの利用方法を備えたクエリの例です。

### <a name="access-the-schema-reference"></a>スキーマ リファレンスにアクセスする
スキーマ参照にすばやくアクセスするには、スキーマ表現のテーブル名の横にある [参照の表示] アクションを選択します。 [スキーマ参照] **を選択して** テーブルを検索することもできます。   

![ポータル内スキーマ リファレンスにアクセスする方法を示す画像 ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>スキーマ テーブルについて
次の参照は、スキーマ内のすべてのテーブルを一覧表示します。 各テーブル名は、そのテーブルの列名を説明するページにリンクします。 テーブル名と列名は、高度な検索画面のスキーマ表現の一部としてセキュリティ センターにも表示されます。

| テーブル名 | 説明 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | アラートに関連付けられているファイル、IP アドレス、URL、ユーザー、またはデバイス |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | エンドポイント用 Microsoft Defender、Office 365 用 Microsoft Defender、Microsoft Cloud App Security、Id 用 Microsoft Defender からのアラート (重大度情報や脅威の分類を含む)  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | クラウド アプリとサービスでのファイル関連のアクティビティ |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Office 365 および他のクラウド アプリとサービスのアカウントとオブジェクトに関連するイベント |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Windows Defender ウイルス対策や Exploit Protection などのセキュリティ制御によりトリガーされたイベントを含むさまざまな種類のイベント  |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | エンドポイント上の証明書検証イベントから取得した署名済みファイルの証明書情報 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | ファイルの作成、変更、およびその他のファイル システム イベント |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL の読み込みイベント |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | OS 情報を含むマシン情報 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | デバイスでのサインインと他の認証イベント |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | ネットワーク接続と関連イベント |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 物理アダプター、IP アドレスと MAC アドレス、接続されたネットワークとドメインを含むデバイスのネットワーク プロパティ |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | プロセスの作成と関連イベント |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | レジストリ エントリの作成と変更 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理の評価イベント |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 脅威および脆弱性管理によってデバイスを評価するために使用されるさまざまなセキュリティ構成に関するサポート技術情報 (さまざまな標準およびベンチマークへのマッピングを含む)　  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | デバイス上のソフトウェアのインベントリと、これらのソフトウェア製品の既知の脆弱性 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | メールに添付されたファイルに関する情報 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 電子メール イベント (メール配信イベントとブロック イベントを含む) |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365 が受信者のメールボックスにメールを配信した後に、配信後に発生するセキュリティ イベント |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | メールの URL に関する情報 |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Active Directory を実行しているオンプレミスのドメイン コントローラーに関連するイベント (AD)。 次の表に、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲を示します。 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Azure Active Directory など、さまざまなソースからのアカウント情報 |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory および Microsoft オンライン サービスの認証イベント |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトのクエリ |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
