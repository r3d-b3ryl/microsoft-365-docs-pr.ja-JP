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
ms.openlocfilehash: 24f6bb636c702438be8ca9520c6523031f297410
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683765"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="e0b8d-103">キーワード ディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="e0b8d-103">Create a keyword dictionary</span></span>

<span data-ttu-id="e0b8d-104">データ損失防止 (DLP) は、機密アイテムの識別、監視、および保護を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="e0b8d-105">機密アイテムの識別には、特に汎用コンテンツ (医療関連の通信など) または不適切な言語や露骨な表現を識別するときに、キーワードを検索する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="e0b8d-106">機密情報の種類でキーワード リストを作成することができますが、キーワード リストにはサイズの制限があり、リストの作成や編集を行うには、XML を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="e0b8d-107">キーワード辞書は、キーワードの管理が簡単になり、はるかに大規模で、辞書で最大 1 MB の用語 (圧縮後) をサポートし、あらゆる言語をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="e0b8d-108">テナント制限は、圧縮後も 1 MB です。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="e0b8d-109">1 MB の圧縮後の制限は、テナント全体で結合されたすべての辞書が 100 万文字近くになる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="e0b8d-110">キーワード辞書の制限</span><span class="sxs-lookup"><span data-stu-id="e0b8d-110">Keyword dictionary limits</span></span>

<span data-ttu-id="e0b8d-111">テナントごとに作成できるキーワード辞書ベースの機密情報の種類は 50 個に制限されています。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="e0b8d-112">テナントにあるキーワード辞書の数を確認するには、「[セキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)」の手順を使用して接続し、テナントに接続してこの PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="e0b8d-113">キーワード辞書を作成する基本的な手順</span><span class="sxs-lookup"><span data-stu-id="e0b8d-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="e0b8d-p103">辞書のキーワードを、さまざまなソースから作成することができます。一般的な例として、サービスにインポートされたファイルや PowerShell コマンドレットでインポートされたファイル (.csv または .txt リストなど)、PowerShell コマンドレットで直接入力するリスト、または既存の辞書などがあります。キーワード辞書を作成するときには、次の同じ基本手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="e0b8d-116">**セキュリティ/コンプライアンス センター** ([https://protection.office.com](https://protection.office.com)) を使用するか、**セキュリティ &amp; コンプライアンス センター PowerShell** に接続します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="e0b8d-117">**目的のソースからキーワードを定義または読み込みます**。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="e0b8d-118">ウィザードとコマンドレットの両方でコンマ区切りキーワード リストを使ってカスタム キーワード ディクショナリを作成できるので、この手順はキーワードがどこから得られるかによって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="e0b8d-119">いったん読み込まれたキーワードは、インポートされる前にエンコードされてバイト配列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="e0b8d-120">**ディクショナリを作成します**。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-120">**Create your dictionary**.</span></span> <span data-ttu-id="e0b8d-121">名前と説明を選択し、ディクショナリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="e0b8d-122">セキュリティ/コンプライアンス センターを使用してキーワード ディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="e0b8d-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="e0b8d-123">ユーザー辞書のキーワードを作成してインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="e0b8d-124">セキュリティ/コンプライアンス センターに接続します ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="e0b8d-125">**[分類] > [機密情報の種類]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="e0b8d-126">**[作成]** を選択し、機密情報の **名前** と **説明** を入力してから、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="e0b8d-127">**[要素を追加する]** を選択し、**[次を含むコンテンツを検出する]** ドロップダウン リストの中から **[辞書 (大規模なキーワード)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="e0b8d-128">**[辞書を追加する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="e0b8d-129">検索コントロールで、**[ここで新しいキーワード ディクショナリを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="e0b8d-130">ユーザー辞書の **名前** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="e0b8d-131">**[インポート]** を選択し、キーワード ファイルの種類に応じて **[テキストから]** か **[csv から]** のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="e0b8d-132">ファイル ダイアログで、ローカル PC またはネットワーク ファイル共有からキーワード ファイルを選択し、**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="e0b8d-133">**[保存]** を選択し、**[キーワード ディクショナリ]** リストから該当するユーザー辞書を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="e0b8d-134">**[追加]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="e0b8d-135">機密情報の種類の選択を最終的に確認し、**[終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="e0b8d-136">PowerShell を使用してファイルからキーワード ディクショナリを作成する</span><span class="sxs-lookup"><span data-stu-id="e0b8d-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="e0b8d-137">大きなディクショナリを作成する必要がある場合、それは他のソースからエクスポートされたファイルやリストからのキーワードを使用するためであることが多いです。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="e0b8d-138">この場合、外部メールの画面に対する不適切な言語のリストを含めて、キーワード ディクショナリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="e0b8d-139">まず、[セキュリティ &amp; コンプライアンス センター PowerShell](/powershell/exchange/connect-to-scc-powershell) に接続します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="e0b8d-140">キーワードをテキスト ファイルにコピーし、各キーワードが別個の行にあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="e0b8d-p107">テキスト ファイルを、Unicode エンコードで、メモ帳 \> **名前を付けて保存** \> **エンコード** \> **Unicode** に保存します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="e0b8d-143">このコマンドレットを実行して、ファイルを変数として読み取ります。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="e0b8d-144">このコマンドレットを実行して、ディクショナリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="e0b8d-145">カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う</span><span class="sxs-lookup"><span data-stu-id="e0b8d-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="e0b8d-146">キーワード ディクショナリは、カスタムの機密情報の種類に一致する要件の一部として、または機密情報の種類自体として使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="e0b8d-147">どちらも、[カスタムの機密情報の種類](create-a-custom-sensitive-information-type-in-scc-powershell.md) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="e0b8d-148">リンク先の記事の手順に従って、機密情報の種類を作成します。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="e0b8d-149">XML がある場合は、それを使用するディクショナリの GUID 識別子が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="e0b8d-150">ディクショナリの ID を取得するには、このコマンドを実行して **ID** のプロパティ値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="e0b8d-151">コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="e0b8d-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="e0b8d-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="e0b8d-p109">カスタムの機密情報の種類の XML に ID を貼り付けて、アップロードします。これで、ディクショナリは機密情報の種類のリストに表示され、それをポリシーで使用して、一致するキーワードがいくつ必要かを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
> <span data-ttu-id="e0b8d-155">Microsoft 365 Information Protection は、次のような場合に 2 バイト文字セットの言語をプレビューでサポートします。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-155">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="e0b8d-156">中国語 (簡体字)</span><span class="sxs-lookup"><span data-stu-id="e0b8d-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="e0b8d-157">中国語 (繁体字)</span><span class="sxs-lookup"><span data-stu-id="e0b8d-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="e0b8d-158">韓国語</span><span class="sxs-lookup"><span data-stu-id="e0b8d-158">Korean</span></span>
> - <span data-ttu-id="e0b8d-159">日本語</span><span class="sxs-lookup"><span data-stu-id="e0b8d-159">Japanese</span></span>
>
><span data-ttu-id="e0b8d-160">このサポートは、機密情報の種類で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="e0b8d-161">詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポー](mip-dbcs-relnotes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0b8d-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
