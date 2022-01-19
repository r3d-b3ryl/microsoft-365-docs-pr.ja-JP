---
title: PowerShell を使用したドキュメント理解モデルのエクスポートとインポート
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
description: PowerShell を使用してドキュメント理解モデルをエクスポートおよびインポートする方法についてSharePoint Syntex
ms.openlocfilehash: 289d802fdea50daa0261ec16ea760e9a57b0e9c5
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074896"
---
# <a name="export-and-import-document-understanding-models-with-powershell"></a>PowerShell を使用したドキュメント理解モデルのエクスポートとインポート

> [!IMPORTANT]
> PowerShell SharePoint Syntexおよび他のすべての PnP コンポーネントは、サポートを提供するアクティブ なコミュニティによってサポートされるオープンソース ツールです。 公式の Microsoft サポート チャネルのオープン ソース ツールのサポート用 SLA ではありません。

SharePoint Syntexは PnP テンプレートとしてエクスポートし、コンテンツ センターまたはテナント間で再利用できます。

## <a name="export-all-models-in-a-content-center"></a>コンテンツ センターのすべてのモデルをエクスポートする

コンテンツ センターのすべてのモデルを 1 つの PnP テンプレートにエクスポートするには、次の [PnP PowerShell コマンドレットを](https://pnp.github.io/powershell/) 使用します。

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Handlers SyntexModels
```

## <a name="export-specific-models"></a>特定のモデルをエクスポートする

コンテンツ センターから PnP テンプレートに特定のモデルをエクスポートするには、次の [PnP PowerShell コマンドレットを](https://pnp.github.io/powershell/) 使用します。

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Configuration .\extract.json
```

extract.json は、エクスポートするモデルを定義し、名前または ID でモデルを指定し、必要に応じてトレーニング データを抽出しない構成を可能にする

### <a name="example--specify-model-by-name"></a>例- 名前でモデルを指定する

```json
{
    "$schema": "https://developer.microsoft.com/en-us/json-schemas/pnp/provisioning/202102/extract-configuration.schema.json",
    "persistAssetFiles": true,
    "handlers": [        
        "SyntexModels"
    ],
    "syntexModels": {
        "models": [
            {
                "name": "Sample - benefits change notice.classifier"
            }
        ]
    }
}
```

### <a name="example--specify-model-by-id"></a>例- ID でモデルを指定する

```json
{
    "$schema": "https://developer.microsoft.com/en-us/json-schemas/pnp/provisioning/202102/extract-configuration.schema.json",
    "persistAssetFiles": true,
    "handlers": [        
        "SyntexModels"
    ],
    "syntexModels": {
        "models": [
            {
                "id": 3,
                "excludeTrainingData": true
            }
        ]
    }
}
```

"includeTrainingData" プロパティを含めない場合、既定の動作は含まれます。

> 注: モデルをコピー先コンテンツ センターにインポートするときに編集可能になるには、トレーニング データが必要です

## <a name="import-models-to-a-content-center"></a>モデルをコンテンツ センターにインポートする
PnP テンプレートにエクスポートされたドキュメント理解モデルは、任意のテナントのコンテンツ センターにインポートできます。 エクスポートにトレーニング データが含まれている場合は、インポート後にモデルを編集できます。

モデルをインポートするには、次のコマンドを使用します。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Invoke-PnPSiteTemplate -Path .\sampleModel.pnp
```
