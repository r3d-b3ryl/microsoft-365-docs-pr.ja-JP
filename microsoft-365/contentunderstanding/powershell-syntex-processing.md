---
title: PowerShell を使用してドキュメント理解モデルによる処理を要求する
ms.author: jaeccles
author: jameseccles
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
ms.localizationpriority: normal
description: PowerShell を使用して、ドキュメント理解モデルで処理SharePoint Syntexする方法について説明します。
ms.openlocfilehash: f6e013bddbec3c0f12bb8665de538967adfff116
ms.sourcegitcommit: d37fce3b708ea5232b4102fd0e693f4bf17a8948
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2022
ms.locfileid: "62159675"
---
# <a name="use-powershell-to-request-processing-by-a-document-understanding-model"></a>PowerShell を使用してドキュメント理解モデルによる処理を要求する

> [!IMPORTANT]
> PowerShell SharePoint Syntexおよび他のすべての PnP コンポーネントは、サポートを提供するアクティブ なコミュニティによってサポートされるオープンソース ツールです。 公式の Microsoft サポート チャネルのオープン ソース ツールのサポート用 SLA ではありません。

ドキュメント理解モデルは、新しくアップロードされたファイルをライブラリに処理します。 UI で手動で処理を要求することもできます。 ただし、PowerShell を使用して処理をトリガーする方が効率的なシナリオがある場合があります。

## <a name="request-processing-of-all-items-that-have-not-been-previously-classified"></a>以前に分類されていないすべてのアイテムの処理を要求する

次のコマンドを使用して、以前に分類されていないライブラリ内のすべてのアイテムの処理を要求できます。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents"
```

優先度の低い処理では、テナントがある営業時間外に処理するファイルをキューに入れる -OffPeak パラメーターの使用も検討できます。 詳細 [については、「Request-PnPSyntexClassifyAndExtract」](https://pnp.github.io/powershell/cmdlets/Request-PnPSyntexClassifyAndExtract.html) を参照してください。

## <a name="request-processing-of-all-items-in-a-library"></a>ライブラリ内のすべてのアイテムの処理を要求する

以前に分類されている場合でも、ライブラリ内のすべてのファイルの処理を要求できます。 これは、モデルを更新した場合や、別のモデルをライブラリに追加した場合に役立ちます。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents" -Force
```

> [!NOTE]
> 5000 を超えるアイテムで -Force オプションを使用すると、ピーク処理が自動的に有効になります。

## <a name="request-processing-of-all-items-based-on-a-property"></a>プロパティに基づいてすべてのアイテムの処理を要求する

ライブラリ内のアイテムの特定のサブセットに処理を制限する場合は、スクリプトを使用して特定のファイル グループを選択できます。 次の例では、スクリプトを使用してフィールドを選択し、フィールド値をフィルター処理できます。 [Get-PnPListItem](https://pnp.github.io/powershell/cmdlets/Get-PnPListItem.html)を使用すると、より複雑なクエリを実行できます。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"
$list = Get-PnPList -Identity "Documents"
# Set the field name to filter items by
$fieldName = "Vendor"
# Set the field value to filter by
$fieldFilter = "Fabrikam"

$listItems = (Get-PnPListItem -List $list -fields $fieldName).fieldValues
$targetItems = $listItems | Where-Object -Property Provider -EQ -Value $fieldFilter

# Create a new batch
$batch = New-PnPBatch

# Add files to classify to the batch
foreach ($listItem in $targetItems) {
    Request-PnPSyntexClassifyAndExtract -FileUrl $listItem.FileRef -Batch $classifyBatch
}

# Execute batch
Invoke-PnPBatch -Batch $batch
```

## <a name="request-processing-of-specific-files"></a>特定のファイルの処理を要求する

特定のファイルに対して処理を要求することもできます。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/contoso contract.docx"
```

ファイル モデル別のファイルは、バッチ処理もサポートしています。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

# Create a new batch
$batch = New-PnPBatch

# Add files to classify to the batch
Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/contoso contract.docx" -Batch $batch
Request-PnPSyntexClassifyAndExtract -FileUrl "/sites/finance/documents/relecloud contract.docx" -Batch $batch

# Execute batch
Invoke-PnPBatch -Batch $batch
```
