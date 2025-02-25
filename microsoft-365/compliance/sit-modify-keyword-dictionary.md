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
description: Microsoft Purview コンプライアンス ポータルでキーワード ディクショナリを変更する方法について説明します。
ms.openlocfilehash: 8b2f2256be506f0ba01dc059bf0ac54e84c481c9
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66621713"
---
# <a name="modify-a-keyword-dictionary"></a>キーワード 辞書を変更する

キーワード ディクショナリのいずれかでキーワードを変更したり、組み込みのディクショナリのいずれかを変更したりする必要が生じることがあります。 これを行うには、PowerShell またはコンプライアンス センターを使用します。

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>コンプライアンス センターでキーワード ディクショナリを変更する

キーワード ディクショナリは、機密情報の種類 (SIT) パターンとして `Primary elements` 、または `Supporting elements` 機密情報の種類で使用できます。 SIT の作成時または既存の SIT 内で、キーワード ディクショナリを編集できます。 たとえば、既存のキーワード ディクショナリを編集するには、

1. 更新するキーワード ディクショナリを含むパターンを開きます。
2. 更新するキーワード ディクショナリを見つけて、[編集] を選択します。
3. 1 行に 1 つのキーワードを使用して編集を行います。

   ![スクリーンショット編集キーワード。](../media/edit-keyword-dictionary.png)

4. を選択します `Done`。

## <a name="modify-a-keyword-dictionary-using-powershell"></a>PowerShell を使用してキーワード ディクショナリを変更する

たとえば、PowerShell で用語をいくつか変更し、ローカル環境のエディターで用語を変更できる場所に用語を保存して、元の用語をそこで更新します。

最初に、ディクショナリ オブジェクトを取得します。

```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

印刷 `$dict` にはさまざまなプロパティが表示されます。 キーワード自体はバックエンド上のオブジェクトに格納されますが、それらの文字列表現が `$dict.KeywordDictionary` 含まれています。この表現を使用してディクショナリを変更します。

ディクショナリを変更する前に、メソッドを使用して `.split(',')` 用語の文字列を配列に戻す必要があります。 次に、メソッドを使用 `.trim()` してキーワード間の不要なスペースをクリーンアップし、操作するキーワードだけを残します。

```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

ここでは、辞書から一部の用語を削除します。例の辞書には少しのキーワードしかないので、辞書のエクスポートとノートパッドでの編集に簡単にスキップすることができますが、通常、辞書には大量のテキストが含まれているので PowerShell で簡単に編集を行うこの方法をまず確認しておいてください。

最後の手順で、キーワードを配列に保存しました。[配列から項目を削除する](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))にはいくつか方法がありますが、簡単なのは、ディクショナリから削除する用語の配列を作成して、削除する用語のリストには含まれないディクショナリの用語だけをそこにコピーする方法です。

コマンド `$terms` を実行して、現在の用語の一覧を表示します。 コマンドの出力は次のようになります。

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

コマンド `$updatedTerms` を実行して、更新された用語の一覧を表示します。 コマンドの出力は次のようになります (指定された用語は削除されました)。

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

辞書はその場で更新されます。 フィールドは `Identity` ディクショナリの名前を受け取ります。 コマンドレットを使用してディクショナリの名前も変更する場合は、新しいディクショナリ名を`-Name`使用`Set-`して上記のパラメーターを追加するだけで済みます。

## <a name="see-also"></a>関連項目

- [キーワード辞書を作成する](create-a-keyword-dictionary.md)
- [カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)
