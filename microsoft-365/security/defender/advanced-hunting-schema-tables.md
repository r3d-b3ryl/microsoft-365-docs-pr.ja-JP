---
title: Microsoft 365 Defender高度なハンティング スキーマのデータ テーブル
description: 高度な捜索スキーマのテーブルについて学習し、脅威の捜索クエリを実行できるデータを理解します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, データ
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
ms.openlocfilehash: 11b0c3e76b7f14396ea2bd2b133d1b5a34ec0624
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477299"
---
# <a name="understand-the-advanced-hunting-schema"></a>高度な捜索スキーマの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度なハンティング](advanced-hunting-overview.md) スキーマは、イベント情報またはデバイス、アラート、ID、およびその他のエンティティの種類に関する情報を提供する複数のテーブルで構成されています。 複数のテーブルにまたがるクエリを効果的にビルドするには、高度な追求スキーマのテーブルと列を理解する必要があります。

<a name="get-schema-information-in-the-security-center"></a>

## <a name="get-schema-information"></a>スキーマ情報を取得する

クエリを作成するときに、組み込みのスキーマ参照を使用して、スキーマ内の各テーブルに関する次の情報をすばやく取得します。

- **テーブルの説明 - テーブル** に含まれるデータの種類とそのデータのソース。
- **列** - テーブル内のすべての列。
- **アクションの種類** - テーブルで `ActionType` サポートされているイベントの種類を表す列で使用できる値。 この情報は、イベント情報を含むテーブルに対してのみ提供されます。
- **サンプル クエリ** - テーブルの使用方法を特徴とするクエリの例。

### <a name="access-the-schema-reference"></a>スキーマリファレンスにアクセスする
スキーマ参照にすばやくアクセスするには、スキーマ表現のテーブル名の横にある **[参照の表示** ] アクションを選択します。 [ **スキーマ参照** ] を選択してテーブルを検索することもできます。

:::image type="content" source="../../media/understand-schema-1.png" alt-text="Microsoft 365 Defender ポータルの [高度な検索] ページの [スキーマ参照] ページ" lightbox="../../media/understand-schema-1.png":::

## <a name="learn-the-schema-tables"></a>スキーマ テーブルについて学習する
次の参照は、スキーマ内のすべてのテーブルを一覧表示します。 各テーブル名は、そのテーブルの列名を説明するページにリンクします。 テーブル名と列名は、高度なハンティング画面のスキーマ表現の一部として Defender for Cloud にも一覧表示されます。

| テーブル名 | 説明 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | アラートに関連付けられているファイル、IP アドレス、URL、ユーザー、またはデバイス |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、Microsoft Defender for Identityからのアラート重大度情報と脅威の分類を含む  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Office 365 およびその他のクラウド アプリとサービスのアカウントとオブジェクトに関連するイベント |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Microsoft Defender ウイルス対策やエクスプロイト保護などのセキュリティ制御によってトリガーされるイベントを含む、複数のイベントの種類 |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | エンドポイント上の証明書検証イベントから取得した署名済みファイルの証明書情報 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | ファイルの作成、変更、およびその他のファイル システム イベント |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL の読み込みイベント |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | OS 情報を含むマシン情報 |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | サインインおよびデバイス上のその他のイベント |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | ネットワーク接続と関連イベント |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 物理アダプタ、IP アドレス、MAC アドレス、および接続されたネットワークとドメインなど、デバイスのネットワーク プロパティ |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | プロセスの作成と関連イベント |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | レジストリ エントリの作成と変更 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | デバイス上のさまざまなセキュリティ構成の状態を示す評価イベントをMicrosoft Defender 脆弱性の管理する |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | デバイスを評価するためにMicrosoft Defender 脆弱性の管理によって使用されるさまざまなセキュリティ構成のナレッジ ベース。さまざまな標準とベンチマークへのマッピングが含まれています。  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | デバイスにインストールされているソフトウェアのインベントリ (バージョン情報とサポート終了の状態を含む) |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | デバイスで見つかったソフトウェアの脆弱性と、各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | メールに添付されたファイルに関する情報 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | メールの配信やブロック イベントなど、Microsoft 365 のメール イベント |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365 が受信者メールボックスにメールを配信した後に配信後に発生するセキュリティ イベント |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | メールの URL に関する情報 |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Active Directory (AD) を実行しているオンプレミス ドメイン コントローラーに関連するイベント。 このテーブルでは、ドメイン コントローラー上の ID 関連のイベントとシステム イベントの範囲を説明しています。 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Azure Active Directory など、様々なソースからのアカウント情報 |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory および Microsoft オンライン サービスでの認証イベント |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | ユーザー、グループ、デバイス、ドメインなどの Active Directory オブジェクトのクエリ |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
