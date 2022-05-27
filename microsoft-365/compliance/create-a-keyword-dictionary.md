---
title: キーワード 辞書を作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: Office 365 セキュリティ/コンプライアンス センターでキーワード ディクショナリを作成する基本的な手順について説明します。
ms.openlocfilehash: ceb410d09d9869d87681128f2c6e7b45cd8363cb
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753674"
---
# <a name="create-a-keyword-dictionary"></a>キーワード ディクショナリを作成する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview のデータ損失防止 (DLP) は、機密アイテムの識別、監視、および保護を行うことができます。 機密アイテムの識別には、特に汎用コンテンツ (医療関連の通信など) または不適切な言語や露骨な表現を識別するときに、キーワードを検索する必要がある場合があります。 機密情報の種類でキーワード リストを作成することができますが、キーワード リストにはサイズの制限があり、リストの作成や編集を行うには、XML を変更する必要があります。 キーワード辞書は、キーワードの管理が簡単になり、はるかに大規模で、辞書で最大 1 MB の用語 (圧縮後) をサポートし、あらゆる言語をサポートします。 テナント制限は、圧縮後も 1 MB です。 1 MB の圧縮後の制限は、テナント全体で結合されたすべての辞書が 100 万文字近くになる可能性があることを意味します。

## <a name="keyword-dictionary-limits"></a>キーワード辞書の制限

テナントごとに作成できるキーワード辞書ベースの機密情報の種類は 50 個に制限されています。 テナントにあるキーワード辞書の数を確認するには、「[セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)」の手順を使用して接続し、テナントに接続してこの PowerShell スクリプトを実行します。

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
[System.IO.File]::WriteAllBytes((Resolve-Path $rawFile), $ruleCollections.SerializedClassificationRuleCollection)
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>キーワード辞書を作成する基本的な手順

辞書のキーワードを、さまざまなソースから作成することができます。一般的な例として、サービスにインポートされたファイルや PowerShell コマンドレットでインポートされたファイル (.csv または .txt リストなど)、PowerShell コマンドレットで直接入力するリスト、または既存の辞書などがあります。キーワード辞書を作成するときには、次の同じ基本手順に従います。

1. *<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>を使用するか **、Microsoft Purview コンプライアンス ポータル PowerShell** に接続します。

2. **該当するソースからキーワードを定義する、または読み込む**。ウィザードとコマンドレットの両方でコンマ区切りキーワード リストを使ってカスタム キーワード辞書を作成できるので、この手順はキーワードがどこから得られるかによって多少異なります。いったん読み込まれたキーワードは、インポートされる前にエンコードされてバイト配列に変換されます。

3. **ディクショナリを作成する**。名前と説明を選択し、ディクショナリを作成します。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターを使用してキーワード ディクショナリを作成する

ユーザー辞書のキーワードを作成してインポートするには、次の手順を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>に接続します。

2. **[分類] > [機密情報の種類]** の順に移動します。

3. **[作成]** を選択し、機密情報の **名前** と **説明** を入力してから、**[次へ]** を選択します。

4. **[要素を追加する]** を選択し、**[次を含むコンテンツを検出する]** ドロップダウン リストの中から **[辞書 (大規模なキーワード)]** を選択します。

5. **[辞書を追加する]** を選択します。

6. 検索コントロールで、**[ここで新しいキーワード ディクショナリを作成する]** を選択します。

7. ユーザー辞書の **名前** を入力します。

8. **[インポート]** を選択し、キーワード ファイルの種類に応じて **[テキストから]** か **[csv から]** のいずれかを選択します。

9. ファイル ダイアログで、ローカル PC またはネットワーク ファイル共有からキーワード ファイルを選択し、**[開く]** を選択します。

10. **[保存]** を選択し、**[キーワード ディクショナリ]** リストから該当するユーザー辞書を選択します。

11. **[追加]** を選択し、**[次へ]** を選択します。

