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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 79503f4089f1ff19bc9f47c6032b6ebc33b244d8
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171163"
---
# <a name="machineaction-resource-type"></a>MachineAction リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- 詳細については、「応答アクション [」を参照してください](respond-machine-alerts.md)。

|メソッド|戻り値の型|Description|
|---|---|---|
|[MachineActions の一覧表示](get-machineactions-collection.md)|[マシン アクション](machineaction.md)|[ [マシン アクション] エンティティを](machineaction.md) 一覧表示します。|
|[MachineAction の取得](get-machineaction-object.md)|[マシン アクション](machineaction.md)|単一の [Machine Action エンティティを取得](machineaction.md) します。|
|[調査パッケージの収集](collect-investigation-package.md)|[マシン アクション](machineaction.md)|コンピューターから調査パッケージを収集 [します](machine.md)。|
|[調査パッケージ SAS URI の取得](get-package-sas-uri.md)|[マシン アクション](machineaction.md)|調査パッケージをダウンロードするための URI を取得します。|
|[マシンの隔離](isolate-machine.md)|[マシン アクション](machineaction.md)|ネットワーク [からコンピューター](machine.md) を分離します。|
|[マシンを隔離から解放する](unisolate-machine.md)|[マシン アクション](machineaction.md)|分離 [からコンピューター](machine.md) を解放します。|
|[アプリの実行を制限する](restrict-code-execution.md)|[マシン アクション](machineaction.md)|アプリケーションの実行を制限します。|
|[アプリの制限を削除する](unrestrict-code-execution.md)|[マシン アクション](machineaction.md)|アプリケーションの実行制限を削除します。|
|[ウイルス対策スキャンを実行する](run-av-scan.md)|[マシン アクション](machineaction.md)|アプリケーションを使用して AV スキャンWindows Defender実行します (該当する場合)。|
|[マシンのオフボード](offboard-machine-api.md)|[マシン アクション](machineaction.md)|Microsoft [Defender](machine.md) for Endpoint のオフボード マシン。|
|[ファイルの停止と検疫](stop-and-quarantine-file.md)|[マシン アクション](machineaction.md)|コンピューター上のファイルの実行を停止し、削除します。|
|[ライブ応答を実行する](run-live-response.md)|[マシン アクション](machineaction.md)|デバイスで一連のライブ応答コマンドを実行する|
|[ライブ応答結果の取得](get-live-response-result.md)|URL エンティティ|インデックスによって特定のライブ応答コマンドの結果ダウンロード リンクを取得します。|
|[マシン アクションのキャンセル](cancel-machine-action.md)|[マシン アクション](machineaction.md)|アクティブなコンピューターの操作を取り消します。|

<br>

## <a name="properties"></a>プロパティ

|プロパティ|種類|説明|
|---|---|---|
|ID|Guid|Machine [Action エンティティの](machineaction.md) ID。|
|type|列挙|アクションの種類。 指定できる値は、「RunAntiVirusScan」、"Offboard"、"Live Response"、"CollectInvestigationPackage"、"Isolate"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution"、"UnrestrictCodeExecution"です。|
|scope|string|アクションのスコープ。 "Full" または "Selective" for Isolation, "Quick" or "Full" for Anti-Virus scan.|
|requestor|String|アクションを実行したユーザーの ID。|
|externalID|String|カスタム相関関係の要求で顧客が送信できる ID。|
|requestSource|string|アクションを送信したユーザー/アプリケーションの名前。|
|コマンド|配列|実行するコマンド。 使用できる値は PutFile、RunScript、GetFile です。|
|cancellationRequestor|String|アクションをキャンセルしたユーザーの ID。|
|requestorComment|String|アクションを発行するときに書き込まれたコメント。|
|cancellationComment|String|アクションをキャンセルするときに書き込まれたコメント。|
|status|列挙|コマンドの現在の状態。 指定できる値は、"Pending"、"InProgress"、"Succeeded"、"Failed"、"TimeOut"、"キャンセル" です。|
|machineId|String|アクションが [実行](machine.md) されたコンピューターの ID。|
|computerDnsName|String|アクションが [実行](machine.md) されたコンピューターの名前。|
|creationDateTimeUtc|DateTimeOffset|アクションが作成された日時。|
|cancellationDateTimeUtc|DateTimeOffset|アクションが取り消された日時。|
|lastUpdateDateTimeUtc|DateTimeOffset|アクションの状態が更新された最後の日付と時刻。|
|title|String|コンピューター アクションのタイトル。|
|relatedFileInfo|クラス|2 つのプロパティが含まれる。 string 、 Enum と指定できる値 `fileIdentifier` : `fileIdentifierType` "Sha1"、"Sha256"、および "Md5" 。|

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
