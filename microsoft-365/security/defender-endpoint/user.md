---
title: ユーザー リソースの種類
description: ユーザーに関連する最近の Microsoft Defender for Endpoint アラートを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 5a3ea32227f64fbf00563f2b48f99b0a21e5510e
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53648857"
---
# <a name="user-resource-type"></a>ユーザー リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


メソッド|戻り値の型 |説明
:---|:---|:---
[ユーザー関連のアラートの一覧表示](get-user-related-alerts.md) | [alert](alerts.md) コレクション |  ユーザーに関連付けられているすべてのアラートを一覧表示 [します](user.md)。
[リスト ユーザー関連のデバイス](get-user-related-machines.md) | [machine](machine.md) コレクション | ユーザーがログオンしていたすべてのデバイスを一覧表示 [します](user.md)。