12. 機密情報の種類の選択を最終的に確認し、**[終了]** を選択します。

## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>PowerShell を使用してファイルからキーワード ディクショナリを作成する

大きなディクショナリを作成する必要がある場合はたいてい、ファイルからのキーワードや、その他のソースからエクスポートしたリストを使うことになります。その場合、外部電子メールでスクリーニングを行うための不適切な言語のリストを含むキーワード ディクショナリを作成します。まず[セキュリティ  コンプライアンス センター PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)必要があります。

1. キーワードをテキスト ファイルにコピーし、各キーワードが別個の行にあるかどうかを確認します。

2. テキスト ファイルを、Unicode エンコードで、メモ帳 \> **名前を付けて保存** \> **エンコード** \> **Unicode** に保存します。

3. このコマンドレットを実行して、ファイルを変数として読み取ります。

    ```powershell
    $fileData = [System.IO.File]::ReadAllBytes('<filename>')
    ```

4. このコマンドレットを実行して、ディクショナリを作成します。

    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う

キーワード ディクショナリは、カスタムの機密情報の種類の合致要件の一部として、または機密情報の種類そのものとして使用することができます。どちらの場合も、[カスタムの機密情報の種類](create-a-custom-sensitive-information-type-in-scc-powershell.md)を作成する必要があります。リンク先の記事にある手順に従って、機密情報の種類を作成できます。XML ができたら、それを使うためにディクショナリの GUID 識別子が必要になります。

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

カスタムの機密情報の種類の XML に ID を貼り付けて、アップロードします。これで、ディクショナリは機密情報の種類のリストに表示され、それをポリシーで使用して、一致するキーワードがいくつ必要かを指定することができます。

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

> [!NOTE]
> Microsoft 365 Information Protection は、次のような場合に 2 バイト文字セットの言語をサポートします。
>
> - 中国語 (簡体字)
> - 中国語 (繁体字)
> - 韓国語
> - 日本語
>
> このサポートは、機密情報の種類で使用できます。 詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポー](mip-dbcs-relnotes.md)」を参照してください。

> [!TIP]
> 中国語/日本語の文字と 1 バイト文字を含むパターンを検出する、または中国語/日本語と英語を含むパターンを検出するには、キーワードまたは正規表現の 2 つのバリエーションを定義します。
>
> - たとえば、「机密的ドキュメント」のようなキーワードを検出するには、キーワードの 2 つのバリエーションを使用します。 1 つは日本語と英語のテキストの間にスペースがあり、もう 1 つは日本語と英語のテキストの間にスペースがありません。 したがって、SITに追加するキーワードは、"机密的 document" と "机密的document" である必要があります。 同様に、"東京オリンピック2020" というフレーズを検出するには、"東京オリンピック 2020" と "東京オリンピック2020" の 2 つのバリエーションを使用する必要があります。
>
> 中国語/日本語/ 2 バイト文字に加えて、キーワード/フレーズのリストに中国語/日本語以外の単語も含まれている場合 (英語のみなど)、2 つの辞書/キーワード リストを作成することをお勧めします。 1 つは中国語/日本語/ 2 バイト文字を含むキーワード用で、もう1 つは英語のみ用です。
>
> - たとえば、"Highly confidential"、"機密性が高い"、"机密的document" の 3 つのフレーズを含むキーワード辞書/リストを作成する場合は、2 つのキーワード リストを作成する必要があります。
>   1. Highly confidential
>   2. 機密性が高い、机密的document、机密的 document
>
> 2 バイトのハイフンまたは 2 バイトのピリオドを使用して正規表現を作成するときは、正規表現のハイフンまたはピリオドをエスケープするように、必ず両方の文字をエスケープしてください。参考までに、サンプルの正規表現を次に示します。
>
> - `(?<!\d)([4][0-9]{3}[\-?\-\t]*[0-9]{4}`
>
> キーワード リストでは、単語の一致ではなく文字列の一致を使用することをお勧めします。
