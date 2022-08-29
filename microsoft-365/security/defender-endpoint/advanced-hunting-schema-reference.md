---
title: 高度なハンティング スキーマリファレンス
description: 高度なハンティング スキーマのテーブルについて説明し、脅威検出クエリを実行できるデータを理解します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, mdatp, microsoft defender atp, Microsoft Defender for endpoint, wdatp search, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, データ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: 76c9f55e99ba13417403a6f9ac2d03913f792326
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326323"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointの高度なハンティング スキーマについて理解する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[高度なハンティング](advanced-hunting-overview.md) スキーマは、イベント情報またはデバイスやその他のエンティティに関する情報を提供する複数のテーブルで構成されています。 複数のテーブルにまたがるクエリを効果的にビルドするには、高度な追求スキーマのテーブルと列を理解する必要があります。

## <a name="get-schema-information-in-the-defender-for-cloud"></a>Defender for Cloud でスキーマ情報を取得する

クエリを作成するときに、組み込みのスキーマ参照を使用して、スキーマ内の各テーブルに関する次の情報をすばやく取得します。

- **テーブルの説明: テーブル** に含まれるデータの種類とそのデータのソース。
- **列**: テーブル内のすべての列。
- **アクションの種類**: テーブルで `ActionType` サポートされているイベントの種類を表す列で使用できる値。 これらの値は、イベント情報を含むテーブルにのみ提供されます。
- **サンプル クエリ**: テーブルの使用方法を特徴とするクエリの例。

### <a name="access-the-schema-reference"></a>スキーマリファレンスにアクセスする

スキーマ参照にすばやくアクセスするには、スキーマ表現のテーブル名の横にある **[参照の表示** ] アクションを選択します。 [ **スキーマ参照** ] を選択してテーブルを検索することもできます。

:::image type="content" source="images/ah-reference.png" alt-text="高度なハンティング ページ" lightbox="images/ah-reference.png":::

## <a name="learn-the-schema-tables"></a>スキーマ テーブルについて学習する

次のリファレンスは、高度なハンティング スキーマ内のすべてのテーブルの一覧です。 各テーブル名は、そのテーブルの列名を説明するページにリンクします。

テーブル名と列名は、高度な検索画面のスキーマ表現のMicrosoft 365 Defender ポータルにも一覧表示されます。

<br>

****

|テーブル名|説明|
|---|---|
|**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**|Microsoft 365 Defenderに関するアラート |
|**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**|OS 情報を含むデバイス情報|
|**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**|アダプター、IP アドレス、MAC アドレス、接続されたネットワークとドメインなど、デバイスのネットワーク プロパティ|
|**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**|プロセスの作成と関連イベント|
|**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**|ネットワーク接続と関連イベント|
|**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**|ファイルの作成、変更、およびその他のファイル システム イベント|
|**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**|レジストリ エントリの作成と変更|
|**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**|サインインとその他の認証イベント|
|**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**|DLL の読み込みイベント|
|**[DeviceEvents](advanced-hunting-deviceevents-table.md)**|Microsoft Defender ウイルス対策やエクスプロイト保護などのセキュリティ制御によってトリガーされるイベントを含む、複数のイベントの種類|
|**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**|エンドポイント上の証明書検証イベントから取得した署名済みファイルの証明書情報|
|**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**|デバイスにインストールされているソフトウェアのインベントリ (バージョン情報とサポート終了の状態を含む)|
|**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**|デバイスで見つかったソフトウェアの脆弱性と、各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧|
|**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**|悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報|
|**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**|デバイス上のさまざまなセキュリティ構成の状態を示す評価イベントをMicrosoft Defender 脆弱性の管理する|
|**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**|Defender 脆弱性管理がデバイスを評価するために使用するさまざまなセキュリティ構成のナレッジ ベース。には、さまざまな標準とベンチマークへのマッピングが含まれます|
|

> [!TIP]
> [Microsoft 365 Defenderでの高度な捜索](/microsoft-365/security/defender/advanced-hunting-overview)を使用して、Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、およびMicrosoft Defender for Identity。 [Microsoft 365 Defenderをオンにします](/microsoft-365/security/defender/m365d-enable)。

高度なハンティング のワークフローをMicrosoft Defender for EndpointからMicrosoft 365 Defenderに移行する方法の詳細については、「[高度なハンティング クエリをMicrosoft Defender for Endpointから移行する」を参照](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)してください。

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](overview-custom-detections.md)
- [高度なハンティング データ スキーマの変更](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
