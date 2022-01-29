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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: コンプライアンス センターでキーワード 辞書を変更するMicrosoft 365説明します。
ms.openlocfilehash: acdf8b24aced21ed2f576fd57a3c685ef14debea
ms.sourcegitcommit: 99067d5eb1fa7b094e7cdb1f7be65acaaa235a54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2022
ms.locfileid: "62271816"
---
# <a name="modify-a-keyword-dictionary"></a>キーワード 辞書を変更する

キーワード ディクショナリのいずれかでキーワードを変更したり、組み込みのディクショナリのいずれかを変更したりする必要が生じることがあります。 これを行うには、PowerShell またはコンプライアンス センターを使用します。

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>コンプライアンス センターでキーワード 辞書を変更する

キーワード ディクショナリは、機密情報の種類 `Primary elements` `Supporting elements` (SIT) パターンとして、または機密情報のパターンで使用できます。 SIT または既存の SIT の作成時にキーワード 辞書を編集できます。 たとえば、既存のキーワード ディクショナリを編集するには、次の方法を使用します。

1. 更新するキーワード ディクショナリを含むパターンを開きます。
2. 更新するキーワード 辞書を見つけて、[編集] を選択します。
3. 1 行に 1 つのキーワードを使用して編集します。

   ![スクリーンショットの編集キーワード。](../media/edit-keyword-dictionary.png)

4. を選択します `Done`。

## <a name="modify-a-keyword-dictionary-using-powershell"></a>PowerShell を使用してキーワード ディクショナリを変更する

たとえば、PowerShell で用語をいくつか変更し、ローカル環境のエディターで用語を変更できる場所に用語を保存して、元の用語をそこで更新します。

最初に、ディクショナリ オブジェクトを取得します。

```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

印刷では `$dict` 、さまざまなプロパティが表示されます。 キーワード自体は `$dict.KeywordDictionary` 、バックエンド上のオブジェクトに格納されますが、辞書の変更に使用する文字列表現が含まれます。

辞書を変更する前に、メソッドを使用して用語の文字列を配列に戻す必要 `.split(',')` があります。 次に、メソッドを使用 `.trim()` してキーワード間の不要なスペースをクリーンアップし、使用するキーワードを残します。

```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

ここでは、辞書から一部の用語を削除します。例の辞書には少しのキーワードしかないので、辞書のエクスポートとノートパッドでの編集に簡単にスキップすることができますが、通常、辞書には大量のテキストが含まれているので PowerShell で簡単に編集を行うこの方法をまず確認しておいてください。

最後の手順で、キーワードを配列に保存しました。[配列から項目を削除する](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))にはいくつか方法がありますが、簡単なのは、ディクショナリから削除する用語の配列を作成して、削除する用語のリストには含まれないディクショナリの用語だけをそこにコピーする方法です。

コマンドを実行して `$terms` 、現在の用語の一覧を表示します。 コマンドの出力は次のようになります。

```powershell
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

このコマンドを実行して、削除する用語を指定します。

```powershell
$termsToRemove = @('abandonment','ablatio')
```

リストから用語を実際に削除するには、このコマンドを実行します。

```powershell
$updatedTerms = $terms | Where-Object {$_ -notin $termsToRemove}
```

コマンドを実行して `$updatedTerms` 、更新された用語の一覧を表示します。 コマンドの出力は次のように表示されます (指定した用語は削除されています)。

```powershell
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

ここでは、ディクショナリをローカルに保存して、用語をいくつか追加します。PowerShell で直接用語を追加できますが、確実に Unicode エンコードで保存し BOM が含まれるようにするために、ファイルをローカルでエクスポートする必要があります。

次のように実行してディクショナリをローカルに保存します。

```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

次にファイルを開いて、その他の用語を追加し、Unicode エンコード (UTF-16) で保存します。それから更新した用語をアップロードして、辞書を所定の場所で更新します。

```powershell
Set-DlpKeywordDictionary -Identity "Diseases" -FileData ([System.IO.File]::ReadAllBytes('C:myPath\terms.txt'))
```

辞書はその場で更新されます。 この `Identity` フィールドは辞書の名前を受け取る。 コマンドレットを使用して`Set-``-Name`辞書の名前も変更する場合は、新しい辞書名で上記のパラメーターを追加する必要があります。

## <a name="see-also"></a>関連項目

- [キーワード辞書を作成する](create-a-keyword-dictionary.md)
- [カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)
