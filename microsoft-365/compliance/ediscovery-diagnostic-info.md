---
title: 電子情報開示の診断情報を収集する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft サポート案件の電子情報開示診断情報を収集する方法について説明します。
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944394"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="d9a1e-103">電子情報開示の診断情報を収集する</span><span class="sxs-lookup"><span data-stu-id="d9a1e-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="d9a1e-104">Microsoft サポートエンジニアは、コア電子情報開示または Advanced 電子情報開示に関連したサポート事例を開く際に、問題に関する特定の情報を必要とします。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="d9a1e-105">この記事では、エンジニアによる問題の調査および解決に役立つ診断情報を収集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="d9a1e-106">通常、Microsoft サポートエンジニアによる指示があるまで、この情報を収集する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9a1e-107">この記事に記載されているコマンドレットと診断情報の出力には、組織内の訴訟や内部調査に関する機密情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="d9a1e-108">生の診断情報を Microsoft サポートに送信する前に、情報を確認し、機密情報 (他者に関する名前やその他の情報など) をに置き換えて、その情報を消し `XXXXXXX` ます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="d9a1e-109">この方法を使用すると、Microsoft サポートエンジニアに情報ががされたことも示されます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="d9a1e-110">コア電子情報開示の診断情報を収集する</span><span class="sxs-lookup"><span data-stu-id="d9a1e-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="d9a1e-111">コア電子情報開示の診断情報の収集はコマンドレットベースなので、セキュリティ & コンプライアンスセンターの PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="d9a1e-112">次の PowerShell の例では、コマンドレットを実行し、指定したテキストファイルに出力を保存します。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="d9a1e-113">ほとんどのサポートされている場合は、次のいずれかのコマンドのみを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="d9a1e-114">次のコマンドレットを実行するには、[セキュリティ & コンプライアンス </span> センター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="d9a1e-115">接続した後、次のコマンドを1つ以上実行し、プレースホルダーを実際のオブジェクト名に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="d9a1e-116">生成されたテキストファイルと赤の機密情報を確認した後、ケースで作業している Microsoft サポートエンジニアに送信します。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a1e-117">このセクションのコマンドを実行して、Microsoft 365 コンプライアンスセンターの [ **コンテンツ検索** ] ページにリストされている検索とエクスポートに関する診断情報を収集することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="d9a1e-118">検索に関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="d9a1e-118">Collect information about searches</span></span>

<span data-ttu-id="d9a1e-119">次のコマンドは、コンテンツ検索に関する問題を調査するときに役立つ情報を収集します。または、コア電子情報開示ケースに関連付けられている検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="d9a1e-120">検索アクションに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="d9a1e-120">Collect information about search actions</span></span>

<span data-ttu-id="d9a1e-121">次のコマンドは、主要な電子情報開示ケースに関連付けられたコンテンツ検索または検索結果のプレビュー、エクスポート、または削除に関する問題を調査するための情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="d9a1e-122">[ **エクスポート** ] タブに一覧表示されているエクスポートをクリックすると、検索アクションの名前を識別できます。プレビューおよび削除アクションの名前を特定するには、 **new-compliancesearchaction** コマンドレットを実行して、すべてのアクションの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="d9a1e-123">検索アクション名の形式は、、、 `_Preview` `_Export` または `_Purge` 対応する検索の名前によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="d9a1e-124">電子情報開示の保持に関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="d9a1e-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="d9a1e-125">コア電子情報開示ケースに関連付けられている電子情報開示保持が期待どおりに機能していない場合は、次のコマンドを実行して、電子情報開示保持のケースホールドポリシーおよび関連するケース保持ルールに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="d9a1e-126">次のコマンドの *ケース保持ポリシー名* は、電子情報開示ホールドの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="d9a1e-127">この名前は、コア電子情報開示ケースの **ホールド** タブで識別できます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="d9a1e-128">すべてのケース情報を収集する</span><span class="sxs-lookup"><span data-stu-id="d9a1e-128">Collect all case information</span></span>

<span data-ttu-id="d9a1e-129">場合によっては、Microsoft サポートが問題を調査するために必要な情報がわからないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="d9a1e-130">このような状況では、コア電子情報開示ケースの診断情報をすべて収集できます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="d9a1e-131">次のコマンドの *コア電子情報開示ケース名* は、Microsoft 365 コンプライアンスセンターの **コア電子情報開示** ページに表示されるケースの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="d9a1e-132">高度な電子情報開示の診断情報を収集する</span><span class="sxs-lookup"><span data-stu-id="d9a1e-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="d9a1e-133">高度な電子情報開示ケースの [ **設定** ] タブでは、ケースの診断情報をすばやくコピーできます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="d9a1e-134">診断情報は、テキストファイルに貼り付けて Microsoft サポートに送信できるように、クリップボードに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="d9a1e-135">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **> すべての電子情報開示 > 詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="d9a1e-136">ケースを選択し、[ **設定** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="d9a1e-137">[ **ケース情報** ] で、[ **選択** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-137">Under **Case Information** , click **Select**.</span></span>

4. <span data-ttu-id="d9a1e-138">[ポップアップ] ページで、[ **診断情報のコピー** ] をクリックして情報をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="d9a1e-139">メモ帳でテキストファイルを開き、その情報をテキストファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="d9a1e-140">テキストファイルを保存して、次のように名前を付け `AeD Diagnostic Info YYYY.MM.DD` ます (たとえば、 `AeD Diagnostic Info 2020.11.03` )。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="d9a1e-141">ファイルの内容を確認し、機密情報が赤で処理された後、ケースで作業している Microsoft サポートエンジニアに送信します。</span><span class="sxs-lookup"><span data-stu-id="d9a1e-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
