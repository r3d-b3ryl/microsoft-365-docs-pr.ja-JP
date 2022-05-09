---
title: machineAction リソースの種類
description: Microsoft Defender for Endpointの MachineAction リソースの種類のメソッドとプロパティについて説明します。
keywords: apis, サポートされている API, get, machineaction, recent
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
ms.openlocfilehash: 625170f0e589ece6f6277dc8445f3af7bef11837
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301860"
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


- 詳細については、「 [応答アクション」を](respond-machine-alerts.md)参照してください。

|メソッド|戻り値の型|説明|
|---|---|---|
|[MachineActions を一覧表示する](get-machineactions-collection.md)|[マシン アクション](machineaction.md)|[マシン アクション エンティティを](machineaction.md)一覧表示します。|
|[MachineAction を取得する](get-machineaction-object.md)|[マシン アクション](machineaction.md)|単一の [Machine Action エンティティを](machineaction.md) 取得します。|
|[調査パッケージの収集](collect-investigation-package.md)|[マシン アクション](machineaction.md)|コンピューターから調査パッケージを収集 [します](machine.md)。|
|[調査パッケージ SAS URI の取得](get-package-sas-uri.md)|[マシン アクション](machineaction.md)|調査パッケージをダウンロードするための URI を取得します。|
|[マシンの隔離](isolate-machine.md)|[マシン アクション](machineaction.md)|[ネットワークからマシンを](machine.md)分離します。|
|[マシンを隔離から解放する](unisolate-machine.md)|[マシン アクション](machineaction.md)|分離から [マシンを](machine.md) 解放します。|
|[アプリの実行を制限する](restrict-code-execution.md)|[マシン アクション](machineaction.md)|アプリケーションの実行を制限します。|
|[アプリの制限を削除する](unrestrict-code-execution.md)|[マシン アクション](machineaction.md)|アプリケーションの実行制限を削除します。|
|[ウイルス対策スキャンを実行する](run-av-scan.md)|[マシン アクション](machineaction.md)|Windows Defenderを使用して AV スキャンを実行します (該当する場合)。|
|[マシンのオフボード](offboard-machine-api.md)|[マシン アクション](machineaction.md)|Microsoft Defender for Endpointからのオフボード [マシン](machine.md)。|
|[ファイルの停止と検疫](stop-and-quarantine-file.md)|[マシン アクション](machineaction.md)|コンピューター上のファイルの実行を停止し、削除します。|
|[ライブ応答を実行する](run-live-response.md)|[マシン アクション](machineaction.md)|デバイスで一連のライブ応答コマンドを実行する|
|[ライブ応答結果の取得](get-live-response-result.md)|URL エンティティ|インデックスを使用して、特定のライブ応答コマンドの結果ダウンロード リンクを取得します。|
|[マシン アクションのキャンセル](cancel-machine-action.md)|[マシン アクション](machineaction.md)|アクティブなマシン アクションを取り消します。|

<br>

## <a name="properties"></a>プロパティ

|プロパティ|種類|説明|
|---|---|---|
|ID|Guid|[Machine Action](machineaction.md) エンティティの ID。|
|type|列挙|アクションの種類。 指定できる値は、"RunAntiVirusScan"、"オフボード"、"Live Response"、"CollectInvestigationPackage"、"Isolate"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution"、および "UnrestrictCodeExecution" です。|
|scope|string|アクションのスコープ。 分離のための "完全" または "選択的"、ウイルス対策スキャン用の "クイック" または "完全"。|
|リクエスター|String|アクションを実行したユーザーの ID。|
|externalID|String|顧客がカスタム関連付けの要求で送信できる ID。|
|requestSource|string|アクションを送信したユーザー/アプリケーションの名前。|
| コマンド|配列|実行するコマンド。 使用できる値は PutFile、RunScript、GetFile です。|
|cancellationRequestor|String|アクションを取り消したユーザーの ID。|
|requestorComment|String|アクションを発行するときに書き込まれたコメント。|
|cancellationComment|String|アクションをキャンセルするときに書き込まれたコメント。|
|status|列挙|コマンドの現在の状態。 指定できる値は、"Pending"、"InProgress"、"Succeeded"、"Failed"、"TimeOut"、"Cancelled" です。|
|machineId|String|アクションが実行された [マシン](machine.md) の ID。|
|computerDnsName|String|アクションが実行された [マシン](machine.md) の名前。|
|creationDateTimeUtc|DateTimeOffset|アクションが作成された日時。|
|cancellationDateTimeUtc|DateTimeOffset|アクションが取り消された日時。|
|lastUpdateDateTimeUtc|DateTimeOffset|アクションの状態が更新された最後の日付と時刻。|
|title|String|マシン アクションのタイトル。|
|relatedFileInfo|クラス|2 つのプロパティが含まれています。 string `fileIdentifier`、Enum 、使用可能な値を持つ列挙型 `fileIdentifierType` : "Sha1"、"Sha256"、および "Md5"。|

## <a name="json-representation"></a>Json 表現

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
