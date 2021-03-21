---
title: 一般的な電子情報開示の問題のトラブルシューティング
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 365 電子情報開示の一般的な問題を解決するために実行できる基本的なトラブルシューティングOffice説明します。
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a867ed2e55c73fe4bbd890273d78cf57f4bfbd2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926547"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>一般的な電子情報開示の問題を調査、トラブルシューティング、解決する

このトピックでは、電子情報開示検索中または電子情報開示プロセスの他の場所で発生する可能性のある問題を特定して解決するために実行できる基本的なトラブルシューティング手順について説明します。 これらのシナリオの一部を解決するには、Microsoft サポートのヘルプが必要です。 Microsoft サポートに問い合わせする場合の情報は、解決手順に含まれています。

## <a name="errorissue-ambiguous-location"></a>エラー/問題: あいまいな場所

ユーザーのメールボックスの場所を検索に追加しようとして、Exchange Online Protection (EOP) ディレクトリに同じ userID を持つオブジェクトが重複または競合している場合は、次のエラーが表示されます。 `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`

### <a name="resolution"></a>解決方法

同じユーザー ID を持つ重複ユーザーまたは配布リストを確認します。

1. コンプライアンス センター [PowerShell &に接続します](/powershell/exchange/connect-to-scc-powershell)。

2. 次のコマンドを実行して、ユーザー名のすべてのインスタンスを取得します。

    ```powershell
    Get-Recipient <username>
    ```

   'useralias@contoso.com' の出力は、次のようになります。

   > 
   > |名前|RecipientType|
   > |---|---|
   > |エイリアス、ユーザー|MailUser|
   > |エイリアス、ユーザー|User|

3. 複数のユーザーが返された場合は、競合するオブジェクトを見つけて修正します。

## <a name="errorissue-search-fails-on-specific-locations"></a>エラー/問題: 特定の場所で検索が失敗する

