---
title: キーワード 辞書の変更
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
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685212"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="7c857-103">キーワード 辞書の変更</span><span class="sxs-lookup"><span data-stu-id="7c857-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="7c857-104">キーワード ディクショナリのいずれかでキーワードを変更したり、組み込みのディクショナリのいずれかを変更したりする必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="7c857-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="7c857-105">これを行うには、PowerShell またはコンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c857-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="7c857-106">コンプライアンス センターでキーワード 辞書を変更する</span><span class="sxs-lookup"><span data-stu-id="7c857-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="7c857-107">キーワード ディクショナリは、機密情報の種類 `Primary elements` `Supporting elements` (SIT) パターンとして、または機密情報のパターンで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c857-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="7c857-108">SIT または既存の SIT の作成時にキーワード 辞書を編集できます。</span><span class="sxs-lookup"><span data-stu-id="7c857-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="7c857-109">たとえば、既存のキーワード ディクショナリを編集するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c857-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="7c857-110">更新するキーワード ディクショナリを含むパターンを開きます。</span><span class="sxs-lookup"><span data-stu-id="7c857-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="7c857-111">更新するキーワード 辞書を見つけて、[編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c857-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="7c857-112">1 行に 1 つのキーワードを使用して編集します。</span><span class="sxs-lookup"><span data-stu-id="7c857-112">Make your edits, using one keyword per line.</span></span>

![スクリーンショットの編集キーワード](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="7c857-114">を選択します `Done` 。</span><span class="sxs-lookup"><span data-stu-id="7c857-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="7c857-115">PowerShell を使用してキーワード ディクショナリを変更する</span><span class="sxs-lookup"><span data-stu-id="7c857-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="7c857-116">たとえば、PowerShell で用語をいくつか変更し、ローカル環境のエディターで用語を変更できる場所に用語を保存して、元の用語をそこで更新します。</span><span class="sxs-lookup"><span data-stu-id="7c857-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="7c857-117">最初に、ディクショナリ オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c857-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="7c857-118">`$dict` を印刷すると、さまざまな変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c857-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="7c857-119">キーワード自体はバックエンドのオブジェクトに保存されますが、`$dict.KeywordDictionary` にはその文字列表現が含まれ、ディクショナリを変更するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7c857-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="7c857-120">ディクショナリを変更する前に、`.split(',')` メソッドを使用して、用語の文字列を配列に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c857-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="7c857-121">使用するキーワードだけを残し、`.trim()` メソッドでキーワード間の不要なスペースを取り除きます。</span><span class="sxs-lookup"><span data-stu-id="7c857-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="7c857-p105">ここでは、辞書から一部の用語を削除します。例の辞書には少しのキーワードしかないので、辞書のエクスポートとノートパッドでの編集に簡単にスキップすることができますが、通常、辞書には大量のテキストが含まれているので PowerShell で簡単に編集を行うこの方法をまず確認しておいてください。</span><span class="sxs-lookup"><span data-stu-id="7c857-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="7c857-p106">最後の手順で、キーワードを配列に保存しました。[配列から項目を削除する](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))にはいくつか方法がありますが、簡単なのは、ディクショナリから削除する用語の配列を作成して、削除する用語のリストには含まれないディクショナリの用語だけをそこにコピーする方法です。</span><span class="sxs-lookup"><span data-stu-id="7c857-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="7c857-p107">コマンド `$terms` を実行して、現在の用語のリストを表示します。コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7c857-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="7c857-128">このコマンドを実行して、削除する用語を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c857-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="7c857-129">リストから用語を実際に削除するには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c857-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="7c857-p108">コマンド `$updatedTerms` を実行して、更新された用語のリストを表示します。コマンドの出力は次のようになります (指定した用語は削除されています)。</span><span class="sxs-lookup"><span data-stu-id="7c857-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="7c857-p109">次にファイルを開いて、その他の用語を追加し、Unicode エンコード (UTF-16) で保存します。それから更新した用語をアップロードして、辞書を所定の場所で更新します。</span><span class="sxs-lookup"><span data-stu-id="7c857-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="7c857-134">辞書はその場で更新されます。</span><span class="sxs-lookup"><span data-stu-id="7c857-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="7c857-135">`Identity` フィールドは、辞書の名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7c857-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="7c857-136">また、`set-` コマンドレットを使用して辞書の名前も変更するには、上述の内容に新しい辞書名と共に `-Name` パラメーターを追加する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="7c857-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="7c857-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c857-137">See Also</span></span>
- [<span data-ttu-id="7c857-138">キーワード辞書を作成する</span><span class="sxs-lookup"><span data-stu-id="7c857-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="7c857-139">カスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="7c857-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
