---
title: 電子情報開示で部分的にインデックスが作成されたアイテムの調査
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: 部分的にインデックスが作成されたアイテム (インデックスのないアイテムとも呼ばれる) を組織内の Exchange、SharePoint、OneDrive for Business から管理する方法について説明します。
ms.openlocfilehash: 6a2a1d042c52a445538903fd7db9fc54305e6c13
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655451"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>電子情報開示で部分的にインデックスが作成されたアイテムの調査

Microsoft 365 コンプライアンス センターから実行する電子情報開示検索では、検索を実行すると、部分的にインデックスが作成されたアイテムが推定検索結果に自動的に含まれます。 部分的にインデックスが作成されたアイテムは、何らかの理由で検索用に完全にはインデックスが作成されなかった SharePoint および OneDrive for Business サイト上の Exchange メールボックス アイテムとドキュメントです。 ほとんどの電子メール メッセージとサイト ドキュメントは、電子メール メッセージのインデックス作成の制限に含むため、正常にインデックス [が作成されます](limits-for-content-search.md#indexing-limits-for-email-messages)。 ただし、一部のアイテムは、これらのインデックス作成の制限を超え、部分的にインデックスが作成されます。 電子情報開示検索を実行すると、アイテムを検索用にインデックス付けできない他の理由と、部分的にインデックスが作成されたアイテムとして返される理由を次に示します。
  
- 電子メール メッセージには、イメージ ファイルなどの有効なハンドラーのない添付ファイルがあります。これは、部分的にインデックスが作成された電子メール アイテムの最も一般的な原因です。

- 電子メール メッセージに添付されているファイルが多すぎます。

- 電子メール メッセージに添付されているファイルが大きすぎます。

- この種のファイルのインデックス付けはサポートされているが、特定のファイルでインデックス付けエラーが発生した。

規模は異なりますが、大部分の組織のお客様は、コンテンツのボリュームが 1% 未満で、部分的にインデックスが作成されるコンテンツのサイズが 12% 未満です。 ボリュームとサイズの違いは、サイズが大きいファイルの方が、完全にインデックスを作成できないコンテンツを含む可能性が高いからです。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>部分的にインデックスが作成されたアイテムの数が検索で変更される理由

電子情報開示検索を実行すると、検索された場所にある部分的にインデックスが作成されたアイテムの総数とサイズが、検索の詳細な統計情報に表示される検索結果の統計情報に表示されます。 これらは、検索統計では  *インデックスのないアイテム*  と呼ばれる点に注意してください。 検索結果で返される部分的にインデックスが作成されたアイテムの数に影響を与えるいくつかの点を次に示します。
  
- アイテムが部分的にインデックス付けされ、検索クエリに一致する場合は、検索結果アイテムのカウント (およびサイズ) と部分的にインデックスが作成されたアイテムの両方に含まれます。 ただし、同じ検索の結果がエクスポートされる場合、アイテムは検索結果のセットにのみ含まれます。部分的にインデックスが作成されたアイテムには含まれません。

- (キーワード クエリに含めるか、条件を使用して) 検索クエリの日付範囲を指定した場合、日付範囲と一致しない部分的にインデックスが作成されたアイテムは、部分的にインデックスが作成されたアイテムの数には含まれません。 日付範囲内にある部分的にインデックスが作成されたアイテムは、インデックス付きアイテムの数に含まれます。

  > [!NOTE]
  > SharePoint および OneDrive サイトにある部分的にインデックスが作成されたアイテムは、検索の詳細な統計情報に表示される部分的にインデックスが作成されたアイテムの推定には含まれません。 ただし、部分的にインデックスが作成されたアイテムは、電子情報開示検索の結果をエクスポートするときにエクスポートできます。 たとえば、サイトのみを検索する場合、部分的にインデックスが作成されたアイテムの推定数は 0 になります。
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>組織内の部分的にインデックスが作成されたアイテムの比率の計算

部分的にインデックスが作成されたアイテムに対する組織の露出を理解するために、(空白のキーワード クエリを使用して) すべてのメールボックス内のすべてのコンテンツの検索を実行できます。 次の例では、完全にインデックスが作成されたアイテムは 56,208 (4,830 MB)、部分的にインデックスが作成されたアイテムは 470 (316 MB) です。
  
![部分的にインデックスが作成されたアイテムを示す検索統計の例](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
次の計算を使用して、部分的にインデックスが作成されたアイテムの割合を確認できます。
  
 **組織内の部分的にインデックスが作成されたアイテムの比率を計算するには、次の式を使用します。**

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

前の例の検索結果を使用すると、すべてのメールボックス アイテムの 0.84% が部分的にインデックス付けされます。
  
 **組織内の部分的にインデックスが作成されたアイテムのサイズの割合を計算するには、次の式を使用します。**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

そのため、前の例では、メールボックス アイテムの合計サイズの 6.54% が部分的にインデックスが作成されたアイテムのサイズです。 前に説明したように、ほとんどの組織のお客様は、コンテンツのボリュームが 1% 未満で、部分的にインデックスが作成されたコンテンツのサイズが 12% 未満です。

## <a name="working-with-partially-indexed-items"></a>部分的にインデックスが作成されたアイテムを操作する

部分的にアイテムを調べて、関連情報が含まれているのを確認する必要がある場合は、部分的にインデックス[](export-a-content-search-report.md)が作成されたアイテムに関する情報を含むコンテンツ検索レポートをエクスポートできます。 コンテンツ検索レポートをエクスポートする場合は、部分的にインデックスが作成されたアイテムを含むエクスポート オプションのいずれかを選択してください。
  
![部分的にインデックスが作成されたアイテムをエクスポートする 2 番目または 3 番目のオプションを選択する](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
これらのオプションのいずれかを使用して電子情報開示検索結果または検索レポートをエクスポートする場合、エクスポートには Unindexed という名前のレポートがItems.csv。 このレポートには、このファイルと同じ情報の大部分がResultsLog.csvされます。ただし、インデックス付きItems.csvファイルには、部分的にインデックスが作成されたアイテムに関連するエラー タグとエラー プロパティの 2 つのフィールドも **含まれています**。 これらのフィールドには、部分的にインデックスが作成された各アイテムのインデックス作成エラーに関する情報が含まれます。 これら 2 つのフィールドの情報を使用すると、特定のインデックス作成エラーが調査に影響を与えるかどうかを判断するのに役立ちます。 その場合は、対象を絞った検索を実行し、特定の電子メール メッセージと SharePoint または OneDrive ドキュメントを取得およびエクスポートして、調査に関連したかどうかを確認できます。 詳しい手順については、「Office [365](csv-file-for-an-id-list-content-search.md)でターゲット検索用の CSV ファイルを準備する」を参照してください。

> [!NOTE]
> Unindexed Items.csvファイルには、エラーの種類とエラー メッセージという **名前の** フィールド **も含まれています**。 これらは、[エラー タグ] フィールドと [エラー プロパティ]フィールドの情報に似た情報を含み、より詳細な情報を含むレガシ フィールドです。 これらの従来のフィールドは無視しても問題ではありません。
  
## <a name="errors-related-to-partially-indexed-items"></a>部分的にインデックスが作成されたアイテムに関連するエラー

エラー タグは、エラーとファイルの種類の 2 つの情報からなります。 たとえば、このエラー/ファイルの種類のペアでは、次のようになります。

```text
 parseroutputsize_xls
```

 `parseroutputsize` はエラーであり `xls` 、エラーが発生したファイルのファイルの種類です。 ファイルの種類が認識されない場合や、ファイルの種類がエラーに適用されない場合は、ファイルの種類の代わりの値 `noformat` が表示されます。
  
インデックス作成エラーの一覧と、エラーの考えられる原因の説明を次に示します。
  
| エラー タグ | 内容 |
|:-----|:-----|
| `attachmentcount` <br/> |電子メール メッセージの添付ファイルが多すぎるので、これらの添付ファイルの一部は処理されません。  <br/> |
| `attachmentdepth` <br/> |コンテンツ取得機能とドキュメント パーサーは、他の添付ファイル内に入れ子になった添付ファイルのレベルが多すぎます。 これらの添付ファイルの一部は処理されません。  <br/> |
| `attachmentrms` <br/> |添付ファイルは RMS で保護されたため、デコードに失敗しました。  <br/> |
| `attachmentsize` <br/> |電子メール メッセージに添付されたファイルが大きすぎて処理できなかった。  <br/> |
| `indexingtruncated` <br/> |処理された電子メール メッセージをインデックスに書き込むときに、インデックス可能なプロパティの 1 つが大きすぎて切り詰められていました。 切り捨てられたプロパティは、[エラーのプロパティ] フィールドに一覧表示されます。  <br/> |
| `invalidunicode` <br/> |電子メール メッセージに、有効な Unicode として処理できなかったテキストが含まれている。 このアイテムのインデックス作成が不完全な場合があります。  <br/> |
| `parserencrypted` <br/> |添付ファイルまたは電子メール メッセージのコンテンツは暗号化され、Microsoft 365 はコンテンツをデコードできなかった。  <br/> |
| `parsererror` <br/> |解析中に不明なエラーが発生しました。 これは通常、ソフトウェアのバグやサービスのクラッシュによって発生します。  <br/> |
| `parserinputsize` <br/> |添付ファイルが大きすぎてパーサーが処理できないので、その添付ファイルの解析が行えなかったか、完了しなかった。  <br/> |
| `parsermalformed` <br/> |添付ファイルの形式が正しくなかったので、パーサーが処理できなかった。 この結果は、古いファイル形式、互換性のないソフトウェアによって作成されたファイル、またはクレーム以外のファイルを名用するウイルスが原因である可能性があります。  <br/> |
| `parseroutputsize` <br/> |添付ファイルの解析からの出力が大きすぎるので、切り捨てる必要がありました。  <br/> |
| `parserunknowntype` <br/> |添付ファイルのファイルの種類が Microsoft 365 で検出できなかった。  <br/> |
| `parserunsupportedtype` <br/> |添付ファイルのファイルの種類は 365 Office検出できますが、そのファイルの種類の解析はサポートされていません。  <br/> |
| `propertytoobig` <br/> |Exchange ストアの電子メール プロパティの値が大きすぎて取得できなかったので、メッセージを処理できませんでした。 これは通常、電子メール メッセージの body プロパティにのみ発生します。  <br/> |
| `retrieverrms` <br/> |コンテンツ取得者は、RMS で保護されたメッセージのデコードに失敗しました。  <br/> |
| `wordbreakertruncated` <br/> |インデックス作成中にドキュメント内で識別された単語が多すぎます。 制限値に達するとプロパティの処理が停止し、プロパティは切り捨てらされます。  <br/> |

エラー フィールドは、[エラー タグ] フィールドに表示される処理エラーの影響を受けるフィールドを示します。 If you're searching a property such as  `subject` or , errors in the body of the message  `participants` won't impact the results of your search. これは、詳細な調査が必要になる可能性がある部分的にインデックスが作成されたアイテムを正確に判断する場合に役立ちます。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>PowerShell スクリプトを使用して、部分的にインデックスが作成された電子メール アイテムに対する組織の露出を特定する

次の手順では、すべての Exchange メールボックス内のすべてのアイテムを検索し、部分的にインデックスが作成された電子メール アイテムの組織の比率に関するレポートを (カウントおよびサイズ別に) 生成し、発生するインデックス作成エラーごとにアイテム数 (およびファイルの種類) を表示する PowerShell スクリプトを実行する方法を示します。 前のセクションのエラー タグの説明を使用して、インデックス作成エラーを特定します。
  
1. ファイル名サフィックス .ps1 を使用Windows PowerShellスクリプト ファイルに次のテキストを保存します。たとえば、 `PartiallyIndexedItems.ps1` .

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "**************************************************"
     " " 
     # Create a search with Error Tags Refinders enabled
     Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
     New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
     Start-ComplianceSearch "RefinerTest"
     # Loop while search is in progress
     do{
         Write-host "Waiting for search to complete..."
         Start-Sleep -s 5
         $complianceSearch = Get-ComplianceSearch "RefinerTest"
     }while ($complianceSearch.Status -ne 'Completed')
     $refiners = $complianceSearch.Refiners | ConvertFrom-Json
     $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
     $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
     $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
     " "
     "===== Partially indexed items ====="
     "         Total          Ratio"
     "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
     "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
     " "
     Write-Host ===== Reasons for partially indexed items =====
     foreach($errorTagProperty in $errorTagProperties)
     {
         $name = $refiners.Entries.($errorTagProperty.Name).Name
         $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
         $frag = $name.Split("{_}")
         $errorTag = $frag[0]
         $fileType = $frag[1]
         if ($errorTag -ne $lastErrorTag)
         {
             $errorTag
         }
         "    " + $fileType + " => " + $count
         $lastErrorTag = $errorTag
     }
   ```

2. [セキュリティ/コンプライアンス センター PowerShell に接続します](https://go.microsoft.com/fwlink/p/?linkid=627084)。

3. セキュリティ センター & コンプライアンス センターの PowerShell で、手順 1 でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

スクリプトによって返される出力の例を次に示します。
  
![部分的にインデックスが作成された電子メール アイテムに対する組織の露出に関するレポートを生成するスクリプトからの出力の例](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> 次の点に注意してください。
>  
> - メール アイテムの総数とサイズ、および部分的にインデックスが作成された電子メール アイテムに対する組織の比率 (カウントおよびサイズ別)。
> 
> - エラーが発生したリスト エラー タグと対応するファイルの種類。
  
## <a name="see-also"></a>関連項目

[電子情報開示の部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)
