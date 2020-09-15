---
title: Microsoft の脅威保護 Api にアクセスする
description: Microsoft の脅威保護 Api にアクセスする方法について説明します。
keywords: access、api、アプリケーションコンテキスト、ユーザーコンテキスト、aad アプリケーション、アクセストークン
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 653c359c324852719688a374a6e863df0a1909ba
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650428"
---
# <a name="access-the-microsoft-threat-protection-apis"></a>Microsoft の脅威保護 Api にアクセスする

**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


 Microsoft の脅威保護は、プログラム Api のセットを使用して、そのデータおよびアクションの多くを公開します。 これらの Api を使用すると、Microsoft の脅威保護機能に基づいてワークフローとイノベーションを自動化できます。 API へのアクセスには、OAuth 2.0 認証が必要です。 詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。


一般に、Api を使用するには、次の手順を実行する必要があります。
- AAD アプリケーションを作成する
- このアプリケーションを使用してアクセストークンを取得する
- トークンを使用して Microsoft の脅威保護 API にアクセスする


**アプリケーションコンテキスト**または**ユーザーコンテキスト**を使用して、MICROSOFT の脅威保護 API にアクセスできます。

- **アプリケーションコンテキスト: (推奨)** <br>
    サインインしているユーザーなしで実行するアプリによって使用されます。 たとえば、バックグラウンドサービスまたはデーモンとして実行されるアプリです。

    アプリケーションコンテキストを使用して Microsoft の脅威保護 API にアクセスするために実行する必要がある手順は次のとおりです。

  1. AAD Web アプリケーションを作成します。
  2. 必要なアクセス許可をアプリケーションに割り当てます。たとえば、 **インシデント.** **AdvancedHunting**, read. 
  3. このアプリケーションのキーを作成します。
  4. アプリケーションとそのキーを使用してトークンを取得します。
  5. トークンを使用して Microsoft の脅威保護 API にアクセスする

     詳細については、「 [Get access with application context](api-create-app-web.md)」を参照してください。


- **ユーザーコンテキスト:** <br>
    ユーザーに代わって API でアクションを実行するために使用されます。

    アプリケーションコンテキストを使用して Microsoft の脅威保護 API にアクセスするために実行する必要がある手順は次のとおりです。
  1. AAD ネイティブアプリケーションを作成します。
  2. アプリケーションに必要なアクセス許可を割り当てます。 たとえば、「 **AdvancedHunting** **」と読みます**。
  3. ユーザー資格情報を使用してアプリケーションを使用してトークンを取得します。
  4. トークンを使用して Microsoft の脅威保護 API にアクセスする

     詳細については、「 [Get access with user context](api-create-app-user-context.md)」を参照してください。


## <a name="related-topics"></a>関連項目
- [Microsoft の脅威保護 Api](api-supported.md)
- [アプリケーションコンテキストを使用して Microsoft の脅威保護にアクセスする](api-create-app-web.md)
- [ユーザーコンテキストを使用して Microsoft の脅威保護にアクセスする](api-create-app-user-context.md)
