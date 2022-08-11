---
title: Microsoft Defender ウイルス対策エクスポート デバイス ウイルス対策の正常性の詳細 API メソッドとプロパティ
description: Microsoft Defender ウイルス対策デバイスの正常性の詳細のリストをエクスポートする方法について説明します。
keywords: API, グラフ API, サポートされている API, GET, デバイス正常性 API, Microsoft Defender for Endpoint レポート API Microsoft Defender レポート API, Microsoft Defender for Endpoint レポート API, Windows Defender レポート API, Defender for Endpoint レポート API, Windows Defender レポート API
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
ms.date: 08/08/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 91d8f711abf3a428b506d580227589253ee156a2
ms.sourcegitcommit: 402e0b2095b6cb141b8525a53194d47357bcd612
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2022
ms.locfileid: "67285083"
---
# <a name="export-device-antivirus-health-details-api-methods-and-properties"></a>デバイスウイルス対策の正常性の詳細 API のメソッドとプロパティをエクスポートする

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="export-device-antivirus-health-details-api-description"></a>デバイス ウイルス対策の正常性の詳細 API の説明をエクスポートする

Microsoft Defender ウイルス対策デバイスの正常性の詳細のリストを取得します。 この API には、さまざまな種類のデータを取得するための異なる API 呼び出し (メソッド) があります。 データの量は大きくなる可能性があるため、取得する方法は 2 つあります。

- **JSON 応答**  API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の \@odata.nextLink フィールドを使用して次の結果をフェッチできます。

- **ファイル経由** この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からすべてのデータをダウンロードできます:
  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。
  - ダウンロード URL を使用してすべてのファイルをダウンロードし、データを好きなように処理します。

"_JSON 応答_ または _ファイル経由_" を使用して収集されるデータは、現在の状態の現在のスナップショットです。 履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

> [!IMPORTANT]
>
> Windows &nbsp;Server&nbsp; 2012 &nbsp;R2 と Windows &nbsp;Server&nbsp; 2016 がデバイス正常性レポートに表示されるようにするには、これらのデバイスを最新の統合ソリューション パッケージを使用してオンボードする必要があります。 詳細については、「[Windows Server 2012 R2 と 2016 の最新の統合ソリューションの新機能](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)」を参照してください。

> [!NOTE]
>
> Microsoft 365 セキュリティ ダッシュボードで **デバイスの正常性とウイルス対策のコンプライアンス** レポート ツールを使用する方法については、「[Microsoft Defender for Endpoint のデバイスの正常性とウイルス対策のコンプライアンス レポート](machine-reports.md)」を参照してください。
>

### <a name="11-export-device-antivirus-health-details-api-methods"></a>1.1 デバイスウイルス対策正常性の詳細 API メソッドをエクスポートする

