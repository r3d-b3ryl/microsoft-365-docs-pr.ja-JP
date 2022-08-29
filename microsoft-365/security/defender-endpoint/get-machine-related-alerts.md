---
title: マシン関連のアラート API を取得する
description: マシン関連のアラートを取得する API を使用する方法について説明します。 この API を使用すると、Microsoft Defender for Endpoint内の特定のデバイスに関連するすべてのアラートを取得できます。
keywords: apis, graph api, サポートされている API, get, devices, related, alerts
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
ms.openlocfilehash: d5a7673ef10e374a830c5410ec96a057d150b36d
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326521"
---
# <a name="get-machine-related-alerts--api"></a>マシン関連のアラート API を取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

特定のデバイスに関連するすべての [アラート](alerts.md) を取得します。

## <a name="limitations"></a>制限事項

1. 構成された保持期間に従って、最後に更新されたデバイスに対してクエリを実行できます。
2. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|Alert.Read.All|'すべてのアラートを読み取る'
アプリケーション|Alert.ReadWrite.All|'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント) | Alert.Read | 'アラートの読み取り'
委任 (職場または学校のアカウント) | Alert.ReadWrite | 'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーには、少なくとも次のロール権限が必要です。"データの表示"。 アクセス許可の詳細については、「 [ロールの作成と管理](user-roles.md)」を参照してください。
> - ユーザーは、デバイス グループの設定に基づいて、デバイスにアクセスできる必要があります。 デバイス グループの設定の詳細については、「 [デバイス グループの作成と管理](machine-groups.md)」を参照してください。

## <a name="http-request"></a>HTTP 要求

```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功し、デバイスが存在する場合: 本文内の [アラート](alerts.md) エンティティの一覧を含む 200 OK。 デバイスが見つからなかった場合: 404 Not Found。
