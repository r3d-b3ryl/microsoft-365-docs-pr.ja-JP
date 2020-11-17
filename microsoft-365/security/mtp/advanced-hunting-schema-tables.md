---
title: Microsoft 365 Defender の高度な検索スキーマのデータテーブル
description: 高度な捜索スキーマのテーブルについて学習し、脅威の捜索クエリを実行できるデータを理解します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、データ
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
ms.openlocfilehash: ed5c7084e899c99237074a46af21454a4c21dfe8
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087017"
---
# <a name="understand-the-advanced-hunting-schema"></a>高度な捜索スキーマの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度な](advanced-hunting-overview.md)検索スキーマは、デバイス、アラート、id、およびその他のエンティティの種類に関するイベント情報または情報を提供する複数のテーブルで構成されています。 複数のテーブルにまたがるクエリを効果的に構築するには、高度な捜索スキーマのテーブルと列を理解する必要があります。

## <a name="get-schema-information-in-the-security-center"></a>セキュリティセンターでスキーマ情報を取得する
クエリを作成する際には、組み込みスキーマ参照を使用して、スキーマ内の各テーブルに関する以下の情報をすばやく取得します。

- [**テーブルの説明**]: テーブルに格納されているデータの種類と、そのデータのソース。
- **列**-表のすべての列。
- **アクションの種類**-列で、 `ActionType` テーブルでサポートされているイベントの種類を表す値を指定できます。 この情報は、イベント情報を含むテーブルに対してのみ表示されます。
- **サンプルクエリ**-テーブルを使用する方法を示すクエリの例です。

### <a name="access-the-schema-reference"></a>スキーマリファレンスにアクセスする
スキーマ参照にすばやくアクセスするには、スキーマ表現のテーブル名の横にある [ **参照の表示** ] アクションを選択します。 [ **スキーマ参照** ] を選択して、テーブルを検索することもできます。   

![ポータル内スキーマリファレンスへのアクセス方法を示す画像 ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>スキーマテーブルについて
次の参照は、スキーマ内のすべてのテーブルを一覧表示します。 各テーブル名は、そのテーブルの列名を説明するページにリンクします。 詳細な検索画面のスキーマ表現の一部として、テーブルと列の名前もセキュリティセンターに表示されます。

| テーブル名 | 説明 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | アラートに関連付けられているファイル、IP アドレス、Url、ユーザー、またはデバイス |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | エンドポイントに関する Microsoft Defender、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Id (重要度情報や脅威の分類を含む) に関する microsoft defender からの通知  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | クラウドアプリとサービスのファイル関連アクティビティ |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Office 365 のアカウントとオブジェクトに関連するイベントとその他のクラウドアプリおよびサービス |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Windows Defender ウイルス対策や Exploit Protection などのセキュリティ制御によりトリガーされたイベントを含むさまざまな種類のイベント  |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | エンドポイントの証明書検証イベントから取得された署名済みファイルの証明書情報 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | ファイルの作成、変更、およびその他のファイル システム イベント |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL の読み込みイベント |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | OS 情報を含むマシン情報 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | デバイス上のサインインとその他の認証イベント |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | ネットワーク接続と関連イベント |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 物理アダプター、IP アドレス、MAC アドレス、および接続されたネットワークとドメインを含むデバイスのネットワークプロパティ |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | プロセスの作成と関連イベント |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | レジストリ エントリの作成と変更 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理の評価イベント |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 脅威および脆弱性管理によってデバイスを評価するために使用されるさまざまなセキュリティ構成に関するサポート技術情報 (さまざまな標準およびベンチマークへのマッピングを含む)　  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | デバイス上のソフトウェアのインベントリと、これらのソフトウェア製品の既知の脆弱性 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 電子メールに添付されたファイルに関する情報 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Microsoft 365 の電子メールイベント (電子メール配信およびブロックイベントを含む) |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365 がメールを受信者のメールボックスに配信した後の、配信後に発生するセキュリティイベント |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | メールの Url に関する情報 |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Active Directory (AD) を実行しているオンプレミスのドメインコントローラーに関係するイベント。 この表は、ドメインコントローラーの id 関連イベントとシステムイベントの範囲を示しています。 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Azure Active Directory を含む、さまざまなソースからのアカウント情報 |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory と Microsoft online services の認証イベント |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトに対するクエリ |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で捜索する](advanced-hunting-query-emails-devices.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