Method|データ型|説明
:---|:---|:---
**(JSON 応答)**|デバイス コレクションあたりの Microsoft Defender ウイルス対策の正常性。 参照: [1.2 デバイス ウイルス対策正常性の詳細 API プロパティのエクスポート (JSON 応答)](#12-export-device-antivirus-health-details-api-properties-json-response)|DeviceId、ConfigurationId のすべての一意の組み合わせのエントリを含むテーブルを返します。 | API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、10 万個未満のデバイスのある小規模な組織に最適です。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。
**(ファイル経由)**|デバイス コレクションあたりの Microsoft Defender ウイルス対策の正常性。 参照: [1.3 ファイル\)を使用してデバイスウイルス対策の正常性の詳細 API プロパティ\(をエクスポート](#13-export-device-antivirus-health-details-api-properties-via-files)する|DeviceId、ConfigurationId のすべての一意の組み合わせのエントリを含むテーブルを返します。 |この API ソリューションを使用すると、より大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からすべてのデータをダウンロードできます: <ol><li>すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。</li><li>ダウンロード URL を使用してすべてのファイルをダウンロードし、データを好きなように処理します。</li></ol>

### <a name="12-export-device-antivirus-health-details-api-properties-json-response"></a>1.2 デバイスウイルス対策正常性の詳細 API プロパティをエクスポートする (JSON 応答)

> [!NOTE]
>
> - 次のテーブルで定義されているプロパティは、プロパティ ID でアルファベット順にリスト表示されます。 この API を実行する場合、結果の出力は必ずしもこのテーブルにリストされているのと同じ順序で返されるとは限りません。
> - 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。ドキュメント化された列のみを使用してください。

| プロパティ (ID) | データ型 | 説明 | 戻り値の例 |
|:----|:----|:----|:----|
| avEngineUpdateTime | DateTimeOffset | デバイスで AV エンジンが最後に更新された日付/時刻 | "2022-08-04T12:44:02Z" |
| avEngineVersion | String | ウイルス対策エンジンのバージョン | "1.1.19400.3" |
| avIsEngineUpToDate | String | AV エンジンの最新の状態 | "True"、"False"、"不明" |
| avIsPlatformUpToDate | String | AV プラットフォームの最新のスタット | "True"、"False"、"不明" |
| avIsSignatureUpToDate | String | AV 署名の最新の状態 | "True"、"False"、"不明" |
| avMode | String | ウイルス対策モード。 | 各モードは、0 から 5 までの範囲の文字列型の整数値になります。 次のマッピングを参照して、その値の意味を確認してください: <ul><li>'' = その他</li><li> '0' = アクティブ</li><li> '1' = パッシブ</li><li> '2' = 無効</li><li> '3' = その他</li><li> '4' = EDRBlocked</li><li>'5' = PassiveAudit</li></ul> |
| avPlatformUpdateTime | DateTimeOffset | デバイスで AV プラットフォームが最後に更新された日付/時刻 | "2022-08-04T12:44:02Z" |
| avPlatformVersion | String | ウイルス対策プラットフォームのバージョン | "4.18.2203.5" |
| avSignaturePublishTime | DateTimeOffset | AV セキュリティ インテリジェンス ビルドがリリースされた日付/時刻 | "2022-08-04T12:44:02Z" |
| avSignatureUpdateTime | DateTimeOffset | デバイスで AV セキュリティ インテリジェンスが最後に更新された日付/時刻 | "2022-08-04T12:44:02Z" |
| avSignatureVersion | String | ウイルス対策セキュリティ インテリジェンスのバージョン | "1.371.1323.0" |
| computerDnsName | String | DNS 名 | "SampleDns" |
| dataRefreshTimestamp | DateTimeOffset | このレポートのデータが更新される日付/時刻 | "2022-08-04T12:44:02Z" |
| fullScanError | String | フル スキャンのエラー コード | "0x80508023" |
| fullScanResult | String | このデバイスのフル スキャン結果 | "完了済み" <br> "取り消し済み" <br>"失敗" |
| fullScanTime | DateTimeOffset | 完全スキャンが完了した日付/時刻 | "2022-08-04T12:44:02Z" |
| id | String | マシン GUID | "30a8fa2826abf24d24379b23f8a44d471f00feab" |
| lastSeenTime | DateTimeOffset | このマシンの最終表示日付/時刻 | "2022-08-04T12:44:02Z" |
| MachineId | String | マシン GUID | "30a8fa2826abf24d24379b23f8a44d471f00feab" |
| osKind | String | オペレーティング システムの種類 | "windows"、"mac"、"linux" |
| osPlatform | String | オペレーティング システムのメジャー バージョン名 | Windows 10、macO |
| osVersion | String | オペレーティング システムのバージョン | 10.0.18363.1440, 12.4.0.0 |
| quickScanError | String | クイック スキャンのエラー コード | "0x80508023" |
| quickScanResult | String | このデバイスのクイック スキャン結果 | "完了済み" <br>"取り消し済み" <br>"失敗" |
| quickScanTime | DateTimeOffset | クイック スキャンが完了した日付/時刻   | "2022-08-04T12:44:02Z" |
| rbacGroupId | Long | このマシンが属するデバイス グループ ID | 712 |
| rbacGroupName | String | このマシンが属するデバイス グループの名前 | "SampleGroup" |

### <a name="13-export-device-antivirus-health-details-api-properties-via-files"></a>1.3 デバイス ウイルス対策の正常性の詳細 API プロパティをエクスポートする (ファイル経由)

> [!NOTE]
>
> - ファイルは、複数行の JSON 形式の gzip 圧縮されています。
> - ダウンロード URL は 3 時間だけ有効です。それ以外の場合は、パラメーターを使用できます。
> - データの最大ダウンロード速度を確保するために、データが存在するのと同じ Azure リージョンからダウンロードしていることを確認できます。
> - 各レコードは約 1 KB のデータです。 正しい pageSize パラメーターを選択するときは、これを考慮する必要があります。
> - 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。ドキュメント化された列のみを使用してください。

| プロパティ (ID) | データ型 | 説明 | 戻り値の例 |
|:----|:----|:----|:----|
| ファイルをエクスポートする | array[string] | 組織の現在のスナップショットを保持しているファイルのダウンロード URL のリスト。 | ["https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"] |
| GeneratedTime | String | エクスポートが生成された時刻。 | 2022-05-20T08:00:00Z |

> [!NOTE]
> 各エクスポート ファイルでは、ウイルス対策情報に関するデータを含むプロパティ "DeviceGatheredInfo" が見つかります。 各属性は、デバイスの正常性とその状態に関する情報を提供できます。

## <a name="see-also"></a>関連項目

[デバイス ウイルス対策の正常性レポートをエクスポートする](device-health-export-antivirus-health-report-api.md)

[デバイスの正常性とコンプライアンスのレポート](machine-reports.md)
