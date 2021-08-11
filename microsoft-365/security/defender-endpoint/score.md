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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 53abd7fa11d7e49059daef39be58f923e2c858d65bc9b6051c12886ac8a9137d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53792964"
---
# <a name="score-resource-type"></a>スコア リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>メソッド

メソッド|戻り値の型|説明
:---|:---|:---
[暴露スコアを取得する](get-exposure-score.md)|[スコア](score.md)|組織の露出スコアを取得します。
[デバイスのセキュア スコアを取得する](get-device-secure-score.md)|[スコア](score.md)|組織デバイスのセキュリティで保護されたスコアを取得します。
[デバイス グループ別の露出スコアの一覧表示](get-machine-group-exposure-score.md)|[スコア](score.md)|デバイス グループ別にスコアを一覧表示します。

## <a name="properties"></a>プロパティ

プロパティ|種類|説明
:---|:---|:---
スコア|Double|現在のスコア。
Time|DateTime|この API の呼び出しが行われた日時。
RbacGroupName|String|デバイス グループ名。
