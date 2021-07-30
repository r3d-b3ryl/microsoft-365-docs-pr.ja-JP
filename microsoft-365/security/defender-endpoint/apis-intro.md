---
title: Microsoft Defender for Endpoint API にアクセスする
ms.reviewer: ''
description: API を使用してワークフローを自動化し、Microsoft Defender for Endpoint の機能に基づいて革新する方法について説明します。
keywords: apis, api, wdatp, open api, microsoft defender for endpoint api, microsoft Defender atp, public api, supported apis, alerts, device, user, domain, ip, file, advanced hunting, query
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4042216878767552769dabe9636cee212cca3a23
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53651485"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender for Endpoint API にアクセスする 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。 これらの API を使用すると、Defender for Endpoint の機能に基づいてワークフローを自動化し、革新することができます。 API アクセスには、OAuth2.0 認証が必要です。 詳細については[、「OAuth 2.0 Authorization Code Flow」 を参照してください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

Defender for Endpoint の API の概要については、このビデオをご覧ください。

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

一般に、API を使用するには、次の手順を実行する必要があります。

- [AAD アプリケーションの作成](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用して Defender for Endpoint API にアクセスする

アプリケーション コンテキストまたはユーザー コンテキストを使用して Defender for Endpoint API **にアクセスできます**。

- **アプリケーション コンテキスト: (推奨)**

  サインインしているユーザーが存在せずに実行されるアプリで使用されます。 たとえば、バックグラウンド サービスまたはデーモンとして実行されるアプリ。

  アプリケーション コンテキストを使用して Defender for Endpoint API にアクセスするために必要な手順は次のとおりです。

  1. AAD Web-Application を作成します。
  2. 目的のアクセス許可をアプリケーションに割り当てる (たとえば、「アラートの読み取り」、"コンピューターの分離" など)。 
  3. このアプリケーションのキーを作成します。
  4. キーを使用してアプリケーションを使用してトークンを取得します。
  5. トークンを使用して Microsoft Defender for Endpoint API にアクセスする

     詳細については、「Get [access with application context 」を参照してください](exposed-apis-create-app-webapp.md)。

- **ユーザー コンテキスト:**

  ユーザーに代わって API でアクションを実行するために使用します。

  アプリケーション コンテキストを使用して Defender for Endpoint API にアクセスするための手順は次のとおりです。

  1. AAD ネイティブ アプリケーションを作成します。
  2. 目的のアクセス許可をアプリケーションに割り当てる (「アラートの読み取り」、"コンピューターの分離" など)。 
  3. ユーザー資格情報を使用してアプリケーションを使用してトークンを取得します。
  4. トークンを使用して Microsoft Defender for Endpoint API にアクセスする

     詳細については、「ユーザー コンテキストで [アクセスを取得する」を参照してください](exposed-apis-create-app-nativeapp.md)。

## <a name="related-topics"></a>関連項目

- [エンドポイント API 用 Microsoft Defender](exposed-apis-list.md)
- [アプリケーション コンテキストを使用して Microsoft Defender for Endpoint にアクセスする](exposed-apis-create-app-webapp.md)
- [ユーザー コンテキストを使用して Microsoft Defender for Endpoint にアクセスする](exposed-apis-create-app-nativeapp.md)
