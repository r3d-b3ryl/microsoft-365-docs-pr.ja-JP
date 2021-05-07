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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Office 365 セキュリティ/コンプライアンス センターでキーワード ディクショナリを作成する基本的な手順について説明します。
ms.openlocfilehash: 94bacc2a2fe91fdc35aad753cc2e7db80a374e29
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876078"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="33d64-103">キーワード ディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="33d64-103">Create a keyword dictionary</span></span>

<span data-ttu-id="33d64-104">データ損失防止 (DLP) は、機密アイテムの識別、監視、および保護を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="33d64-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="33d64-105">機密アイテムの識別には、特に汎用コンテンツ (医療関連の通信など) または不適切な言語や露骨な表現を識別するときに、キーワードを検索する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="33d64-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="33d64-106">機密情報の種類でキーワード リストを作成することができますが、キーワード リストにはサイズの制限があり、リストの作成や編集を行うには、XML を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33d64-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="33d64-107">キーワード辞書は、キーワードの管理が簡単になり、はるかに大規模で、辞書で最大 1 MB の用語 (圧縮後) をサポートし、あらゆる言語をサポートします。</span><span class="sxs-lookup"><span data-stu-id="33d64-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="33d64-108">テナント制限は、圧縮後も 1 MB です。</span><span class="sxs-lookup"><span data-stu-id="33d64-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="33d64-109">1 MB の圧縮後の制限は、テナント全体で結合されたすべての辞書が 100 万文字近くになる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="33d64-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="33d64-110">キーワード辞書の制限</span><span class="sxs-lookup"><span data-stu-id="33d64-110">Keyword dictionary limits</span></span>

