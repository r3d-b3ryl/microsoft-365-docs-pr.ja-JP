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
description: Microsoft サポート ケースの電子情報開示診断情報を収集する方法について説明します。
ms.openlocfilehash: b2441e0b7af8a82e24a8acca9e000e954e1c8964
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362596"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="0e03d-103">電子情報開示の診断情報を収集する</span><span class="sxs-lookup"><span data-stu-id="0e03d-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="0e03d-104">場合によっては、Microsoft サポート エンジニアは、Core eDiscovery または電子情報開示に関連するサポート ケースを開く際に、問題に関する特定の情報をAdvanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="0e03d-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="0e03d-105">この記事では、サポート エンジニアが問題を調査および解決するために診断情報を収集する方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0e03d-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="0e03d-106">通常、Microsoft サポート エンジニアからこの情報の収集を求めるまで、この情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e03d-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e03d-107">この記事で説明するコマンドレットと診断情報からの出力には、組織内の訴訟や内部調査に関する機密情報が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e03d-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="0e03d-108">生の診断情報を Microsoft サポートに送信する前に、情報を確認し、機密情報 (訴訟や調査の関係者に関する名前や他の情報など) を置き換えてやり直す必要があります `XXXXXXX` 。</span><span class="sxs-lookup"><span data-stu-id="0e03d-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="0e03d-109">このメソッドを使用すると、Microsoft サポート エンジニアに情報が再編集されたというメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e03d-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="0e03d-110">Core eDiscovery の診断情報を収集する</span><span class="sxs-lookup"><span data-stu-id="0e03d-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="0e03d-111">Core eDiscovery の診断情報の収集はコマンドレットベースなので、コンプライアンス センター PowerShell でセキュリティ &使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e03d-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="0e03d-112">次の PowerShell の例では、コマンドレットを実行し、指定したテキスト ファイルに出力を保存します。</span><span class="sxs-lookup"><span data-stu-id="0e03d-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="0e03d-113">ほとんどのサポートケースでは、これらのコマンドのいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e03d-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="0e03d-114">次のコマンドレットを実行するには、コンプライアンス センター [PowerShell &に接続します </span> ](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0e03d-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="0e03d-115">接続が終わると、次の 1 つ以上のコマンドを実行し、プレースホルダーを実際のオブジェクト名に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e03d-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="0e03d-116">生成されたテキスト ファイルを確認し、機密情報を編集した後、ケースに取り組む Microsoft サポート エンジニアに送信します。</span><span class="sxs-lookup"><span data-stu-id="0e03d-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="0e03d-117">また、このセクションのコマンドを実行して、検索とエクスポートの診断情報を収集し、このセクションの[コンテンツ検索] ページに一覧表示Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="0e03d-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="0e03d-118">検索に関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="0e03d-118">Collect information about searches</span></span>

<span data-ttu-id="0e03d-119">次のコマンドは、コンテンツ検索またはコア電子情報開示ケースに関連付けられた検索に関する問題を調査するときに役立つ情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="0e03d-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="0e03d-120">検索アクションに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="0e03d-120">Collect information about search actions</span></span>

<span data-ttu-id="0e03d-121">次のコマンドは、コンテンツ検索または Core 電子情報開示ケースに関連付けられた検索の結果をプレビュー、エクスポート、または削除する際の問題を調査するために情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="0e03d-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="0e03d-122">[エクスポート] タブに表示されているエクスポートをクリックすると、検索アクションの名前 **を識別** できます。プレビューアクションと削除アクションの名前を識別するには **、Get-ComplianceSearchAction** コマンドレットを実行して、すべてのアクションの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0e03d-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="0e03d-123">検索アクション名の形式は、対応する検索の名前に 、を追加 `_Preview` `_Export` `_Purge` して作成されます。</span><span class="sxs-lookup"><span data-stu-id="0e03d-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="0e03d-124">電子情報開示ホールドに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="0e03d-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="0e03d-125">Core 電子情報開示ケースに関連付けられている電子情報開示ホールドが期待通り機能しない場合は、次のコマンドを実行して、電子情報開示ホールドのケースホールド ポリシーと関連付けられたケースホールド ルールに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="0e03d-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="0e03d-126">次 *のコマンドのケース* 保持ポリシー名は、電子情報開示ホールドの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="0e03d-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="0e03d-127">この名前は、コア電子 **情報開示ケースの [** 保留] タブで識別できます。</span><span class="sxs-lookup"><span data-stu-id="0e03d-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="0e03d-128">すべてのケース情報を収集する</span><span class="sxs-lookup"><span data-stu-id="0e03d-128">Collect all case information</span></span>

<span data-ttu-id="0e03d-129">Microsoft サポートが問題を調査するために必要な情報が明らかではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e03d-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="0e03d-130">この状況では、コア電子情報開示ケースのすべての診断情報を収集できます。</span><span class="sxs-lookup"><span data-stu-id="0e03d-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="0e03d-131">次 *のコマンドのコア* 電子情報開示ケース名は、次のコマンドの [コア電子情報開示] ページに表示されるケースの名前と同Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="0e03d-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="0e03d-132">ユーザーの診断情報をAdvanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0e03d-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="0e03d-133">ケース **設定** の [Advanced eDiscovery] タブを使用すると、ケースの診断情報をすばやくコピーできます。</span><span class="sxs-lookup"><span data-stu-id="0e03d-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="0e03d-134">診断情報はクリップボードに保存され、テキスト ファイルに貼り付け、Microsoft サポートに送信できます。</span><span class="sxs-lookup"><span data-stu-id="0e03d-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="0e03d-135">[電子情報開示 [https://compliance.microsoft.com](https://compliance.microsoft.com/) の詳細] に移動し、[すべての> **を>] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0e03d-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="0e03d-136">ケースを選択し、[追加] タブ **設定** します。</span><span class="sxs-lookup"><span data-stu-id="0e03d-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="0e03d-137">[ケース **情報] で、[** 選択] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0e03d-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="0e03d-138">[フライアウト] ページで、[診断 **情報のコピー** ] をクリックして、情報をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0e03d-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="0e03d-139">テキスト ファイル (メモ帳) を開き、テキスト ファイルに情報を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0e03d-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="0e03d-140">テキスト ファイルを保存し、名前を付けます `AeD Diagnostic Info YYYY.MM.DD` (たとえば `AeD Diagnostic Info 2020.11.03` )。</span><span class="sxs-lookup"><span data-stu-id="0e03d-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="0e03d-141">ファイルを確認して機密情報を編集した後、ケースに取り組む Microsoft サポート エンジニアに送信します。</span><span class="sxs-lookup"><span data-stu-id="0e03d-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
