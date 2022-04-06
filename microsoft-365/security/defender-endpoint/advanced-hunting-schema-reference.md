---
title: 高度な検索スキーマリファレンス
description: 高度な検索スキーマのテーブルについて説明し、脅威検出クエリを実行できるデータを理解します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、エンドポイント用の microsoft Defender、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、データ
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
ms.openlocfilehash: 2e45a4ae78d0beb9bc57b72a59b9cf1376ac7da7
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468349"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の高度なハンティング スキーマを理解する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

高度 [な検索スキーマ](advanced-hunting-overview.md) は、イベント情報またはデバイスや他のエンティティに関する情報を提供する複数のテーブルで構成されます。 複数のテーブルにまたがるクエリを効果的にビルドするには、高度な追求スキーマのテーブルと列を理解する必要があります。

## <a name="get-schema-information-in-the-defender-for-cloud"></a>Defender for Cloud でスキーマ情報を取得する

クエリを作成する場合は、組み込みのスキーマ参照を使用して、スキーマ内の各テーブルに関する次の情報をすばやく取得します。

- **テーブルの** 説明: テーブルに含まれるデータの種類と、そのデータのソース。
- **列**: テーブル内のすべての列。
- **アクションの種類**: テーブルでサポートされている `ActionType` イベントの種類を表す列の値を指定できます。 これらの値は、イベント情報を含むテーブルにのみ提供されます。
- **サンプル クエリ**: テーブルの利用方法を備えたクエリの例。

### <a name="access-the-schema-reference"></a>スキーマ参照へのアクセス

スキーマ参照にすばやくアクセスするには、スキーマ表現のテーブル名の横にある [参照の表示] アクションを選択します。 [スキーマ参照] **を選択して** テーブルを検索することもできます。

:::image type="content" source="images/ah-reference.png" alt-text="[高度な検索] ページ" lightbox="images/ah-reference.png":::

## <a name="learn-the-schema-tables"></a>スキーマ テーブルの詳細

次の参照では、高度な検索スキーマのすべてのテーブルを一覧表示します。 各テーブル名は、そのテーブルの列名を説明するページにリンクします。

テーブル名と列名は、高度なMicrosoft 365 Defenderスキーマ表現のポータル内にも表示されます。

<br>

****

|テーブル名|説明|
|---|---|
|**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**|ユーザーに関するMicrosoft 365 Defender |
|**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**|OS 情報を含むデバイス情報|
|**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**|アダプター、IP アドレス、MAC アドレス、接続されたネットワークおよびドメインを含むデバイスのネットワーク プロパティ|
|**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**|プロセスの作成と関連イベント|
|**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**|ネットワーク接続と関連イベント|
|**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**|ファイルの作成、変更、およびその他のファイル システム イベント|
|**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**|レジストリ エントリの作成と変更|
|**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**|サインインとその他の認証イベント|
|**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**|DLL の読み込みイベント|
|**[DeviceEvents](advanced-hunting-deviceevents-table.md)**|複数のイベントの種類 (セキュリティ制御によってトリガーされるイベントなど) (Microsoft Defender ウイルス対策悪用防止など)|
|**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**|エンドポイント上の証明書検証イベントから取得した署名済みファイルの証明書情報|
|**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**|デバイスにインストールされているソフトウェアのインベントリ (バージョン情報とサポート終了の状態を含む)|
|**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**|デバイスで見つかったソフトウェアの脆弱性と、各脆弱性に対処する利用可能なセキュリティ更新プログラムの一覧|
|**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**|悪用コードが公開されているかどうかなど、公開されている脆弱性のサポート技術情報|
|**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**|デバイス上のさまざまなセキュリティ構成の状態を示す脅威および脆弱性管理の評価イベント|
|**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**|脅威および脆弱性管理によってデバイスを評価するために使用されるさまざまなセキュリティ構成に関するサポート技術情報 (さまざまな標準およびベンチマークへのマッピングを含む)　|
|

> [!TIP]
> Microsoft 365 Defender で高度な検索[を](/microsoft-365/security/defender/advanced-hunting-overview)使用して、Defender for Endpoint、microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、Microsoft Defender for Identity のデータを使用して脅威を探します。 [[オンにする] Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable)。

高度なハンティング ワークフローを Microsoft Defender for Endpoint から Microsoft 365 Defenderに移動する方法の詳細については、「[Advanced hunting queries from Microsoft Defender for Endpoint」を参照してください](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)。

## <a name="related-topics"></a>関連項目

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [クエリ結果を操作する](advanced-hunting-query-results.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [カスタム検出の概要](overview-custom-detections.md)
- [高度なハンティング データ スキーマの変更](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
