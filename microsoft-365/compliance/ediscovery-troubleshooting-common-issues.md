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
description: Office 365 電子情報開示の一般的な問題を解決するために実行できる基本的なトラブルシューティング手順について説明します。
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b96ed80ba9f347616fd364b3b97ac960cdaeb8e
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357997"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>一般的な電子情報開示の問題を調査、トラブルシューティング、および解決する

このトピックでは、電子情報開示の検索中に発生する可能性のある問題を特定して解決するために実行できる基本的なトラブルシューティング手順について説明します。 これらのシナリオのいくつかを解決するには、Microsoft サポートのヘルプが必要です。 Microsoft サポートに連絡するタイミングについては、「解決手順」を参照してください。

## <a name="errorissue-ambiguous-location"></a>エラー/問題: あいまいな場所

ユーザーのメールボックスの場所を検索に追加しようとしたときに、Exchange Online Protection (EOP) ディレクトリに同じ userID を持つオブジェクトが重複しているか競合している場合、次のエラーが表示され `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` ます。

### <a name="resolution"></a>解決方法

同じユーザー ID を持つ重複したユーザーまたは配布リストをチェックします。

1. [セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)に接続します。

2. ユーザー名のすべてのインスタンスを取得するには、次のコマンドを実行します。

    ```powershell
    Get-Recipient <username>
    ```

   ' Useralias@contoso.com ' の出力は次のようになります。

   > 
   > |名前|RecipientType|
   > |---|---|
   > |Alias、User|Enable-mailuser|
   > |Alias、User|ユーザー|

3. 複数のユーザーが返された場合は、競合しているオブジェクトを見つけて修正します。

## <a name="errorissue-search-fails-on-specific-locations"></a>エラー/問題: 特定の場所で検索が失敗する

