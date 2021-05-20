---
title: Microsoft Defender for Endpoint API にアクセスする
ms.reviewer: ''
description: API を使用してワークフローを自動化し、エンドポイント用 Microsoft Defender 機能に基づく革新を行う方法を学びます。
keywords: apis, api, wdatp, オープン API, エンドポイント API 用マイクロソフトディフェンダー, マイクロソフトディフェンダー atp, パブリック API, サポートされている API, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度な狩猟, クエリ
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571831"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender for Endpoint API にアクセスする 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**適用対象:** 
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



エンドポイントの Defender は、プログラム API のセットを通じてデータとアクションの多くを公開します。 これらの API を使用すると、ワークフローを自動化し、Endpoint 用 Defender 機能に基づいてイノベーションを起こします。 API アクセスには OAuth2.0 認証が必要です。 詳細については[、「OAuth 2.0 認証コード Flow」](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)を参照してください。

エンドポイントの API の Defender の概要については、このビデオをご覧ください。 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

一般に、API を使用するには、次の手順を実行する必要があります。
- [AAD アプリケーション](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)を作成する
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用してエンドポイント API の Defender にアクセスする


**アプリケーション コンテキスト** または **ユーザー** コンテキスト を使用して、Endpoint API の Defender にアクセスできます。

- **アプリケーションコンテキスト: (推奨)** <br>
    サインインしているユーザーが存在しないまま実行されるアプリで使用されます。 たとえば、バックグラウンド サービスまたはデーモンとして実行されるアプリなどです。

    アプリケーションコンテキストを持つエンドポイントAPIのDefenderにアクセスするために実行する必要がある手順:

  1. AAD Web アプリケーションを作成します。
  2. 「アラートの読み取り」「マシンの分離」など、アプリケーションに必要なアクセス許可を割り当てます。 
  3. このアプリケーションのキーを作成します。
  4. アプリケーションをキーと共に使用してトークンを取得します。
  5. エンドポイント API の Microsoft Defender にアクセスするトークンを使用します。

     詳細については、「アプリケーション [コンテキストを使用したアクセスの取得](exposed-apis-create-app-webapp.md)」を参照してください。


- **ユーザー コンテキスト:** <br>
    ユーザーの代わりに API でアクションを実行するために使用します。

    アプリケーションコンテキストを使用してエンドポイントAPIのDefenderにアクセスするための手順:

  1. AAD ネイティブ アプリケーションを作成します。
  2. 「アラートの読み取り」「マシンの分離」など、アプリケーションに必要なアクセス許可を割り当てます。 
  3. ユーザーの資格情報を持つアプリケーションを使用してトークンを取得します。
  4. エンドポイント API の Microsoft Defender にアクセスするトークンを使用します。

     詳細については、「ユーザー [コンテキストを使用したアクセスの取得](exposed-apis-create-app-nativeapp.md)」を参照してください。


## <a name="related-topics"></a>関連項目
- [エンドポイント API のマイクロソフト ディフェンダー](exposed-apis-list.md)
- [アプリケーション コンテキストを使用してエンドポイント用の Microsoft Defender にアクセスする](exposed-apis-create-app-webapp.md)
- [ユーザー コンテキストを使用してエンドポイント用の Microsoft Defender にアクセスする](exposed-apis-create-app-nativeapp.md)
