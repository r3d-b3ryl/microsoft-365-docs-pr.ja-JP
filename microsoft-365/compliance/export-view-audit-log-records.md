---
title: 監査ログ レコードをエクスポート、構成、表示する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: この記事では、Microsoft 365 監査ログ レコードをエクスポート、構成、および表示する方法について説明します。
ms.openlocfilehash: b528dcd669749198490b028db4bbd18fe313f1ee
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66640096"
---
# <a name="export-configure-and-view-audit-log-records"></a>監査ログ レコードをエクスポート、構成、表示する

監査ログを検索して検索結果を CSV ファイルにダウンロードすると、ファイルには **AuditData** という名前の列が含まれ、各イベントに関する追加情報が含まれます。 この列のデータは JSON オブジェクトとして書式設定されます。これには、プロパティとして構成された複数のプロパティが含まれます *。値* のペアはコンマで区切られます。 Excel のPower Query エディターの JSON 変換機能を使用すると、**AuditData** 列の JSON オブジェクト内の各プロパティを複数の列に分割して、各プロパティに独自の列を含めることができます。 これにより、これらのプロパティの 1 つ以上を並べ替えてフィルター処理できます。これにより、探している特定の監査データをすばやく見つけることができます。

## <a name="step-1-export-audit-log-search-results"></a>手順 1: 監査ログの検索結果をエクスポートする

最初の手順では、監査ログを検索し、結果をコンマ区切り値 (CSV) ファイルでローカル コンピューターにエクスポートします。
  
1. [監査ログ検索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log)を実行し、必要に応じて検索条件を変更して、目的の結果が得られます。

2. 検索結果ページで、[**エクスポート**] > 、[**すべての結果をダウンロード**] の順にクリックします。

   ![[すべての結果をダウンロード] をクリックします。](../media/ExportAuditSearchResults.png)

   このオプションは、手順 1 で実行した監査ログ検索からすべての監査レコードをエクスポートし、監査ログから CSV ファイルに生データを追加します。 大規模な検索のためにダウンロード ファイルを準備するには、しばらく時間がかかります。 大きなファイルは、すべてのアクティビティを検索したり、広い日付範囲を使用したりするときに発生します。

3. エクスポート処理が完了すると、ウィンドウの上部に、CSV ファイルを開いてローカル コンピュータに保存するように促すメッセージが表示されます。ダウンロード フォルダーでも、CSV ファイルにアクセスできます。

   > [!NOTE]
   > 1 つの監査ログ検索から CSV ファイルに最大 50,000 エントリをダウンロードできます。 CSV ファイルに 50,000 個のエントリがダウンロードされている場合は、検索条件を満たしたイベントが 50,000 件を超えると想定できます。 この制限を超えてエクスポートするには、より狭い日付範囲を使用して監査ログ レコードの数を減らしてみてください。 50,000 を超えるエントリをエクスポートするには、より小さい日付範囲で複数の検索を実行する必要がある場合があります。

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>手順 2: Power Query エディターを使用してエクスポートされた監査ログを書式設定する

次の手順では、Excel のPower Query エディターの JSON 変換機能を使用して **、AuditData** 列の JSON オブジェクト内の各プロパティを独自の列に分割します。 次に、列をフィルター処理して、特定のプロパティの値に基づいてレコードを表示します。 これにより、探している特定の監査データをすばやく見つけることができます。

1. Excel for Office 365、Excel 2019、またはExcel 2016で空のブックを開きます。

2. [ **データ** ] タブの [ **変換データの取得] リボン グループ &で** 、[ **テキスト/CSV から**] をクリックします。

    ![[データ] タブで、[テキスト/CSV から] をクリックします。](../media/JSONTransformOpenCSVFile.png)

3. 手順 1. でダウンロードした CSV ファイルを開きます。

4. 表示されるウィンドウで、[ **データの変換**] をクリックします。

   ![[データの変換] をクリックします。](../media/JSONOpenPowerQuery.png)

   CSV ファイルはクエリ エディターで開 **きます**。 **CreationDate**、**UserIds、Operations**、**AuditData** の 4 つの列 **があります**。 **AuditData** 列は、複数のプロパティを含む JSON オブジェクトです。 次の手順では、JSON オブジェクト内の各プロパティの列を作成します。

5. **AuditData** 列でタイトルを右クリックし、[**変換**] をクリックし、[**JSON**] をクリックします。 

   ![AuditData 列を右クリックし、[変換] をクリックして JSON を選択します。](../media/JSONTransform.png)

6. **AuditData** 列の右上隅にある展開アイコンをクリックします。

   ![AuditData 列で、展開アイコンをクリックします。](../media/JSONTransformExpandIcon.png)

   **AuditData** 列の JSON オブジェクトのプロパティの一部が表示されます。

