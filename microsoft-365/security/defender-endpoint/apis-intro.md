---
title: Microsoft Defender for Endpoint API にアクセスする
ms.reviewer: ''
description: API を使用してワークフローを自動化し、Microsoft Defender for Endpoint機能に基づいてイノベーションを行う方法について説明します
keywords: apis, api, wdatp, open api, microsoft defender for endpoint API, microsoft defender atp, public api, サポートされている API, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度な捜索, クエリ
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 3638357d2c1440604858fabfa42e5df32569aed3
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65172254"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender for Endpoint API にアクセスする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender for Business](../defender-business/index.yml)

> [!IMPORTANT]
> 高度なハンティング機能は Defender for Business には含まれません。 [Microsoft Defender for Endpoint プラン 1 とMicrosoft Defender for Businessを比較する方法 2 を](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)参照してください。

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint は、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API を使用すると、Defender for Endpoint 機能に基づいてワークフローを自動化し、イノベーションを行えます。 API アクセスには、OAuth2.0 認証が必要です。 詳細については、「[OAuth 2.0 Authorization Code Flow」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

Defender for Endpoint の API の概要については、このビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

一般に、API を使用するには、次の手順を実行する必要があります。

- [AAD アプリケーション](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)を作成する
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用して Defender for Endpoint API にアクセスする

**アプリケーション コンテキスト** または **ユーザー コンテキスト** を使用して Defender for Endpoint API にアクセスできます。

- **アプリケーション コンテキスト: (推奨)**

  サインインしているユーザーが存在せずに実行するアプリで使用されます。 たとえば、バックグラウンド サービスまたはデーモンとして実行されるアプリなどです。

  アプリケーション コンテキストを使用して Defender for Endpoint API にアクセスするには、次の手順を実行する必要があります。

  1. AAD Web アプリケーションを作成します。
  2. 目的のアクセス許可をアプリケーションに割り当てます (例: "アラートの読み取り"、"マシンの分離")。
  3. このアプリケーションのキーを作成します。
  4. キーを使用してアプリケーションを使用してトークンを取得します。
  5. トークンを使用してMicrosoft Defender for Endpoint API にアクセスする

     詳細については、「 [アプリケーション コンテキストを使用したアクセスの取得](exposed-apis-create-app-webapp.md)」を参照してください。

- **ユーザー コンテキスト:**

  ユーザーの代わりに API でアクションを実行するために使用されます。

  ユーザー コンテキストを使用して Defender for Endpoint API にアクセスするための手順:

  1. ネイティブ アプリケーションAAD作成します。
  2. アプリケーションに必要なアクセス許可 ("アラートの読み取り"、"マシンの分離" など) を割り当てます。
  3. ユーザー資格情報を使用してアプリケーションを使用してトークンを取得します。
  4. トークンを使用してMicrosoft Defender for Endpoint API にアクセスする

     詳細については、「 [ユーザー コンテキストを使用したアクセスの取得](exposed-apis-create-app-nativeapp.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint API](exposed-apis-list.md)
- [アプリケーション コンテキストを使用してMicrosoft Defender for Endpointにアクセスする](exposed-apis-create-app-webapp.md)
- [ユーザー コンテキストを使用してMicrosoft Defender for Endpointにアクセスする](exposed-apis-create-app-nativeapp.md)
