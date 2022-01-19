---
title: PowerShell を使用してドキュメント理解モデルを公開する
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
description: PowerShell を使用してドキュメントSharePoint Syntexを発行する方法について説明します。
ms.openlocfilehash: 4aa5639d50145cabe5b95a11d3d927b7d2e06749
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074862"
---
# <a name="publish-document-understanding-models-with-powershell"></a>PowerShell を使用してドキュメント理解モデルを公開する

> [!IMPORTANT]
> PowerShell SharePoint Syntexおよび他のすべての PnP コンポーネントは、サポートを提供するアクティブ なコミュニティによってサポートされるオープンソース ツールです。 公式の Microsoft サポート チャネルのオープン ソース ツールのサポート用 SLA ではありません。

SharePoint Syntexモデルは、通常、テナント全体のドキュメント ライブラリに展開されます。 これは、コンテンツ センター サイトを使用して実行できますが、この記事で説明したように [、PnP PowerShell](https://pnp.github.io/powershell/) を使用して実行できます。

## <a name="listing-the-available-models-in-a-content-center"></a>コンテンツ センターで使用可能なモデルの一覧を表示する

現在のコンテンツ センター サイトに追加されたモデルのSharePoint Syntex取得するには[、Get-PnPSyntexModel コマンドレットを使用](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModel.html)します。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModel
```

## <a name="apply-a-model-to-a-library"></a>ライブラリにモデルを適用する

モデルをライブラリに適用するには [、Publish-PnPSyntexModel コマンドレットを使用](https://pnp.github.io/powershell/cmdlets/Publish-PnPSyntexModel.html) します。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Publish-PnPSyntexModel -Model "Contract Notice" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="understanding-where-a-model-is-used"></a>モデルの使用場所を理解する

モデルを多数のライブラリに展開したら、モデルを使用してライブラリの一覧を確認できます。 これは [、Get-PnPSyntexModelPublication コマンドレットを使用して実行](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModelPublication.html) できます。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModelPublication -Identity "Contract Notice"
```

## <a name="removing-a-model-from-a-library"></a>ライブラリからモデルを削除する

ライブラリからモデルを削除すると、適用と同じパターンに従い [、Unpublish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Unpublish-PnPSyntexModel.html) コマンドレットを対話型または複数のアクションのバッチとして使用できます。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourSite"
Unpublish-PnPSyntexModel -Model "Invoice model" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="apply-models-in-bulk"></a>モデルを一括で適用する

複数のモデルを複数のライブラリに発行する場合は、 

最初に、モデルとターゲットの場所を示す入力 CSV ファイルを作成します。

```CSV
ModelName,TargetSiteUrl,TargetWebServerRelativeUrl,TargetLibraryServerRelativeUrl
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/shared%20documents
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/other
Trade Confirmation,https://contoso.sharepoint.com/sites/Site2,/sites/Site2,/sites/site2/shared%20documents
```

この CSV ファイルは、リストされているモデルを適切なライブラリに発行するスクリプトへの入力として使用できます。 次の例では、バッチ処理を使用して要求の効率を上げ

```PowerShell
$contentCenterURL = "https://contoso.sharepoint.com/sites/yourSite"
$targetsCSV = "./Publish-SyntexModelBulk.csv"

Connect-PnPOnline -url $contentCenterURL

$targetLibraries = Import-Csv -Path $targetsCSV

$batch = New-PnPBatch

foreach ($target in $targetLibraries) {
    Publish-PnPSyntexModel -Model $target.ModelName -TargetSiteUrl $target.TargetSiteUrl -TargetWebServerRelativeUrl $target.TargetWebServerRelativeUrl -TargetLibraryServerRelativeUrl $target.TargetLibraryServerRelativeUrl -Batch $batch
}

Invoke-PnPBatch -Batch $batch
```
