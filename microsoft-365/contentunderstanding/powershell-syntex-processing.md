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
ms.localizationpriority: medium
description: PowerShell を使用して、SharePoint Syntex ドキュメント理解モデルによる処理を要求する方法について説明します。
ms.openlocfilehash: 8f66a0cc5e59ad2ccb6b92d98cfaee8ce84470f2
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526444"
---
# <a name="use-powershell-to-request-processing-by-a-document-understanding-model"></a>PowerShell を使用してドキュメント理解モデルによる処理を要求する

> [!IMPORTANT]
> SharePoint Syntex PowerShell コマンドレットとその他のすべての PnP コンポーネントは、アクティブなコミュニティによってサポートされるオープン ソース ツールです。 公式の Microsoft サポート チャネルのオープン ソース ツールのサポート用 SLA ではありません。

ドキュメント理解モデルは、新しくアップロードされたファイルをライブラリに処理します。 UI で手動で処理を要求することもできます。 ただし、PowerShell を使用して処理をトリガーする方が効率的なシナリオが考えられます。

## <a name="request-processing-of-all-items-that-have-not-been-previously-classified"></a>以前に分類されていないすべてのアイテムの処理を要求する

このコマンドを使用して、以前に分類されていないライブラリ内のすべての項目の処理を要求できます。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents"
```

優先度の低い処理では、テナントが配置されている営業時間外の処理用にファイルをキューに入れる -OffPeak パラメーターの使用も検討できます。 詳細については、「 [Request-PnPSyntexClassifyAndExtract](https://pnp.github.io/powershell/cmdlets/Request-PnPSyntexClassifyAndExtract.html) 」を参照してください。

## <a name="request-processing-of-all-items-in-a-library"></a>ライブラリ内のすべての項目の処理を要求する

ライブラリ内のすべてのファイルの処理は、以前に分類されている場合でも要求できます。 これは、モデルを更新した場合や、ライブラリに別のモデルを追加した場合に便利な場合があります。

```PowerShell
#Note: you're connecting here to the site that holds the document library you want to process
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/finance"

Request-PnPSyntexClassifyAndExtract -List "Documents" -Force
```

> [!NOTE]
> 5,000 を超える項目で -Force オプションを使用すると、ピーク時の処理が自動的に無効になります。

## <a name="request-processing-of-all-items-based-on-a-property"></a>プロパティに基づいてすべての項目の処理を要求する

ライブラリ内の項目の特定のサブセットに処理を制限する場合は、スクリプトを使用して特定のファイル のグループを選択できます。 次の例では、スクリプトを使用してフィールドを選択し、フィールド値をフィルター処理できます。 [Get-PnPListItem](https://pnp.github.io/powershell/cmdlets/Get-PnPListItem.html) を使用して、より複雑なクエリを完了できます。

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

ファイル ごとのファイル モデルでは、バッチ処理もサポートされています。

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
