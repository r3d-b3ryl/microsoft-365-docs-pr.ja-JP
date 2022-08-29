---
title: スコア メソッドとプロパティ
description: 組織の公開スコア、デバイス セキュリティ スコア、およびデバイス グループ別の露出スコアを取得します。
keywords: apis, graph api, サポートされている API, スコア, 露出スコア, デバイス セキュリティ スコア, デバイス グループ別の露出スコア
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 270ce3b5a2127217c1fb2e7e568b21d5f7b33ecd
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331447"
---
# <a name="score-resource-type"></a>リソースの種類をスコア付けする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>メソッド

メソッド|戻り値の型|説明
:---|:---|:---
[暴露スコアを取得する](get-exposure-score.md)|[スコア](score.md)|組織の公開スコアを取得します。
[デバイスのセキュア スコアを取得する](get-device-secure-score.md)|[スコア](score.md)|組織のデバイスのセキュリティスコアを取得します。
[デバイス グループ別に公開スコアを一覧表示する](get-machine-group-exposure-score.md)|[スコア](score.md)|デバイス グループ別にスコアを一覧表示します。

## <a name="properties"></a>プロパティ

プロパティ|種類|説明
:---|:---|:---
スコア|倍精度浮動小数点数|現在のスコア。
Time|DateTime|この API の呼び出しが行われた日時。
RbacGroupName|文字列|デバイス グループ名。
RbacGroupId|文字列|デバイス グループ ID。
