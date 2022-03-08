---
title: ライブ応答ライブラリのメソッドとプロパティ
description: ライブ応答ライブラリのメソッドとプロパティを使用する方法について説明します。
keywords: apis, graph api, supported apis, get, devices
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
ms.technology: m365d
ms.openlocfilehash: 74f4fbe69135433597492854428b34449fbd0260
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319279"
---
#  <a name="live-response-library-methods-and-properties"></a>ライブ応答ライブラリのメソッドとプロパティ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>メソッド

| **メソッド**          | **戻り値の型**         | **説明**                         |
|---------------------|-------------------------|-----------------------------------------|
| リスト ライブラリ ファイル  | ライブラリ ファイル コレクション | リスト ライブラリ ファイル エンティティ              |
| アップロードライブラリへのアクセス   | ライブラリ ファイル エンティティ     | アップロードをライブ応答ライブラリに保存する |
| ライブラリから削除する | コンテンツはありません              | ライブラリ ファイル エンティティの削除              |

## <a name="properties"></a>プロパティ

| **Property** | **型**                         | **説明**                                        |
|--------------|----------------------------------|--------------------------------------------------------|
| コマンド     | Live Response コマンド コレクション | Command オブジェクトの配列。 「ライブ [応答コマンド」を参照してください](live-response.md#live-response-commands)。 |

