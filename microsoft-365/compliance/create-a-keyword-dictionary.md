---
title: キーワード ディクショナリを作成する
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
description: Office 365 セキュリティ & コンプライアンスセンターでキーワードディクショナリを作成するための基本的な手順について説明します。
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818056"
---
# <a name="create-a-keyword-dictionary"></a>キーワード 辞書を作成する

データ損失防止 (DLP) は、機密情報を識別、監視、保護することができます。 機密情報を特定するには、特に、一般的なコンテンツ (医療関連の通信など) や不適切または明示的な言語を特定するときにキーワードの検索が必要になることがあります。 キーワードリストは機密情報の種類に作成できますが、キーワードリストのサイズは制限されており、作成または編集するには XML を変更する必要があります。 キーワード辞書を使用すると、キーワードを簡単に管理でき、より大きなスケールで、1つの辞書に最大10万用語をサポートします。
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>キーワード ディクショナリを作成する基本的な手順

The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:
  
1. **セキュリティ & コンプライアンスセンター** ( [https://protection.office.com](https://protection.office.com) ) を使用するか、**セキュリティ &amp; コンプライアンスセンターの PowerShell**に接続します。
    
2. **目的のソースからキーワードを定義または読み込み**ます。 ウィザードとコマンドレットはどちらも、ユーザー設定のキーワード辞書を作成するためのキーワードのコンマ区切りのリストを受け入れます。この手順は、キーワードの取得元に応じて若干異なります。 いったん読み込まれたキーワードは、インポートされる前にエンコードされてバイト配列に変換されます。
    
3. **辞書を作成**します。 名前と説明を選択し、辞書を作成します。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターを使用してキーワードディクショナリを作成する

ユーザー辞書のキーワードを作成してインポートするには、次の手順を実行します。

1. セキュリティ & コンプライアンスセンター () に接続し [https://protection.office.com](https://protection.office.com) ます。

2. **[分類] > [機密情報の種類]** の順に移動します。

3. **[作成]** を選択し、機密情報の**名前**と**説明**を入力してから、**[次へ]** を選択します。

4. **[要素を追加する]** を選択し、**[次を含むコンテンツを検出する]** ドロップダウン リストの中から **[辞書 (大規模なキーワード)]** を選択します。

5. **[辞書を追加する]** を選択します。

6. 検索コントロールで、**[ここで新しいキーワード ディクショナリを作成する]** を選択します。

7. ユーザー辞書の**名前**を入力します。

8. **[インポート]** を選択し、キーワード ファイルの種類に応じて **[テキストから]** か **[csv から]** のいずれかを選択します。

9. ファイル ダイアログで、ローカル PC またはネットワーク ファイル共有からキーワード ファイルを選択し、**[開く]** を選択します。

10. **[保存]** を選択し、**[キーワード ディクショナリ]** リストから該当するユーザー辞書を選択します。

11. **[追加]** を選択し、**[次へ]** を選択します。

12. 機密情報の種類の選択を最終的に確認し、**[終了]** を選択します。
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>PowerShell を使用してファイルからキーワード ディクショナリを作成する

Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. キーワードをテキスト ファイルにコピーし、各キーワードが別個の行にあるかどうかを確認します。
    
2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.
    
3. このコマンドレットを実行して、ファイルを変数として読み取ります。
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. このコマンドレットを実行して、ディクショナリを作成します。
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>既存のキーワード ディクショナリを変更する

キーワード ディクショナリのいずれかでキーワードを変更したり、組み込みのディクショナリのいずれかを変更したりする必要が生じることがあります。 現在のところ、PowerShell を使用してのみ、カスタム キーワード ディクショナリを更新できます。 

たとえば、いくつかの用語を PowerShell で変更し、それらをエディターで変更できるようにローカルに保存してから、以前の用語をインプレースで更新します。 

最初に、ディクショナリ オブジェクトを取得します。
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

印刷 `$dict` にはさまざまな変数が表示されます。 キーワード自体はバックエンドのオブジェクトに格納されますが、 `$dict.KeywordDictionary` 辞書を変更するために使用する文字列表現が含まれています。 

辞書を変更する前に、メソッドを使用して用語の文字列を配列に戻す必要があり `.split(',')` ます。 その後、メソッドを使用してキーワード間の不要なスペースをクリーンアップし `.trim()` 、操作するキーワードだけを残します。 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.
  
In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.
  
Run the command  `$terms` to show the current list of terms. The output of the command looks like this: 
  
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

Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed): 
  
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

Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う

キーワード辞書は、カスタムの機密情報の種類の一致要件の一部として、または機密情報の種類自体として使用できます。 どちらの場合も、[カスタムの機密情報の種類](create-a-custom-sensitive-information-type-in-scc-powershell.md)を作成する必要があります。 リンクされた記事の手順に従って、機密情報の種類を作成します。 XML を取得したら、それを使用するには、ディクショナリの GUID 識別子が必要になります。
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

ディクショナリの ID を取得するには、このコマンドを実行して **ID** のプロパティ値をコピーします。 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

コマンドの出力は次のようになります。
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```