<span data-ttu-id="33d64-111">テナントごとに作成できるキーワード辞書ベースの機密情報の種類は 50 個に制限されています。</span><span class="sxs-lookup"><span data-stu-id="33d64-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="33d64-112">テナントにあるキーワード辞書の数を確認するには、「[セキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)」の手順を使用して接続し、テナントに接続してこの PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="33d64-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="33d64-113">キーワード辞書を作成する基本的な手順</span><span class="sxs-lookup"><span data-stu-id="33d64-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="33d64-p103">辞書のキーワードを、さまざまなソースから作成することができます。一般的な例として、サービスにインポートされたファイルや PowerShell コマンドレットでインポートされたファイル (.csv または .txt リストなど)、PowerShell コマンドレットで直接入力するリスト、または既存の辞書などがあります。キーワード辞書を作成するときには、次の同じ基本手順に従います。</span><span class="sxs-lookup"><span data-stu-id="33d64-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="33d64-116">**セキュリティ/コンプライアンス センター** ([https://protection.office.com](https://protection.office.com)) を使用するか、**セキュリティ &amp; コンプライアンス センター PowerShell** に接続します。</span><span class="sxs-lookup"><span data-stu-id="33d64-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="33d64-117">**目的のソースからキーワードを定義または読み込みます**。</span><span class="sxs-lookup"><span data-stu-id="33d64-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="33d64-118">ウィザードとコマンドレットの両方でコンマ区切りキーワード リストを使ってカスタム キーワード ディクショナリを作成できるので、この手順はキーワードがどこから得られるかによって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="33d64-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="33d64-119">いったん読み込まれたキーワードは、インポートされる前にエンコードされてバイト配列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="33d64-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="33d64-120">**ディクショナリを作成します**。</span><span class="sxs-lookup"><span data-stu-id="33d64-120">**Create your dictionary**.</span></span> <span data-ttu-id="33d64-121">名前と説明を選択し、ディクショナリを作成します。</span><span class="sxs-lookup"><span data-stu-id="33d64-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="33d64-122">セキュリティ/コンプライアンス センターを使用してキーワード ディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="33d64-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="33d64-123">ユーザー辞書のキーワードを作成してインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="33d64-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="33d64-124">セキュリティ/コンプライアンス センターに接続します ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="33d64-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="33d64-125">**[分類] > [機密情報の種類]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="33d64-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="33d64-126">**[作成]** を選択し、機密情報の **名前** と **説明** を入力してから、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="33d64-127">**[要素を追加する]** を選択し、**[次を含むコンテンツを検出する]** ドロップダウン リストの中から **[辞書 (大規模なキーワード)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="33d64-128">**[辞書を追加する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="33d64-129">検索コントロールで、**[ここで新しいキーワード ディクショナリを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="33d64-130">ユーザー辞書の **名前** を入力します。</span><span class="sxs-lookup"><span data-stu-id="33d64-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="33d64-131">**[インポート]** を選択し、キーワード ファイルの種類に応じて **[テキストから]** か **[csv から]** のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="33d64-132">ファイル ダイアログで、ローカル PC またはネットワーク ファイル共有からキーワード ファイルを選択し、**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="33d64-133">**[保存]** を選択し、**[キーワード ディクショナリ]** リストから該当するユーザー辞書を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="33d64-134">**[追加]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="33d64-135">機密情報の種類の選択を最終的に確認し、**[終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d64-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="33d64-136">PowerShell を使用してファイルからキーワード ディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="33d64-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="33d64-137">大きなディクショナリを作成する必要がある場合、それは他のソースからエクスポートされたファイルやリストからのキーワードを使用するためであることが多いです。</span><span class="sxs-lookup"><span data-stu-id="33d64-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="33d64-138">この場合、外部メールの画面に対する不適切な言語のリストを含めて、キーワード ディクショナリを作成します。</span><span class="sxs-lookup"><span data-stu-id="33d64-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="33d64-139">まず、[セキュリティ &amp; コンプライアンス センター PowerShell](/powershell/exchange/connect-to-scc-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="33d64-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="33d64-140">キーワードをテキスト ファイルにコピーし、各キーワードが別個の行にあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="33d64-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="33d64-p107">テキスト ファイルを、Unicode エンコードで、メモ帳 \> **名前を付けて保存** \> **エンコード** \> **Unicode** に保存します。</span><span class="sxs-lookup"><span data-stu-id="33d64-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="33d64-143">このコマンドレットを実行して、ファイルを変数として読み取ります。</span><span class="sxs-lookup"><span data-stu-id="33d64-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="33d64-144">このコマンドレットを実行して、ディクショナリを作成します。</span><span class="sxs-lookup"><span data-stu-id="33d64-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="33d64-145">既存のキーワード ディクショナリを変更する</span><span class="sxs-lookup"><span data-stu-id="33d64-145">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="33d64-146">キーワード ディクショナリのいずれかでキーワードを変更したり、組み込みのディクショナリのいずれかを変更したりする必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="33d64-146">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="33d64-147">現在のところ、PowerShell を使用してのみ、カスタム キーワード ディクショナリを更新できます。</span><span class="sxs-lookup"><span data-stu-id="33d64-147">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="33d64-148">たとえば、PowerShell で用語をいくつか変更し、ローカル環境のエディターで用語を変更できる場所に用語を保存して、元の用語をそこで更新します。</span><span class="sxs-lookup"><span data-stu-id="33d64-148">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="33d64-149">最初に、ディクショナリ オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="33d64-149">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="33d64-150">`$dict` を印刷すると、さまざまな変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="33d64-150">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="33d64-151">キーワード自体はバックエンドのオブジェクトに保存されますが、`$dict.KeywordDictionary` にはその文字列表現が含まれ、ディクショナリを変更するために使用します。</span><span class="sxs-lookup"><span data-stu-id="33d64-151">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="33d64-152">ディクショナリを変更する前に、`.split(',')` メソッドを使用して、用語の文字列を配列に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="33d64-152">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="33d64-153">使用するキーワードだけを残し、`.trim()` メソッドでキーワード間の不要なスペースを取り除きます。</span><span class="sxs-lookup"><span data-stu-id="33d64-153">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="33d64-p111">ここでは、辞書から一部の用語を削除します。例の辞書には少しのキーワードしかないので、辞書のエクスポートとノートパッドでの編集に簡単にスキップすることができますが、通常、辞書には大量のテキストが含まれているので PowerShell で簡単に編集を行うこの方法をまず確認しておいてください。</span><span class="sxs-lookup"><span data-stu-id="33d64-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="33d64-p112">最後の手順で、キーワードを配列に保存しました。[配列から項目を削除する](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))にはいくつか方法がありますが、簡単なのは、ディクショナリから削除する用語の配列を作成して、削除する用語のリストには含まれないディクショナリの用語だけをそこにコピーする方法です。</span><span class="sxs-lookup"><span data-stu-id="33d64-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="33d64-p113">コマンド `$terms` を実行して、現在の用語のリストを表示します。コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="33d64-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="33d64-160">このコマンドを実行して、削除する用語を指定します。</span><span class="sxs-lookup"><span data-stu-id="33d64-160">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="33d64-161">リストから用語を実際に削除するには、このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="33d64-161">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="33d64-p114">コマンド `$updatedTerms` を実行して、更新された用語のリストを表示します。コマンドの出力は次のようになります (指定した用語は削除されています)。</span><span class="sxs-lookup"><span data-stu-id="33d64-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="33d64-p115">次にファイルを開いて、その他の用語を追加し、Unicode エンコード (UTF-16) で保存します。それから更新した用語をアップロードして、辞書を所定の場所で更新します。</span><span class="sxs-lookup"><span data-stu-id="33d64-p115">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="33d64-166">辞書はその場で更新されます。</span><span class="sxs-lookup"><span data-stu-id="33d64-166">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="33d64-167">`Identity` フィールドは、辞書の名前を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="33d64-167">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="33d64-168">また、`set-` コマンドレットを使用して辞書の名前も変更するには、上述の内容に新しい辞書名と共に `-Name` パラメーターを追加する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="33d64-168">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="33d64-169">カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う</span><span class="sxs-lookup"><span data-stu-id="33d64-169">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="33d64-170">キーワード ディクショナリは、カスタムの機密情報の種類に一致する要件の一部として、または機密情報の種類自体として使用できます。</span><span class="sxs-lookup"><span data-stu-id="33d64-170">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="33d64-171">どちらも、[カスタムの機密情報の種類](create-a-custom-sensitive-information-type-in-scc-powershell.md) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33d64-171">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="33d64-172">リンク先の記事の手順に従って、機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="33d64-172">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="33d64-173">XML がある場合は、それを使用するディクショナリの GUID 識別子が必要になります。</span><span class="sxs-lookup"><span data-stu-id="33d64-173">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="33d64-174">ディクショナリの ID を取得するには、このコマンドを実行して **ID** のプロパティ値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="33d64-174">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="33d64-175">コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="33d64-175">The output of the command looks like this:</span></span>
  
<span data-ttu-id="33d64-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="33d64-176">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="33d64-p118">カスタムの機密情報の種類の XML に ID を貼り付けて、アップロードします。これで、ディクショナリは機密情報の種類のリストに表示され、それをポリシーで使用して、一致するキーワードがいくつ必要かを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="33d64-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
> <span data-ttu-id="33d64-179">Microsoft 365 Information Protection は、次のような場合に 2 バイト文字セットの言語をプレビューでサポートします。</span><span class="sxs-lookup"><span data-stu-id="33d64-179">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="33d64-180">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="33d64-180">Chinese (simplified)</span></span>
> - <span data-ttu-id="33d64-181">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="33d64-181">Chinese (traditional)</span></span>
> - <span data-ttu-id="33d64-182">韓国語</span><span class="sxs-lookup"><span data-stu-id="33d64-182">Korean</span></span>
> - <span data-ttu-id="33d64-183">日本語</span><span class="sxs-lookup"><span data-stu-id="33d64-183">Japanese</span></span>
>
><span data-ttu-id="33d64-184">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="33d64-184">This support is available for sensitive information types.</span></span> <span data-ttu-id="33d64-185">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポー](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d64-185">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