電子情報開示またはコンテンツ検索では、次のエラーが発生する可能性があります。 `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![検索固有の場所でエラー のスクリーンショットが失敗する](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>解決方法

このエラーが表示された場合は、検索で失敗した場所を確認してから、失敗した場所でのみ検索を再実行することをお勧めします。

1. コンプライアンス センター [PowerShell &に接続し、](/powershell/exchange/connect-to-scc-powershell) 次のコマンドを実行します。

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. PowerShell 出力から、エラー フィールドまたは検索出力からのエラーの状態の詳細から、失敗した場所を表示します。

3. 失敗した場所でのみ電子情報開示検索を再試行してください。

4. これらのエラーを引き続き受け取る場合は、「失敗した場所を再試行する」を参照 [して](/Office365/SecurityCompliance/retry-failed-content-search) 、トラブルシューティングの手順を確認してください。

## <a name="errorissue-file-not-found"></a>エラー/問題: ファイルが見つかりません

SharePoint Online と One Drive For Business の場所を含む電子情報開示検索を実行すると、ファイルがサイト上にありますが、エラー `File Not Found` が表示される場合があります。 このエラーは、エクスポートの警告に表示され、errors.csvまたはスキップitems.csv。 これは、サイトでファイルが見つからない場合、またはインデックスが最新の日付でなかった場合に発生する可能性があります。 実際のエラーのテキストを次に示します (強調が追加されています)。

> 28.06.2019 10:02:19_FailedToExportItem_Failedダウンロードします。 その他の診断情報 : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Document タイプのコンテンツ 6ea52149-91cd-4965-b5bb-82ca6a3ec9be からダウンロードできなかった。 相関 ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 --->.SharePoint.Client.ServerException: ***ファイルが見つかりません***。 at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---

### <a name="resolution"></a>解決方法

1. 検索で識別された場所を確認して、ファイルの場所が正しく、検索場所に追加されていることを確認します。

2. サイト、ライブラリ、または[](/sharepoint/crawl-site-content)リストのクロールと再インデックスの手動要求の手順を使用して、サイトのインデックスを再作成します。

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>エラー/問題: 受信者が見つからないため、検索が失敗する

電子情報開示の検索が失敗し、エラーが発生しました `recipient not found` 。 このエラーは、オブジェクトが同期されていないため、ユーザー オブジェクトが Exchange Online Protection (EOP) で見つからない場合に発生する可能性があります。

### <a name="resolution"></a>解決方法

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する

2. 次のコマンドを実行して、ユーザーが Exchange Online Protection と同期されている場合は、次のコマンドを実行します。

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. ユーザーの質問のメール ユーザー オブジェクトが必要です。 何も返されなかった場合は、ユーザー オブジェクトを調査します。 オブジェクトを同期できない場合は、Microsoft サポートにお問い合わせください。

## <a name="errorissue-exporting-search-results-is-slow"></a>エラー/問題: 検索結果のエクスポートが遅い

セキュリティとコンプライアンス センターで電子情報開示またはコンテンツ検索から検索結果をエクスポートする場合、ダウンロードに予想以上の時間がかかります。  ダウンロードするデータの量を確認し、エクスポート速度を上げすることができます。

### <a name="resolution"></a>解決方法

1. コンプライアンス センター [PowerShell &に接続し、](/powershell/exchange/connect-to-scc-powershell) 次のコマンドを実行します。

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. SearchResults パラメーターと SearchStatistics パラメーターで、ダウンロードするデータの量を検索します。

3. 次のコマンドを実行します。

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. 結果フィールドで、エクスポートされたデータを検索し、発生したエラーを表示します。

5. コンテンツをエクスポートしたディレクトリにある trace.log ファイルで、エラーが発生した場合はチェックします。

6. それでも問題が発生する場合は、結果の大きなセットを返す検索を小さな検索に分割する方法を検討してください。 たとえば、検索クエリで日付範囲を使用して、より速くダウンロードできる結果の小さなセットを返します。

## <a name="errorissue-internal-server-error-500-occurred"></a>エラー/問題: "内部サーバー エラー (500) が発生しました"

電子情報開示検索を実行する場合、"内部サーバー エラー (500) が発生しました"のようなエラーで検索が継続的に失敗する場合は、特定のメールボックスの場所でのみ検索を再実行する必要があります。

![内部サーバー エラー 500 スクリーンショット](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>解決方法

1. 検索を小さな検索に分割し、もう一度検索を実行します。  日付範囲を小さくするか、検索する場所の数を制限してみてください。

2. コンプライアンス センター [PowerShell &に接続し、](/powershell/exchange/connect-to-scc-powershell) 次のコマンドを実行します。

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. 結果とエラーの出力を確認します。

4. trace.log ファイルを確認します。 検索結果をエクスポートしたフォルダーと同じフォルダーにあります。

5. Microsoft サポートにお問い合わせください。

## <a name="errorissue-holds-dont-sync"></a>エラー/問題: 保留は同期されません

電子情報開示ケースホールド ポリシー同期配布エラー。 エラーは次のように読み取ります。

> "リソース: ポリシーの展開に予想以上に時間がかかります。 最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。

### <a name="resolution"></a>解決方法

1. コンプライアンス センター [PowerShell &に接続](/powershell/exchange/connect-to-scc-powershell) し、電子情報開示ケースホールドに対して次のコマンドを実行します。

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    アイテム保持ポリシーの場合は、次のコマンドを実行します。

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. DistributionDetail パラメーターの値を調べて、次のようなエラーを確認します。

   > エラー: リソース: ポリシーの展開に予想以上に時間がかかります。 最終的な展開状態を更新するにはさらに 2 時間かかる場合があります。数時間後に確認してください。

3. 問題のポリシーで RetryDistribution パラメーターを実行してみてください。

   電子情報開示ケースホールドの場合:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   アイテム保持ポリシーの場合:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Microsoft サポートにお問い合わせください。

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>エラー: "HTTP 条件付きヘッダーを使用して指定された条件が満たされていません"

電子情報開示エクスポート ツールを使用して検索結果をダウンロードすると、次のエラーが表示される可能性があります。これは一時的なエラーであり、通常は Azure Storage の場所で `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 発生します。

### <a name="resolution"></a>解決方法

この問題を解決するには、検索結果の [ダウンロードを](export-search-results.md#step-2-download-the-search-results)再試行し、電子情報開示エクスポート ツールを再起動します。

## <a name="errorissue-downloaded-export-shows-no-results"></a>エラー/問題: ダウンロードしたエクスポートに結果が表示されません

エクスポートが正常に完了すると、エクスポート ツールを介したダウンロードが完了すると、結果にファイルが 0 件表示されます。

### <a name="resolution"></a>解決方法

これはクライアント側の問題であり、修復するには、次の手順を試してください。

1. 別のクライアント/コンピューターを使用してダウンロードしてみてください。

2. 必ずローカル ドライブにダウンロードしてください。

3. ウイルス スキャナーが実行されていないか確認します。

4. 同じフォルダーまたは任意の親フォルダーに他のエクスポートがダウンロードしなかからなことを確認します。

5. 前の手順が機能しない場合は、zipping と重複除外を無効にします。

6. これが機能する場合は、ローカル ウイルス スキャナーまたはディスクの問題が原因で問題が発生します。