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
# <a name="machineaction-resource-type"></a><span data-ttu-id="67f69-104">MachineAction リソースの種類</span><span class="sxs-lookup"><span data-stu-id="67f69-104">MachineAction resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="67f69-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="67f69-105">**Applies to:**</span></span>
- [<span data-ttu-id="67f69-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="67f69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67f69-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67f69-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="67f69-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="67f69-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="67f69-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="67f69-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="67f69-110">詳細については、「応答アクション [」を参照してください](respond-machine-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="67f69-110">For more information, see [Response Actions](respond-machine-alerts.md).</span></span> 

| <span data-ttu-id="67f69-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="67f69-111">Method</span></span>                                                            | <span data-ttu-id="67f69-112">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="67f69-112">Return Type</span></span>                        | <span data-ttu-id="67f69-113">説明</span><span class="sxs-lookup"><span data-stu-id="67f69-113">Description</span></span>                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [<span data-ttu-id="67f69-114">MachineActions の一覧表示</span><span class="sxs-lookup"><span data-stu-id="67f69-114">List MachineActions</span></span>](get-machineactions-collection.md)           | [<span data-ttu-id="67f69-115">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-115">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-116">[ [マシン アクション] エンティティを](machineaction.md) 一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="67f69-116">List [Machine Action](machineaction.md) entities.</span></span>           |
| [<span data-ttu-id="67f69-117">MachineAction の取得</span><span class="sxs-lookup"><span data-stu-id="67f69-117">Get MachineAction</span></span>](get-machineaction-object.md)                  | [<span data-ttu-id="67f69-118">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-118">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-119">単一の [Machine Action エンティティを取得](machineaction.md) します。</span><span class="sxs-lookup"><span data-stu-id="67f69-119">Get a single [Machine Action](machineaction.md) entity.</span></span>     |
| [<span data-ttu-id="67f69-120">調査パッケージの収集</span><span class="sxs-lookup"><span data-stu-id="67f69-120">Collect investigation package</span></span>](collect-investigation-package.md) | [<span data-ttu-id="67f69-121">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-121">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-122">コンピューターから調査パッケージを収集 [します](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="67f69-122">Collect investigation package from a [machine](machine.md).</span></span> |
| [<span data-ttu-id="67f69-123">調査パッケージ SAS URI の取得</span><span class="sxs-lookup"><span data-stu-id="67f69-123">Get investigation package SAS URI</span></span>](get-package-sas-uri.md)       | [<span data-ttu-id="67f69-124">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-124">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-125">調査パッケージをダウンロードするための URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="67f69-125">Get URI for downloading the investigation package.</span></span>          |
| [<span data-ttu-id="67f69-126">コンピューターを分離する</span><span class="sxs-lookup"><span data-stu-id="67f69-126">Isolate machine</span></span>](isolate-machine.md)                             | [<span data-ttu-id="67f69-127">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-127">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-128">ネットワーク [からコンピューター](machine.md) を分離します。</span><span class="sxs-lookup"><span data-stu-id="67f69-128">Isolate [machine](machine.md) from network.</span></span>                 |
| [<span data-ttu-id="67f69-129">分離からコンピューターを解放する</span><span class="sxs-lookup"><span data-stu-id="67f69-129">Release machine from isolation</span></span>](unisolate-machine.md)            | [<span data-ttu-id="67f69-130">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-130">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-131">分離 [からコンピューター](machine.md) を解放します。</span><span class="sxs-lookup"><span data-stu-id="67f69-131">Release [machine](machine.md) from Isolation.</span></span>               |
| [<span data-ttu-id="67f69-132">アプリの実行を制限する</span><span class="sxs-lookup"><span data-stu-id="67f69-132">Restrict app execution</span></span>](restrict-code-execution.md)              | [<span data-ttu-id="67f69-133">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-133">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-134">アプリケーションの実行を制限します。</span><span class="sxs-lookup"><span data-stu-id="67f69-134">Restrict application execution.</span></span>                             |
| [<span data-ttu-id="67f69-135">アプリの制限を削除する</span><span class="sxs-lookup"><span data-stu-id="67f69-135">Remove app restriction</span></span>](unrestrict-code-execution.md)            | [<span data-ttu-id="67f69-136">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-136">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-137">アプリケーションの実行制限を削除します。</span><span class="sxs-lookup"><span data-stu-id="67f69-137">Remove application execution restriction.</span></span>                   |
| [<span data-ttu-id="67f69-138">ウイルス対策スキャンの実行</span><span class="sxs-lookup"><span data-stu-id="67f69-138">Run antivirus scan</span></span>](run-av-scan.md)                              | [<span data-ttu-id="67f69-139">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-139">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-140">アプリケーションを使用して AV スキャンWindows Defender実行します (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="67f69-140">Run an AV scan using Windows Defender (when applicable).</span></span>    |
| [<span data-ttu-id="67f69-141">オフボード マシン</span><span class="sxs-lookup"><span data-stu-id="67f69-141">Offboard machine</span></span>](offboard-machine-api.md)                       | [<span data-ttu-id="67f69-142">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-142">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-143">Microsoft [Defender](machine.md) for Endpoint のオフボード マシン。</span><span class="sxs-lookup"><span data-stu-id="67f69-143">Offboard [machine](machine.md) from Microsoft Defender for Endpoint.</span></span> |
| [<span data-ttu-id="67f69-144">ファイルの停止と検疫</span><span class="sxs-lookup"><span data-stu-id="67f69-144">Stop and quarantine file</span></span>](stop-and-quarantine-file.md)           | [<span data-ttu-id="67f69-145">マシン アクション</span><span class="sxs-lookup"><span data-stu-id="67f69-145">Machine Action</span></span>](machineaction.md) | <span data-ttu-id="67f69-146">コンピューター上のファイルの実行を停止し、削除します。</span><span class="sxs-lookup"><span data-stu-id="67f69-146">Stop execution of a file on a machine and delete it.</span></span>        |

<br>

## <a name="properties"></a><span data-ttu-id="67f69-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="67f69-147">Properties</span></span>

| <span data-ttu-id="67f69-148">プロパティ</span><span class="sxs-lookup"><span data-stu-id="67f69-148">Property</span></span>            | <span data-ttu-id="67f69-149">種類</span><span class="sxs-lookup"><span data-stu-id="67f69-149">Type</span></span>           | <span data-ttu-id="67f69-150">説明</span><span class="sxs-lookup"><span data-stu-id="67f69-150">Description</span></span>                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="67f69-151">ID</span><span class="sxs-lookup"><span data-stu-id="67f69-151">ID</span></span>                  | <span data-ttu-id="67f69-152">Guid</span><span class="sxs-lookup"><span data-stu-id="67f69-152">Guid</span></span>           | <span data-ttu-id="67f69-153">Machine [Action エンティティの](machineaction.md) ID。</span><span class="sxs-lookup"><span data-stu-id="67f69-153">Identity of the [Machine Action](machineaction.md) entity.</span></span>                                                                                                                                                     |
| <span data-ttu-id="67f69-154">type</span><span class="sxs-lookup"><span data-stu-id="67f69-154">type</span></span>                | <span data-ttu-id="67f69-155">列挙</span><span class="sxs-lookup"><span data-stu-id="67f69-155">Enum</span></span>           | <span data-ttu-id="67f69-156">アクションの種類。</span><span class="sxs-lookup"><span data-stu-id="67f69-156">Type of the action.</span></span> <span data-ttu-id="67f69-157">指定できる値は、"RunAntiVirusScan"、"Offboard"、"CollectInvestigationPackage"、"Isolate"、"Unisolate"、"StopAndQuarantineFile"、"RestrictCodeExecution"、"UnrestrictCodeExecution" です。</span><span class="sxs-lookup"><span data-stu-id="67f69-157">Possible values are: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" and "UnrestrictCodeExecution"</span></span> |
| <span data-ttu-id="67f69-158">scope</span><span class="sxs-lookup"><span data-stu-id="67f69-158">scope</span></span>               | <span data-ttu-id="67f69-159">string</span><span class="sxs-lookup"><span data-stu-id="67f69-159">string</span></span>         | <span data-ttu-id="67f69-160">アクションのスコープ。</span><span class="sxs-lookup"><span data-stu-id="67f69-160">Scope of the action.</span></span> <span data-ttu-id="67f69-161">"Full" または "Selective" for Isolation, "Quick" or "Full" for Anti-Virus scan.</span><span class="sxs-lookup"><span data-stu-id="67f69-161">"Full" or "Selective" for Isolation, "Quick" or "Full" for Anti-Virus scan.</span></span>                                                                                                   |
| <span data-ttu-id="67f69-162">requestor</span><span class="sxs-lookup"><span data-stu-id="67f69-162">requestor</span></span>           | <span data-ttu-id="67f69-163">文字列</span><span class="sxs-lookup"><span data-stu-id="67f69-163">String</span></span>         | <span data-ttu-id="67f69-164">アクションを実行したユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="67f69-164">Identity of the person that executed the action.</span></span>                                                                                                                                                               |
| <span data-ttu-id="67f69-165">requestorComment</span><span class="sxs-lookup"><span data-stu-id="67f69-165">requestorComment</span></span>    | <span data-ttu-id="67f69-166">文字列</span><span class="sxs-lookup"><span data-stu-id="67f69-166">String</span></span>         | <span data-ttu-id="67f69-167">アクションを発行するときに書き込まれたコメント。</span><span class="sxs-lookup"><span data-stu-id="67f69-167">Comment that was written when issuing the action.</span></span>                                                                                                                                                              |
| <span data-ttu-id="67f69-168">status</span><span class="sxs-lookup"><span data-stu-id="67f69-168">status</span></span>              | <span data-ttu-id="67f69-169">列挙</span><span class="sxs-lookup"><span data-stu-id="67f69-169">Enum</span></span>           | <span data-ttu-id="67f69-170">コマンドの現在の状態。</span><span class="sxs-lookup"><span data-stu-id="67f69-170">Current status of the command.</span></span> <span data-ttu-id="67f69-171">指定できる値は、"Pending"、"InProgress"、"Succeeded"、"Failed"、"TimeOut"、"Canceled" です。</span><span class="sxs-lookup"><span data-stu-id="67f69-171">Possible values are: "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" and "Canceled".</span></span>                                                                                 |
| <span data-ttu-id="67f69-172">machineId</span><span class="sxs-lookup"><span data-stu-id="67f69-172">machineId</span></span>           | <span data-ttu-id="67f69-173">文字列</span><span class="sxs-lookup"><span data-stu-id="67f69-173">String</span></span>         | <span data-ttu-id="67f69-174">アクションが [実行](machine.md) されたコンピューターの ID。</span><span class="sxs-lookup"><span data-stu-id="67f69-174">ID of the [machine](machine.md) on which the action was executed.</span></span>                                                                                                                                              |
| <span data-ttu-id="67f69-175">machineId</span><span class="sxs-lookup"><span data-stu-id="67f69-175">machineId</span></span>           | <span data-ttu-id="67f69-176">文字列</span><span class="sxs-lookup"><span data-stu-id="67f69-176">String</span></span>         | <span data-ttu-id="67f69-177">アクションが [実行](machine.md) されたコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="67f69-177">Name of the [machine](machine.md) on which the action was executed.</span></span>                                                                                                                                            |
| <span data-ttu-id="67f69-178">creationDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="67f69-178">creationDateTimeUtc</span></span> | <span data-ttu-id="67f69-179">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="67f69-179">DateTimeOffset</span></span> | <span data-ttu-id="67f69-180">アクションが作成された日時。</span><span class="sxs-lookup"><span data-stu-id="67f69-180">The date and time when the action was created.</span></span>                                                                                                                                                                 |
| <span data-ttu-id="67f69-181">lastUpdateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="67f69-181">lastUpdateTimeUtc</span></span>   | <span data-ttu-id="67f69-182">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="67f69-182">DateTimeOffset</span></span> | <span data-ttu-id="67f69-183">アクションの状態が更新された最後の日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="67f69-183">The last date and time when the action status was updated.</span></span>                                                                                                                                                     |
| <span data-ttu-id="67f69-184">relatedFileInfo</span><span class="sxs-lookup"><span data-stu-id="67f69-184">relatedFileInfo</span></span>     | <span data-ttu-id="67f69-185">クラス</span><span class="sxs-lookup"><span data-stu-id="67f69-185">Class</span></span>          | <span data-ttu-id="67f69-186">2 つのプロパティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="67f69-186">Contains two Properties.</span></span> <span data-ttu-id="67f69-187">string 、 Enum と指定できる値 ```fileIdentifier``` : ```fileIdentifierType``` "Sha1"、"Sha256" および "Md5" 。</span><span class="sxs-lookup"><span data-stu-id="67f69-187">string ```fileIdentifier```, Enum ```fileIdentifierType``` with the possible values: "Sha1", "Sha256" and "Md5".</span></span>                                                                         |


## <a name="json-representation"></a><span data-ttu-id="67f69-188">Json 表記</span><span class="sxs-lookup"><span data-stu-id="67f69-188">Json representation</span></span>

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