電子情報開示またはコンテンツの検索では、次のエラーが発生することがあります。
>この検索は (#) エラーで完了しました。  失敗した場所で検索を再試行しますか?

![検索固有の場所が失敗するエラーのスクリーンショット](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>解決方法

このエラーが表示された場合は、検索で失敗した場所を確認し、失敗した場所でのみ検索を実行することをお勧めします。

1. [セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)に接続し、次のコマンドを実行します。

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. PowerShell 出力から、失敗した場所を [エラー] フィールドに表示するか、または検索出力からエラーが発生した状態の詳細を確認します。

3. 失敗した場所のみで電子情報開示検索を再試行します。

4. 引き続きこれらのエラーが表示される場合は、「その他のトラブルシューティング手順のために [失敗した場所を再試行](https://docs.microsoft.com/Office365/SecurityCompliance/retry-failed-content-search) する」を参照してください。

## <a name="errorissue-file-not-found"></a>エラー/問題: ファイルが見つかりません

SharePoint Online を含む電子情報開示検索を実行する際に、ビジネスの場所として1つのドライブを使用すると、 `File Not Found` ファイルがサイトに配置されていてもエラーが発生することがあります。 このエラーは、エクスポート時に警告が表示され、items.csv errors.csv またはスキップされます。 これは、サイトでファイルが見つからない場合、またはインデックスが古くなっている場合に発生することがあります。 実際のエラーのテキストを次に示します (強調が追加されています)。

> 28.06.2019 10:02: コンテンツをダウンロードするには19_FailedToExportItem_Failed します。 その他の診断情報: 6ea52149-91cd-コンテンツのダウンロードに失敗しました。 b5bb-82ca6a3ec9be Document of the be of the of the type of Document。 関連付け Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32。 ServerErrorCode:-2147024894 >---例外: ***ファイルが見つかりません***。 ProcessResponseStream (Stream responseStream) () で、内部例外スタックトレース---の最後に (Stream) を呼び出します。の場合は、内部例外スタックトレースの末尾に---します。

### <a name="resolution"></a>解決方法

1. 検索で特定された場所を調べて、ファイルの場所が正しいことと、検索場所に追加されていることを確認します。

2. サイト [、ライブラリ、またはリストのインデックスを再作成するための、手動要求](https://docs.microsoft.com/sharepoint/crawl-site-content) の手順を使用します。

## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>エラー/問題: 受信者が見つからないため、検索が失敗する

電子情報開示の検索が失敗し、エラーが発生し `recipient not found` ます。 このエラーは、オブジェクトが同期されていないために、Exchange Online Protection (EOP) でユーザーオブジェクトが見つからない場合に発生する可能性があります。

### <a name="resolution"></a>解決方法

1. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) に接続する

2. ユーザーが Exchange Online Protection と同期されているかどうかを確認するには、次のコマンドを実行します。

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. ユーザーに質問するメールユーザーオブジェクトが存在する必要があります。 何も返されない場合は、user オブジェクトを調査します。 オブジェクトを同期できない場合は、Microsoft サポートに連絡してください。

## <a name="errorissue-exporting-search-results-is-slow"></a>エラー/問題: 検索結果のエクスポートが遅くなっています

セキュリティ/コンプライアンスセンターの電子情報開示またはコンテンツ検索からの検索結果をエクスポートする場合、ダウンロードには予想より時間がかかります。  ダウンロードするデータの量を確認して、エクスポートの速度を上げることができます。

### <a name="resolution"></a>解決方法

1. この記事に記載されている手順を使用して、 [ダウンロード速度を上げ](https://docs.microsoft.com/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)ます。

2. それでも問題が解決しない場合は、 [セキュリティに & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) に接続し、次のコマンドを実行します。

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

3. SearchResults パラメーターと Searchresults パラメーターにダウンロードされるデータの量を検索します。

4. 次のコマンドを実行します。

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

5. [結果] フィールドに、エクスポートされたデータを検索し、発生したエラーがあるかどうかを確認します。

6. エラーが発生した場合に、コンテンツをエクスポートしたディレクトリにある、トレースログファイルを確認します。

## <a name="errorissue-internal-server-error-500-occurred"></a>エラー/問題: "内部サーバーエラー (500) が発生しました"

電子情報開示検索を実行するときに、"内部サーバーエラー (500) が発生しました" と同様のエラーで検索が引き続き失敗する場合は、特定のメールボックスの場所でのみ検索を再実行する必要がある場合があります。

![内部サーバーエラー500スクリーンショット](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>解決方法

1. 検索を小さな検索に分割して、検索を再度実行します。  短い日付範囲を使用するか、検索する場所の数を制限してください。

2. [セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)に接続し、次のコマンドを実行します。

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. 結果とエラーの出力を確認します。

4. トレースログファイルを調べます。 これは、検索結果をエクスポートしたのと同じフォルダーに配置されます。

5. Microsoft サポートにお問い合わせください。

## <a name="errorissue-holds-dont-sync"></a>エラー/問題: 保留が同期しない

電子情報開示ケース保持ポリシー同期の配布エラー。 エラーは次のとおりです。

> リソース: ポリシーの展開に予想よりも時間がかかっています。 最終的な展開状態を更新するのに2時間かかる場合があります。そのため、しばらくしてから数時間後にもう一度確認してください。

### <a name="resolution"></a>解決方法

1. [セキュリティ & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)に接続し、電子情報開示ケースホールドに対して次のコマンドを実行します。

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    アイテム保持ポリシーの場合は、次のコマンドを実行します。

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. 次のようなエラーが発生した場合は、"指定した値を入力してください" というエラーを示します。

   > エラー: リソース: ポリシーの展開に予想よりも時間がかかります。 最終的な展開状態を更新するのに2時間かかる場合があります。そのため、しばらくしてから数時間後にもう一度確認してください。

3. 対象のポリシーで、RetryDistribution パラメーターを実行してみてください。

   電子情報開示ケース保持の場合:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   アイテム保持ポリシーの場合:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Microsoft サポートにお問い合わせください。

## <a name="see-also"></a>関連項目

- [コンテンツの場所エラーを回避するためのヒント](retry-failed-content-search.md#tips-to-avoid-content-location-errors)
