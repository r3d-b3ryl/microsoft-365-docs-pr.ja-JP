---
title: PowerShell を使用してドキュメント理解モデルをエクスポートおよびインポートする
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
description: SharePoint Syntexで PowerShell を使用してドキュメント理解モデルをエクスポートおよびインポートする方法について説明します。
ms.openlocfilehash: dc35d298ebd79752684c91ce944333277fcef621
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63527006"
---
# <a name="export-and-import-document-understanding-models-with-powershell"></a>PowerShell を使用してドキュメント理解モデルをエクスポートおよびインポートする

> [!IMPORTANT]
> SharePoint Syntex PowerShell コマンドレットとその他のすべての PnP コンポーネントは、アクティブなコミュニティによってサポートされるオープン ソース ツールです。 公式の Microsoft サポート チャネルのオープン ソース ツールのサポート用 SLA ではありません。

SharePoint Syntex モデルは PnP テンプレートとしてエクスポートできるため、コンテンツ センターやテナント間で再利用できます。

## <a name="export-all-models-in-a-content-center"></a>コンテンツ センター内のすべてのモデルをエクスポートする

コンテンツ センター内のすべてのモデルを 1 つの PnP テンプレートにエクスポートするには、次の [PnP PowerShell](https://pnp.github.io/powershell/) コマンドレットを使用します。

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Handlers SyntexModels
```

## <a name="export-specific-models"></a>特定のモデルをエクスポートする

コンテンツ センターから PnP テンプレートに特定のモデルをエクスポートするには、次の [PnP PowerShell](https://pnp.github.io/powershell/) コマンドレットを使用します。

```powershell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Get-PnPSiteTemplate -Out MyModels.pnp -Configuration .\extract.json
```

extract.json では、エクスポートするモデルを定義し、名前または ID でモデルを指定し、必要に応じてトレーニング データを抽出しないように構成できます。

### <a name="example---specify-model-by-name"></a>例 - 名前でモデルを指定する

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

### <a name="example---specify-model-by-id"></a>例 - ID でモデルを指定する

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

プロパティ "includeTrainingData" を含まない場合、既定の動作は含まれます。

> [!NOTE]
> ターゲット コンテンツ センターにインポートするときにモデルを編集可能にするには、トレーニング データが必要です。

## <a name="import-models-to-a-content-center"></a>コンテンツ センターにモデルをインポートする
PnP テンプレートにエクスポートされたドキュメント理解モデルは、任意のテナントのコンテンツ センターにインポートできます。 エクスポートにトレーニング データが含まれている場合、モデルはインポート後に編集可能になります。

モデルをインポートするには、次のコマンドを使用します。

```PowerShell
Connect-PnPOnline -Url "https://contoso.sharepoint.com/sites/yourContentCenter"

Invoke-PnPSiteTemplate -Path .\sampleModel.pnp
```
