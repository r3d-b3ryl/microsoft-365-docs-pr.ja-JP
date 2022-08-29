---
title: ユーザー リソースの種類
description: ユーザーに関連する最近のMicrosoft Defender for Endpointアラートを取得します。
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: da2032da79666016a03323c22cbf29030b920921
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67330589"
---
# <a name="user-resource-type"></a>ユーザー リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

メソッド|戻り値の型|説明
---|---|---
[ユーザー関連のアラートを一覧表示する](get-user-related-alerts.md)|[alert](alerts.md) コレクション|ユーザーに関連付けられているすべてのアラートを一覧表示 [します](user.md)。
[ユーザー関連デバイスの一覧表示](get-user-related-machines.md)|[machine](machine.md) コレクション|ユーザーがログオンしたすべてのデバイスを一覧表示 [します](user.md)。
