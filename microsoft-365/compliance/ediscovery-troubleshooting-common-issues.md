---
title: Troublshooting の一般的な電子情報開示の問題
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Office 365 eDiscovery の一般的な問題を調査、トラブルシューティング、解決します。
siblings_only: true
ms.openlocfilehash: db355067aa4e3fc41541e6414b59c92aaac1b5b3
ms.sourcegitcommit: 75c8f89049081f08852699c8d51c3a07b12165da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2019
ms.locfileid: "37207296"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>一般的な電子情報開示の問題を調査、トラブルシューティング、および解決する

このトピックでは、電子情報開示の検索中に発生する可能性のある問題を特定して解決するために実行できる基本的なトラブルシューティング手順について説明します。 これらのシナリオのいくつかを解決するには、カスタマーサポートサービス (CSS) のヘルプが必要です。 CSS に連絡するタイミングの詳細については、「解決手順」を参照してください。

## <a name="errorissue-ambiguous-location"></a>エラー/問題のあいまいな場所

このエラーメッセージが表示されるのは、Exchange Online Protection ( `(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous"` EOP) で、ユーザーのメールボックスの場所を検索に追加しようとしたときに、重複した、または競合しているオブジェクトが存在する場合です。名簿.

### <a name="resolution"></a>解決策

同じユーザー ID を持つ重複したユーザーまたは配布リストをチェックします。

1. [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) に接続する
2. ユーザー名のすべてのインスタンスを取得するには、次のように入力します。

```powershell
Get-Recipient <username>
```

' Useralias@contoso.com ' の出力は、

> 
> |名前  |RecipientType  |
> |---------|---------|
> |Alias、User     |Enable-mailuser         |
> |Alias、User     |ユーザー         |

3. 複数のユーザーが返された場合は、競合しているオブジェクトを見つけて修正します。

## <a name="errorissue-search-fails-on-specific-locations"></a>特定の場所でエラー/問題の検索が失敗する

