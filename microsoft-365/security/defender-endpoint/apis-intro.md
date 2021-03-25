---
title: エンドポイント API 用 Microsoft Defender にアクセスする
ms.reviewer: ''
description: API を使用してワークフローを自動化し、Microsoft Defender ATP 機能に基づいて革新する方法について説明します。
keywords: apis, api, wdatp, open api, microsoft defender atp api, public api, supported apis, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度なハンティング, クエリ
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
ms.openlocfilehash: 70a8ba9d3ff864ca58c856714b00f0e8feba933a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164764"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>エンドポイント API 用 Microsoft Defender にアクセスする 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**適用対象:** 
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。 これらの API を使用すると、Defender for Endpoint の機能に基づいてワークフローを自動化し、革新することができます。 API アクセスには、OAuth2.0 認証が必要です。 詳細については [、「OAuth 2.0 Authorization Code Flow」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

Defender for Endpoint の API の概要については、このビデオをご覧ください。 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

一般に、API を使用するには、次の手順を実行する必要があります。
- AAD アプリケーションの作成
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用して Defender for Endpoint API にアクセスする


アプリケーション コンテキストまたはユーザー コンテキストを使用して Defender for Endpoint API **にアクセスできます**。

- **アプリケーション コンテキスト: (推奨)** <br>
    サインインしているユーザーが存在せずに実行されるアプリで使用されます。 たとえば、バックグラウンド サービスまたはデーモンとして実行されるアプリ。

    アプリケーション コンテキストを使用して Defender for Endpoint API にアクセスするために必要な手順は次のとおりです。

  1. AAD Web-Application を作成します。
  2. 目的のアクセス許可をアプリケーションに割り当てる (たとえば、「アラートの読み取り」、"コンピューターの分離" など)。 
  3. このアプリケーションのキーを作成します。
  4. キーを使用してアプリケーションを使用してトークンを取得します。
  5. トークンを使用して Microsoft Defender ATP API にアクセスする

     詳細については、「Get [access with application context 」を参照してください](exposed-apis-create-app-webapp.md)。


- **ユーザー コンテキスト:** <br>
    ユーザーに代わって API でアクションを実行するために使用します。

    アプリケーション コンテキストを使用して Defender for Endpoint API にアクセスするための手順は次のとおりです。

  1. AAD ネイティブ アプリケーションを作成します。
  2. 目的のアクセス許可をアプリケーションに割り当てる (「アラートの読み取り」、"コンピューターの分離" など)。 
  3. ユーザー資格情報を使用してアプリケーションを使用してトークンを取得します。
  4. トークンを使用して Microsoft Defender ATP API にアクセスする

     詳細については、「ユーザー コンテキストで [アクセスを取得する」を参照してください](exposed-apis-create-app-nativeapp.md)。


## <a name="related-topics"></a>関連項目
- [エンドポイント API 用 Microsoft Defender](exposed-apis-list.md)
- [アプリケーション コンテキストを使用して Microsoft Defender for Endpoint にアクセスする](exposed-apis-create-app-webapp.md)
- [ユーザー コンテキストを使用して Microsoft Defender for Endpoint にアクセスする](exposed-apis-create-app-nativeapp.md)
