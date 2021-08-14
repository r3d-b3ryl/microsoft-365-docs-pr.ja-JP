---
title: キーワード 辞書を変更する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: コンプライアンス センターでキーワード 辞書を変更するMicrosoft 365説明します。
ms.openlocfilehash: 17dafeb6302207ded8653f17f7bf40dfaa8a9e2ef07d7eb38a485488f2346eaa
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53855462"
---
# <a name="modify-a-keyword-dictionary"></a>キーワード 辞書を変更する

キーワード ディクショナリのいずれかでキーワードを変更したり、組み込みのディクショナリのいずれかを変更したりする必要が生じることがあります。 これを行うには、PowerShell またはコンプライアンス センターを使用します。

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>コンプライアンス センターでキーワード 辞書を変更する

キーワード ディクショナリは、機密情報の種類 `Primary elements` `Supporting elements` (SIT) パターンとして、または機密情報のパターンで使用できます。 SIT または既存の SIT の作成時にキーワード 辞書を編集できます。 たとえば、既存のキーワード ディクショナリを編集するには、次の方法を使用します。

1. 更新するキーワード ディクショナリを含むパターンを開きます。
2. 更新するキーワード 辞書を見つけて、[編集] を選択します。 
3.  1 行に 1 つのキーワードを使用して編集します。

![スクリーンショットの編集キーワード](../media/edit-keyword-dictionary.png)

4. を選択します `Done` 。

## <a name="modify-a-keyword-dictionary-using-powershell"></a>PowerShell を使用してキーワード ディクショナリを変更する 

たとえば、PowerShell で用語をいくつか変更し、ローカル環境のエディターで用語を変更できる場所に用語を保存して、元の用語をそこで更新します。 

最初に、ディクショナリ オブジェクトを取得します。
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

`$dict` を印刷すると、さまざまな変数が表示されます。 キーワード自体はバックエンドのオブジェクトに保存されますが、`$dict.KeywordDictionary` にはその文字列表現が含まれ、ディクショナリを変更するために使用します。 

ディクショナリを変更する前に、`.split(',')` メソッドを使用して、用語の文字列を配列に戻す必要があります。 使用するキーワードだけを残し、`.trim()` メソッドでキーワード間の不要なスペースを取り除きます。 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

ここでは、辞書から一部の用語を削除します。例の辞書には少しのキーワードしかないので、辞書のエクスポートとノートパッドでの編集に簡単にスキップすることができますが、通常、辞書には大量のテキストが含まれているので PowerShell で簡単に編集を行うこの方法をまず確認しておいてください。
  
最後の手順で、キーワードを配列に保存しました。[配列から項目を削除する](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))にはいくつか方法がありますが、簡単なのは、ディクショナリから削除する用語の配列を作成して、削除する用語のリストには含まれないディクショナリの用語だけをそこにコピーする方法です。
  
コマンド `$terms` を実行して、現在の用語のリストを表示します。コマンドの出力は次のようになります。 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

このコマンドを実行して、削除する用語を指定します。
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

リストから用語を実際に削除するには、このコマンドを実行します。
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

コマンド `$updatedTerms` を実行して、更新された用語のリストを表示します。コマンドの出力は次のようになります (指定した用語は削除されています)。 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

次にファイルを開いて、その他の用語を追加し、Unicode エンコード (UTF-16) で保存します。それから更新した用語をアップロードして、辞書を所定の場所で更新します。
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

辞書はその場で更新されます。 `Identity` フィールドは、辞書の名前を受け取ります。 また、`set-` コマンドレットを使用して辞書の名前も変更するには、上述の内容に新しい辞書名と共に `-Name` パラメーターを追加する必要があるだけです。 

関連項目
- [キーワード辞書を作成する](create-a-keyword-dictionary.md)
- [カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)