電子情報開示またはコンテンツの検索では、次のエラーが発生することがあります。
>この検索は (#) エラーで完了しました。  失敗した場所で検索を再試行しますか?

![検索の特定の場所が失敗するエラーのスクリーンショット]( media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>解決策

このエラーが表示された場合は、検索で失敗した場所を確認し、失敗した場所でのみ検索を再実行することをお勧めします。

1. [Exchange Online Protection の Powershell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続します。
1. 種類:

```powershell
Get-Compliancesearch searchname|fl 
```

3. PowerShell 出力から、失敗した場所を [エラー] フィールドに表示するか、または検索出力からエラーが発生した状態の詳細を確認します。
1. 失敗した場所のみで電子情報開示検索を再試行します。
1. 引き続きこれらのエラーが表示される場合は、「その他のトラブルシューティング手順で[失敗した場所を再試行](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/retry-failed-content-search)する」を参照してください。

## <a name="errorissue-file-not-found"></a>エラー/問題ファイルが見つかりません

SharePoint Online を含む電子情報開示検索を実行する際に、ビジネスの場所として 1 `File Not Found`つのドライブを使用すると、ファイルがサイトに配置されていてもエラーが発生することがあります。 このエラーは、エクスポートの警告とエラー .csv またはスキップされたアイテムです。これは、ファイルがサイトに存在しないか、インデックスが古くなっている場合に発生することがあります。 強調が追加された実際のエラーのテキストを次に示します。
  
> 28.06.2019 10:02: 19_FailedToExportItem_Failed をダウンロードしてコンテンツをダウンロードします。 その他の診断情報: 6ea52149-91cd-コンテンツのダウンロードに失敗しました。 b5bb-82ca6a3ec9be Document of the be of the of the type of Document。 関連付け Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32。 ServerErrorCode:-2147024894 >---例外:***ファイルが見つかりません***。 ProcessResponseStream (Stream responseStream) () で、内部例外スタックトレース---の最後に (Stream) を呼び出します。の場合は、内部例外スタックトレースの末尾に---します。

### <a name="resolution"></a>解決策

1. 検索で特定された場所を調べて、ファイルの場所が正しいことと、検索場所に追加されていることを確認します。
2. サイト[、ライブラリ、またはリストの](https://docs.microsoft.com/en-us/sharepoint/crawl-site-content)インデックスを再作成するための手動要求の手順を使用します。

## <a name="errorissue-search-fails-recipient-not-found"></a>エラー/問題の検索で受信者が見つからない

電子情報開示の検索`recipient not found`がエラーで失敗する。 このエラーは、オブジェクトが同期されていないために、Exchange Online Protection (EOP) でユーザーオブジェクトが見つからない場合に発生する可能性があります。

### <a name="resolution"></a>解決策

1. [Exchange Online Protection の PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続します。
1. ユーザーオブジェクトが Exchange Online Protection の種類と同期されているかどうかを確認します。

```powershell
Get-Recipient userId|fl
```

3. ユーザーの質問には enable-mailuser オブジェクトが必要です。 何も返されない場合は、user オブジェクトを調査します。 オブジェクトを同期できない場合は、CSS に接続します。

## <a name="errorissue-exporting-search-results-is-slow"></a>検索結果のエクスポートに時間がかかるエラー/問題

セキュリティ/コンプライアンスセンターの電子情報開示またはコンテンツ検索からの検索結果をエクスポートする場合、ダウンロードには予想より時間がかかります。  ダウンロードするデータの量を確認して、エクスポートの速度を上げることができます。

### <a name="resolution"></a>解決策

1.  この記事に記載されている手順を使用して、[ダウンロード速度を上げ](https://docs.microsoft.com/en-us/office365/securitycompliance/increase-download-speeds-when-exporting-ediscovery-results)ます。
2.  それでも問題が解決しない場合は、 [Exchange Online Protection の PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続し、次のように入力します。

```powershell
Get-ComplianceSearch searchname\fl
```

4. SearchResults パラメーターと Searchresults パラメーターにダウンロードされるデータの量を検索します。
5. 種類:

```powershell
Get-ComplianceSearchAction |fl
```

6. [結果] フィールドに、エクスポートされたデータを検索し、発生したエラーがあるかどうかを確認します。
7. エラーが発生した場合に、コンテンツをエクスポートしたディレクトリにある、トレースログファイルを確認します。

## <a name="errorissue-internal-server-error-500-occurred"></a>エラー/問題 "内部サーバーエラー (500) が発生しました"

電子情報開示検索を実行するときに、"内部サーバーエラー (500) が発生しました" と同様のエラーで検索が繰り返し失敗する場合は、特定のメールボックスの場所でのみ検索を再実行する必要があります。

![内部サーバーエラー500スクリーンショット](media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>解決策

1. 検索を小さな検索に分割して、検索を再度実行します。  短い日付範囲を使用するか、検索する場所の数を制限してください。
2. [Exchange Online Protection の PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続し、次のように入力します。

```powershell
Get-ComplianceSearch searchname |fl
```

3. 結果とエラーの出力を確認します。
3. トレースログファイルを調べます。 エクスポートをに送信したのと同じフォルダーに配置されます。
4. サポートの CSS に問い合わせてください。

## <a name="errorissue-holds-dont-sync"></a>エラー/問題保持が同期しない

電子情報開示ケース保持ポリシー同期の配布エラー。 エラーは次のとおりです。

> リソース: ポリシーの展開に予想よりも時間がかかっています。 最終的な展開状態を更新するには2時間かかることがあります。そのため、数時間後に確認してください。

### <a name="resolution"></a>解決策

1.  [Exchange Online Protection の PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)に接続し、次のように入力します。

```powershell
Get-RetentionCompliancePolicy  policyname - Distributiondetail|fl
```

2. 次のようなエラーが発生した場合は、"指定した値を入力してください" というエラーを示します。

> エラーが存在する場合は、PG へのエスカレーションを作成して、手動による強制的な再同期をポリシーに適用します。

3. 連絡先 CSS。

## <a name="see-also"></a>関連項目
- [コンテンツの場所エラーを回避するためのヒント](https://docs.microsoft.com/en-us/microsoft-365/compliance/retry-failed-content-search%23tips-to-avoid-content-location-errors)