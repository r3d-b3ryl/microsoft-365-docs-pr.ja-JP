---
title: PowerShell を使用してドキュメント理解モデルを発行する
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
description: PowerShell を使用してSharePoint Syntexドキュメント理解モデルを発行する方法について説明します。
ms.openlocfilehash: 5169e5ea5839cd5c341baa2477fd82281f5e5d76
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526486"
---
# <a name="publish-document-understanding-models-with-powershell"></a>PowerShell を使用してドキュメント理解モデルを発行する

> [!IMPORTANT]
> SharePoint Syntex PowerShell コマンドレットとその他のすべての PnP コンポーネントは、アクティブなコミュニティによってサポートされるオープン ソース ツールです。 公式の Microsoft サポート チャネルのオープン ソース ツールのサポート用 SLA ではありません。

通常、SharePoint Syntex モデルは、テナント全体のドキュメント ライブラリにデプロイされます。 これはコンテンツ センター サイトを使用して行うことができますが、この記事で説明されているように [、PnP PowerShell](https://pnp.github.io/powershell/) を使用して行うこともできます。

## <a name="listing-the-available-models-in-a-content-center"></a>コンテンツ センターで使用可能なモデルを一覧表示する

現在のSharePoint Syntex コンテンツ センター サイトに追加されたモデルの概要を確認するには、[Get-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModel.html) コマンドレットを使用します。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModel
```

## <a name="apply-a-model-to-a-library"></a>ライブラリにモデルを適用する

モデルをライブラリに適用するには、 [Publish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Publish-PnPSyntexModel.html) コマンドレットを使用します。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Publish-PnPSyntexModel -Model "Contract Notice" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="understanding-where-a-model-is-used"></a>モデルが使用される場所を理解する

モデルを多数のライブラリにデプロイしたら、モデルを使用してライブラリの一覧を確認できます。 これは、 [Get-PnPSyntexModelPublication](https://pnp.github.io/powershell/cmdlets/Get-PnPSyntexModelPublication.html) コマンドレットを使用して行うことができます。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"
Get-PnPSyntexModelPublication -Identity "Contract Notice"
```

## <a name="removing-a-model-from-a-library"></a>ライブラリからモデルを削除する

ライブラリからモデルを削除することは、適用するのと同じパターンに従い、 [Unpublish-PnPSyntexModel](https://pnp.github.io/powershell/cmdlets/Unpublish-PnPSyntexModel.html) コマンドレットを対話形式または複数のアクションのバッチとして使用して実行できます。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourSite"
Unpublish-PnPSyntexModel -Model "Invoice model" -ListWebUrl "https://contoso.sharepoint.com/sites/finance" -List "Documents"
```

## <a name="apply-models-in-bulk"></a>モデルを一括で適用する

複数のモデルを複数のライブラリに発行する場合は、モデルとターゲットの場所を示す入力 CSV ファイルを作成します。

```CSV
ModelName,TargetSiteUrl,TargetWebServerRelativeUrl,TargetLibraryServerRelativeUrl
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/shared%20documents
Contract Notice,https://contoso.sharepoint.com/sites/Site1,/sites/Site1,/sites/site1/other
Trade Confirmation,https://contoso.sharepoint.com/sites/Site2,/sites/Site2,/sites/site2/shared%20documents
```

この CSV ファイルは、一覧表示されたモデルを適切なライブラリに発行するスクリプトへの入力として使用できます。 次の例では、バッチ処理を使用して要求の効率を高めます。

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