7. [ **その他の読み込み]** をクリックして、 **AuditData** 列の JSON オブジェクトのすべてのプロパティを表示します。

   ![[その他の読み込み] をクリックして、JSON オブジェクトのすべてのプロパティを表示します。](../media/JSONTransformLoadJSONProperties.png)

   含めたくないプロパティの横にあるチェック ボックスをオフにできます。 調査に役立たない列を削除することは、監査ログに表示されるデータの量を減らす適切な方法です。 

   > [!NOTE]
   > 前のスクリーンショットに表示された JSON プロパティ ( **[さらに読み込む**] をクリックした後) は、CSV ファイルの最初の 1,000 行の **AuditData** 列にあるプロパティに基づいています。 最初の 1,000 行の後にレコードに異なる JSON プロパティがある場合、 **AuditData** 列が複数の列に分割されている場合、これらのプロパティ (および対応する列) は含まれません。 これを防ぐには、監査ログ検索の再実行を検討し、返されるレコードが少なくなるように検索条件を絞り込みます。 もう 1 つの回避策は、**AuditData** 列で JSON オブジェクトを変換する前に、(上記の手順 5 を実行する前に) 行数を減らすために **Operations** 列の項目をフィルター処理することです。

   > [!TIP]
   > AuditData.AffectedItems などのリスト内の属性を表示するには、属性をプルする列の右上隅にある **[展開** ] アイコンをクリックし、[ **新しい行に展開**] を選択します。  そこからレコードが表示され、列の右上隅にある **[展開** ] アイコンをクリックし、属性を表示して、表示または抽出するレコードを選択できます。

8. 選択した JSON プロパティごとに追加される列のタイトルを書式設定するには、次のいずれかの操作を行います。

    - JSON プロパティの **名前を列名として使用するには、[元の列名をプレフィックスとして** 使用する] チェック ボックスをオフにします。たとえば、 **RecordType** または **SourceFileName** です。

    - [ **元の列名をプレフィックスとして使用** ] チェック ボックスをオンのままにして、列名に AuditData プレフィックスを追加します。たとえば、 **AuditData.RecordType** や **AuditData.SourceFileName などです**。

9. **[OK]** をクリックします。

    **AuditData** 列は複数の列に分割されます。 各新しい列は、AuditData JSON オブジェクトのプロパティに対応します。 列の各行には、プロパティの値が含まれています。 プロパティに値が含まれていない場合は、 *null* 値が表示されます。 Excel では、null 値を持つセルは空です。
  
10. [**ホーム**] タブで、[**読み込み&閉じる**] をクリックしてPower Query エディターを閉じ、変換された CSV ファイルを Excel ブックで開きます。

## <a name="use-powershell-to-search-and-export-audit-log-records"></a>PowerShell を使用して監査ログ レコードを検索およびエクスポートする

Microsoft Purview コンプライアンス ポータルで監査ログ検索ツールを使用する代わりに、Exchange Online PowerShell の [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) コマンドレットを使用して、監査ログ検索の結果を CSV ファイルにエクスポートできます。 次に、手順 2 で説明したのと同じ手順に従って、Power Query エディターを使用して監査ログを書式設定できます。 PowerShell コマンドレットを使用する利点の 1 つは、 *RecordType* パラメーターを使用して特定のサービスからイベントを検索できることです。 手順 2. で説明したように、PowerShell を使用して監査レコードを CSV ファイルにエクスポートする例をいくつか示します。これにより、Power Query エディターを使用して **AuditData** 列の JSON オブジェクトを変換できます。

この例では、次のコマンドを実行して、SharePoint 共有操作に関連するすべてのレコードを返します。

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

検索結果は、CreationDate、UserIds、RecordType、AuditData の 4 つの列を含む *PowerShellAuditlog* という名前の CSV ファイルにエクスポートされます。

レコード型の名前または列挙値を *RecordType* パラメーターの値として使用することもできます。 レコードの種類名とそれに対応する列挙値の一覧については、[Office 365 Management アクティビティ API スキーマ](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)の *AuditLogRecordType* テーブルを参照してください。

*RecordType* パラメーターには、1 つの値のみを含めることができます。 他のレコードの種類の監査レコードを検索するには、前の 2 つのコマンドをもう一度実行して別のレコードの種類を指定し、それらの結果を元の CSV ファイルに追加する必要があります。 たとえば、次の 2 つのコマンドを実行して、同じ日付範囲から PowerShellAuditlog.csv ファイルに SharePoint ファイル アクティビティを追加します。

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>監査ログをエクスポートして表示するためのヒント

JSON 変換機能を使用して **AuditData** 列を複数の列に分割する前と後の監査ログのエクスポートと表示のヒントと例を次に示します。

- **RecordType** 列をフィルター処理して、特定のサービスまたは機能領域のレコードのみを表示します。 たとえば、SharePoint 共有に関連するイベントを表示するには、 **14** (SharePoint 共有アクティビティによってトリガーされるレコードの列挙値) を選択します。 **RecordType** 列に表示される列挙値に対応するサービスの一覧については、「[監査ログの詳細なプロパティ」を](detailed-properties-in-the-office-365-audit-log.md)参照してください。

- **[操作] 列をフィルター処理** して、特定のアクティビティのレコードを表示します。 コンプライアンス ポータルの監査ログ検索ツールで検索可能なアクティビティに対応するほとんどの操作の一覧については、 [監査ログの検索](search-the-audit-log-in-security-and-compliance.md#audited-activities)の「監査アクティビティ」セクションを参照してください。
