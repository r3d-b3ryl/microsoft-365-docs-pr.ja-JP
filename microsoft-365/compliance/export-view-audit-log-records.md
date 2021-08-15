---
title: 監査ログ レコードをエクスポート、構成、表示する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: この記事では、監査ログ レコードのエクスポート、構成、およびMicrosoft 365について学習します。
ms.openlocfilehash: 14bdd1a8a2576f622c4be63f463e5d42111fc02cd518cf488a8e4df5d39b1241
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53905790"
---
# <a name="export-configure-and-view-audit-log-records"></a>監査ログ レコードをエクスポート、構成、表示する

監査ログを検索して検索結果を CSV ファイルにダウンロードした後、ファイルには **AuditData** という名前の列が含まれます。各イベントに関する追加情報が含まれます。 この列のデータは JSON オブジェクトとして書式設定され、コンマで区切られた *property:value* ペアとして構成された複数のプロパティが含まれます。 Excel の Power Query Editor の JSON 変換機能を使用して **、AuditData** 列の JSON オブジェクトの各プロパティを複数の列に分割して、各プロパティに独自の列を設定できます。 これにより、これらのプロパティの 1 つ以上を並べ替え、フィルター処理し、探している特定の監査データをすばやく見つけるのに役立ちます。

## <a name="step-1-export-audit-log-search-results"></a>手順 1: 監査ログの検索結果をエクスポートする

最初の手順は、監査ログを検索し、その結果をコンマ区切り値 (CSV) ファイルにローカル コンピューターにエクスポートすることです。
  
1. 必要に [応じて監査ログ検索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) を実行し、必要に応じて検索条件を変更します。目的の結果が得られます。

2. [結果 **のエクスポート] をクリック** し、[すべての結果 **をダウンロードする] を選択します**。 

   ![[すべての結果をダウンロードする] をクリックします。](../media/ExportAuditSearchResults.png)

   このオプションは、手順 1 で実行した監査ログ検索からすべての監査レコードをエクスポートし、未加工データを監査ログから CSV ファイルにダウンロードします。 

   ウィンドウの下部にメッセージが表示され、CSV ファイルを開くまたは保存するように求めるメッセージが表示されます。 

