---
title: Microsoft 365 Defender API へのアクセス
description: Microsoft 365 Defender API にアクセスする方法について説明します。
keywords: access, apis, アプリケーション コンテキスト, ユーザー コンテキスト, aad アプリケーション, アクセス トークン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932156"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Microsoft 365 Defender API へのアクセス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender は、一連のプログラム API を通じてデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Microsoft 365 Defender の機能をフルに活用するのに役立ちます。

一般に、API を使用するには、次の手順を実行する必要があります。

- Azure Active Directory アプリケーションを作成する
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用して Microsoft 365 Defender API にアクセスする

> [!NOTE]
> API アクセスには OAuth2.0 認証が必要です。 詳細については [、「OAuth 2.0 認証コード フロー」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

これらの手順を完了すると、特定のコンテキストを使用して Microsoft 365 Defender API にアクセスする準備が整います。

## <a name="application-context-recommended"></a>アプリケーション コンテキスト (推奨)

バックグラウンド サービスやデーモンなど、サインインしているユーザーが存在しないアプリでは、このコンテキストを使用します。

1. Azure Active Directory Web アプリケーションを作成します。
2. 必要なアクセス許可をアプリケーションに割り当てる。
3. アプリケーションのキーを作成します。
4. アプリケーションとそのキーを使用してセキュリティ トークンを取得します。
5. トークンを使用して Microsoft 365 Defender API にアクセスします。

詳しくは、「ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成 **[する」をご覧ください](api-create-app-web.md)**。

## <a name="user-context"></a>ユーザー コンテキスト

このコンテキストを使用して、1 人のユーザーに代わってアクションを実行します。

1. Azure Active Directory ネイティブ アプリケーションを作成します。
2. 必要なアクセス許可をアプリケーションに割り当てる。
3. アプリケーションのユーザー資格情報を使用してセキュリティ トークンを取得します。
4. トークンを使用して Microsoft 365 Defender API にアクセスします。

詳しくは、「ユーザーに代わって **[Microsoft 365 Defender API](api-create-app-user-context.md)** にアクセスするアプリの作成」をご覧ください。

## <a name="partner-context"></a>パートナー コンテキスト

複数のテナントにわたって多くのユーザーにアプリを提供する必要がある場合は、この [コンテキストを使用します](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)。

1. Azure Active Directory マルチテナント アプリケーションを作成します。
2. 必要なアクセス許可をアプリケーションに割り当てる。
3. 各 [テナントからアプリ](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) の管理者の同意を得る。
4. 顧客のテナント ID に基づいて、ユーザー資格情報を使用してセキュリティ トークンを取得します。
5. トークンを使用して Microsoft 365 Defender API にアクセスします。

詳しくは **[、「Microsoft 365 Defender API](api-partner-access.md)** へのパートナー アクセスを使ったアプリの作成」をご覧ください。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [ユーザー サインインと API アクセスの OAuth 2.0 承認](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Azure Key Vault を使用してサーバー アプリのシークレットを管理する](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Microsoft 365 API にアクセスする "Hello world" アプリケーションを作成する](api-hello-world.md)
