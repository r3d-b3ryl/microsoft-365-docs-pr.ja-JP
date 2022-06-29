---
title: Microsoft Defender for Endpointの API エクスプローラー
ms.reviewer: ''
description: API エクスプローラーを使用して、使用可能なすべての API に対する API クエリの作成と実行、テスト、および要求の送信を行います
keywords: api, explorer, send, request, get, post,
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
ms.topic: conceptual
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 5d3d81f878e201cd00e7286bd045caa5fb3e1625
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66486797"
---
# <a name="api-explorer"></a>API エクスプローラー

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint API エクスプローラーは、さまざまな Defender for Endpoint API を対話的に探索するのに役立つツールです。

API エクスプローラーを使用すると、使用可能なすべての Defender for Endpoint API エンドポイントの API クエリの作成と実行、テスト、要求の送信を簡単に行うことができます。 API エクスプローラーを使用して、操作を実行したり、ユーザー インターフェイスではまだ利用できない可能性があるデータを見つけたりします。

このツールは、アプリ開発時に役立ちます。 これにより、ユーザー アクセス設定を尊重する API クエリを実行できるため、アクセス トークンを生成する必要が減ります。

また、このツールを使用して、サンプル クエリのギャラリーを探索し、結果コード サンプルをコピーし、デバッグ情報を生成することもできます。

API エクスプローラーを使用すると、次のことができます。

- 任意のメソッドの要求を実行し、応答をリアルタイムで確認します。
- API サンプルをすばやく参照し、サポートするパラメーターを確認します。
- API 呼び出しを簡単に行います。管理ポータルのサインインを超えて認証する必要はありません。

## <a name="access-api-explorer"></a>Access API Explorer

左側のナビゲーション メニューから、[ **パートナー& API** \> **[API エクスプローラー](https://security.microsoft.com/interoperability/api-explorer)**] を選択します。

## <a name="supported-apis"></a>サポートされている API

API Explorer では、Defender for Endpoint によって提供されるすべての API がサポートされます。

サポートされている API の一覧は、 [API ドキュメント](apis-intro.md)で入手できます。

## <a name="get-started-with-the-api-explorer"></a>API エクスプローラーの使用を開始する

1. 左側のウィンドウには、使用できるサンプル要求の一覧があります。
2. リンクに従って、[ **クエリの実行**] をクリックします。

サンプルの中には、URL にパラメーターを指定する必要がある場合があります (例: {machine- ID})。

## <a name="faq"></a>よくあるご質問 (FAQ)

**API エクスプローラーを使用するには、API トークンが必要ですか?** <br>
API にアクセスするための資格情報は必要ありません。 API エクスプローラーは、要求を行うたびに Defender for Endpoint 管理ポータル トークンを使用します。

ログインしているユーザー認証資格情報は、API Explorer がユーザーに代わってデータにアクセスする権限を持っていることを確認するために使用されます。

特定の API 要求は、RBAC 特権に基づいて制限されます。 たとえば、"Submit indicator" への要求はセキュリティ管理者ロールに限定されます。