3. [ **名前を>保存] をクリックし** 、CSV ファイルをローカル コンピューターに保存します。 多くの検索結果をダウンロードするには、しばらく時間が必要です。 これは通常、すべてのアクティビティまたは広い日付範囲を検索する場合に当てはまっています。 CSV ファイルのダウンロードが完了すると、ウィンドウの下部にメッセージが表示されます。

   ![CSV ファイルのダウンロードが完了すると表示されるメッセージ](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > 1 回の監査ログ検索から最大 50,000 エントリを CSV ファイルにダウンロードできます。 CSV ファイルに 50,000 エントリがダウンロードされている場合は、検索条件を満たすイベントが 50,000 件を超える可能性があります。 この制限を超える値をエクスポートするには、日付範囲を使用して監査ログ レコードの数を減らしてみてください。 50,000 を超えるエントリをエクスポートするには、日付範囲が小さい複数の検索を実行する必要がある場合があります。

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>手順 2: Power Query Editor を使用してエクスポートされた監査ログを書式設定する

次の手順では、Excel の Power Query Editor の JSON 変換機能を使用して **、[AuditData]** 列の JSON オブジェクトの各プロパティを独自の列に分割します。 次に、列をフィルター処理して、特定のプロパティの値に基づいてレコードを表示します。 これにより、探している特定の監査データをすばやく見つけるのに役立ちます。

1. 2019 年または 2019 年Excel 2019 年Office 365、またはExcelのブックを開Excel 2016。

2. [データ **] タブの** [データ変換 **&]** リボン グループで、[テキスト/CSV から] **をクリックします**。

    ![[データ] タブで、[テキスト/CSV から] をクリックします。](../media/JSONTransformOpenCSVFile.png)

3. 手順 1 でダウンロードした CSV ファイルを開きます。

4. 表示されるウィンドウで、[データの変換] **をクリックします**。

   ![[データの変換] をクリックします。](../media/JSONOpenPowerQuery.png)

   CSV ファイルはクエリ エディターで **開きます**。 次の 4 つの列があります。CreationDate、UserIds、Operations、AuditData です。     **AuditData 列は**、複数のプロパティを含む JSON オブジェクトです。 次の手順では、JSON オブジェクト内の各プロパティの列を作成します。

5. **[AuditData]** 列でタイトルを右クリックし、[変換] を **クリックし****、[JSON] をクリックします**。 

   ![[AuditData] 列を右クリックし、[変換] をクリックし、[JSON] を選択します。](../media/JSONTransform.png)

6. **[AuditData]** 列の右上隅にある展開アイコンをクリックします。

   ![[AuditData] 列で、[展開] アイコンをクリックします。](../media/JSONTransformExpandIcon.png)

   **AuditData** 列の JSON オブジェクトのプロパティの一部が表示されます。

7. [ **詳細を読み込** む] をクリックして **、[AuditData]** 列の JSON オブジェクトのすべてのプロパティを表示します。

   ![JSON オブジェクトのすべてのプロパティを表示するには、[その他の読み込み] をクリックします。](../media/JSONTransformLoadJSONProperties.png)

   含めたくないプロパティの横にあるチェック ボックスをオフにできます。 調査に役立てない列を削除すると、監査ログに表示されるデータ量を減らすのに役立ちます。 

   > [!NOTE]
   > 前のスクリーンショットに表示された JSON プロパティ ([追加の読み込み] をクリックした **後)** は、CSV ファイルの最初の 1,000 行の **AuditData** 列にあるプロパティに基づいて作成されます。 最初の 1,000 行の後にレコードに異なる JSON プロパティがある場合 **、AuditData** 列が複数の列に分割されている場合、これらのプロパティ (および対応する列) は含まれません。 これを防ぐには、監査ログの検索を再実行し、検索基準を絞り込み、返されるレコードを少なくします。 もう 1 つの回避策は、[ **操作** ] 列内のアイテムをフィルター処理して、(上記の手順 5 を実行する前に) **AuditData** 列で JSON オブジェクトを変換する前に行数を減らすことです。

   > [!TIP]
   > AuditData.AffectedItems などのリスト内の属性を表示するには、属性をプルする列の右上隅にある [展開] アイコンをクリックし、[新しい行に展開] を選択します。  そこからレコードが作成され、列の右上隅にある [展開] アイコンをクリックし、属性を表示し、表示または抽出する属性を選択できます。

8. 次のいずれかの操作を実行して、選択した JSON プロパティごとに追加される列のタイトルを書式設定します。

    - [元の **列名をプレフィックスとして使用** する] チェック ボックスをオフにして、JSON プロパティの名前を列名として使用します。たとえば **、RecordType または** **SourceFileName**.

    - [元の **列名をプレフィックスとして** 使用する] チェック ボックスをオンのままにして、列名に AuditData プレフィックスを追加します。たとえば **、AuditData.RecordType または** **AuditData.SourceFileName** などです。

9. **[OK]** をクリックします。

    **AuditData 列** は複数の列に分割されます。 新しい各列は、AuditData JSON オブジェクトのプロパティに対応します。 列の各行には、プロパティの値が含まれる。 プロパティに値が含まれている場合は *、null 値が* 表示されます。 このExcel、null 値を持つセルは空です。
  
10. [ホーム **] タブで**、[読み込み&閉じる] をクリックして Power Query Editor を閉じ、変換された CSV ファイルをブックExcelします。 

## <a name="use-powershell-to-search-and-export-audit-log-records"></a>PowerShell を使用して監査ログ レコードを検索およびエクスポートする

セキュリティ & コンプライアンス センターの監査ログ検索ツールを使用する代わりに、Exchange Online PowerShell の[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)コマンドレットを使用して、監査ログ検索の結果を CSV ファイルにエクスポートできます。 次に、手順 2 で説明したのと同じ手順に従って、Power Query エディターを使用して監査ログを書式設定できます。 PowerShell コマンドレットを使用する利点の 1 つは *、RecordType* パラメーターを使用して特定のサービスからイベントを検索できるという利点です。 手順 2 で説明したように、PowerShell を使用して監査レコードを CSV ファイルにエクスポートして、Power Query エディターを使用して **AuditData** 列の JSON オブジェクトを変換する例を以下に示します。

この例では、次のコマンドを実行して、共有操作に関連SharePoint返します。

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

検索結果は、CreationDate、UserIds、RecordType、AuditData の 4 つの列を含む *PowerShellAuditlog* という名前の CSV ファイルにエクスポートされます。

レコードの種類の名前または列挙値を RecordType パラメーターの値 *として使用* することもできます。 レコードの種類名とそれに対応する列挙値の一覧については、「管理アクティビティ API スキーマ」の *AuditLogRecordType* [Office 365を参照してください](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)。

RecordType パラメーターには、1 つの値 *のみを含* めできます。 他のレコードの種類の監査レコードを検索するには、前の 2 つのコマンドを再度実行して別のレコードの種類を指定し、それらの結果を元の CSV ファイルに追加する必要があります。 たとえば、次の 2 つのコマンドを実行して、同SharePointの日付範囲のファイル アクティビティをファイルに追加PowerShellAuditlog.csvします。

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>ヒントログのエクスポートと表示の詳細

JSON 変換機能を使用して **AuditData** 列を複数の列に分割する前と後に監査ログをエクスポートおよび表示するヒントと例を次に示します。

- **[RecordType] 列を** フィルター処理して、特定のサービスまたは機能領域のレコードのみを表示します。 たとえば、共有に関連するイベントSharePoint表示するには **、14** (共有アクティビティによってトリガーされるレコードの列挙SharePoint選択します。 **[RecordType]** 列に表示される列挙値に対応するサービスの一覧については、「監査ログの詳細なプロパティ」[を参照してください](detailed-properties-in-the-office-365-audit-log.md)。

- [操作] **列を** フィルター処理して、特定のアクティビティのレコードを表示します。 セキュリティ & コンプライアンス センターの監査ログ検索ツールで検索可能なアクティビティに対応するほとんどの操作の一覧については、「セキュリティ & コンプライアンス センターの監査ログを検索する」の「監査アクティビティ [」セクションを](search-the-audit-log-in-security-and-compliance.md#audited-activities)参照してください。