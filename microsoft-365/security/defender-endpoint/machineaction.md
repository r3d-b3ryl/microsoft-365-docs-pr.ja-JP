---
title: machineAction リソースの種類
description: Microsoft Defender for Endpoint の MachineAction リソースタイプのメソッドとプロパティについて説明します。
keywords: apis, サポートされている api, get, machineaction, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187387"
---
# <a name="machineaction-resource-type"></a>MachineAction リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- 詳細については、「応答アクション [」を参照してください](respond-machine-alerts.md)。 

| メソッド                                                            | 戻り値の型                        | 説明                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [MachineActions の一覧表示](get-machineactions-collection.md)           | [マシン アクション](machineaction.md) | [ [マシン アクション] エンティティを](machineaction.md) 一覧表示します。           |
| [MachineAction の取得](get-machineaction-object.md)                  | [マシン アクション](machineaction.md) | 単一の [Machine Action エンティティを取得](machineaction.md) します。     |
| [調査パッケージの収集](collect-investigation-package.md) | [マシン アクション](machineaction.md) | コンピューターから調査パッケージを収集 [します](machine.md)。 |
| [調査パッケージ SAS URI の取得](get-package-sas-uri.md)       | [マシン アクション](machineaction.md) | 調査パッケージをダウンロードするための URI を取得します。          |
| [コンピューターを分離する](isolate-machine.md)                             | [マシン アクション](machineaction.md) | ネットワーク [からコンピューター](machine.md) を分離します。                 |
| [分離からコンピューターを解放する](unisolate-machine.md)            | [マシン アクション](machineaction.md) | 分離 [からコンピューター](machine.md) を解放します。               |
| [アプリの実行を制限する](restrict-code-execution.md)              | [マシン アクション](machineaction.md) | アプリケーションの実行を制限します。                             |
| [アプリの制限を削除する](unrestrict-code-execution.md)            | [マシン アクション](machineaction.md) | アプリケーションの実行制限を削除します。                   |
| [ウイルス対策スキャンの実行](run-av-scan.md)                              | [マシン アクション](machineaction.md) | アプリケーションを使用して AV スキャンWindows Defender実行します (該当する場合)。    |
| [オフボード マシン](offboard-machine-api.md)                       | [マシン アクション](machineaction.md) | Microsoft [Defender](machine.md) for Endpoint のオフボード マシン。 |
| [ファイルの停止と検疫](stop-and-quarantine-file.md)           | [マシン アクション](machineaction.md) | コンピューター上のファイルの実行を停止し、削除します。        |

<br>

## <a name="properties"></a>プロパティ

| プロパティ            | 種類           | 説明                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | Machine [Action エンティティの](machineaction.md) ID。                                                                                                                                                     |
| type                | 列挙           | アクションの種類。 指定できる値は、"RunAntiVirusScan"、"Offboard"、"CollectInvestigationPackage"、"Isolate"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution"、"UnrestrictCodeExecution" です。 |
| scope               | string         | アクションのスコープ。 "Full" または "Selective" for Isolation, "Quick" or "Full" for Anti-Virus scan.                                                                                                   |
| requestor           | 文字列         | アクションを実行したユーザーの ID。                                                                                                                                                               |
| requestorComment    | 文字列         | アクションを発行するときに書き込まれたコメント。                                                                                                                                                              |
| status              | 列挙           | コマンドの現在の状態。 指定できる値は、"Pending"、"InProgress"、"Succeeded"、"Failed"、"TimeOut"、"Canceled" です。                                                                                 |
| machineId           | 文字列         | アクションが [実行](machine.md) されたコンピューターの ID。                                                                                                                                              |
| machineId           | 文字列         | アクションが [実行](machine.md) されたコンピューターの名前。                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | アクションが作成された日時。                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | アクションの状態が更新された最後の日付と時刻。                                                                                                                                                     |
| relatedFileInfo     | クラス          | 2 つのプロパティが含まれる。 string 、 Enum と指定できる値 ```fileIdentifier``` : ```fileIdentifierType``` "Sha1"、"Sha256" および "Md5" 。                                                                         |


## <a name="json-representation"></a>Json 表記

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
