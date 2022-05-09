---
title: ファイル リソースの種類
description: ファイルに関連する最近のMicrosoft Defender for Endpointアラートを取得します。
keywords: apis, graph api, サポートされている API, get, alerts, recent
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7fef64136e27b8b9a85163fe9e25fdf59ab6d2aa
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283487"
---
# <a name="file-resource-type"></a>ファイル リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Defender for Endpoint のファイル エンティティを表します。

## <a name="methods"></a>メソッド

メソッド|戻り値の型 |説明
:---|:---|:---
[ファイルを取得する](get-file-information.md) | [file](files.md) | 1 つのファイルを取得する 
[ファイル関連のアラートを一覧表示する](get-file-related-alerts.md) | [alert](alerts.md) コレクション | ファイルに関連付けられている [アラート](alerts.md) エンティティを取得します。
[ファイル関連のマシンを一覧表示する](get-file-related-machines.md) | [machine](machine.md) コレクション | アラートに関連付けられている [コンピューター](machine.md) エンティティを取得します。
[ファイルの統計情報](get-file-statistics.md) | 統計の概要 | 指定されたファイルの有病率を取得します。


## <a name="properties"></a>プロパティ

|プロパティ | 種類 | 説明 |
|:---|:---|:---|
|sha1 | String | ファイル コンテンツの Sha1 ハッシュ |
|sha256 | String | ファイル コンテンツの Sha256 ハッシュ |
|globalPrevalence | Null 許容 long | 組織全体のファイルの普及率 |
|globalFirstObserved | DateTimeOffset | ファイルが初めて観察されたとき |
|globalLastObserved | DateTimeOffset | ファイルが最後に観察された時刻 |
|サイズ | Null 許容 long | ファイルのサイズ |
|Filetype | String | ファイルの種類 |
|isPeFile | ブール値 | ファイルがポータブル実行可能ファイルの場合は true (例: "DLL"、"EXE"など) |
|filePublisher | String | ファイル発行元 |
|fileProductName | String | 製品名 |
|署名 | String | ファイル署名者 |
|発行者 | String | ファイル発行者 |
|signerHash | String | 署名証明書のハッシュ |
|isValidCertificate | ブール値 | Microsoft Defender for Endpoint エージェントによる証明書の署名が正常に検証されました |
|determinationType | String | ファイルの決定の種類 |
|determinationValue | String | 決定値 |

## <a name="json-representation"></a>Json 表現

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
