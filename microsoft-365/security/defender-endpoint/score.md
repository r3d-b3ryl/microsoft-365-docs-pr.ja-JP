---
title: スコア メソッドとプロパティ
description: 組織の露出スコア、デバイスのセキュリティで保護されたスコア、およびデバイス グループ別の露出スコアを取得します。
keywords: apis, graph api, supported apis, score, exposure score, device secure score, exposure score by device group
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500956"
---
# <a name="score-resource-type"></a>スコア リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>メソッド

メソッド |戻り値の型 |説明
:---|:---|:---
[暴露スコアを取得する](get-exposure-score.md) | [スコア](score.md) | 組織の露出スコアを取得します。
[デバイスのセキュア スコアを取得する](get-device-secure-score.md) | [スコア](score.md) | 組織デバイスのセキュリティで保護されたスコアを取得します。
[デバイス グループ別の露出スコアの一覧表示](get-machine-group-exposure-score.md)| [スコア](score.md) | デバイス グループ別にスコアを一覧表示します。

## <a name="properties"></a>プロパティ

プロパティ |  型    |   説明
:---|:---|:---
スコア | Double | 現在のスコア。
Time | DateTime | この API の呼び出しが行われた日時。
RbacGroupName | String | デバイス グループ名。
