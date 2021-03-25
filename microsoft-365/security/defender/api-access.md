---
title: Microsoft 365 Defender API へのアクセス
description: Microsoft 365 Defender API にアクセスする方法について説明します。
keywords: access、apis、アプリケーション コンテキスト、ユーザー コンテキスト、aad アプリケーション、アクセス トークン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064723"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Microsoft 365 Defender API へのアクセス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft 365 Defender は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Microsoft 365 Defender の機能をフルに活用するのに役立ちます。

一般に、API を使用するには、次の手順を実行する必要があります。

- Azure Active Directory アプリケーションの作成
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用して Microsoft 365 Defender API にアクセスする

> [!NOTE]
> API アクセスには、OAuth2.0 認証が必要です。 詳細については [、「OAuth 2.0 Authorization Code Flow」を参照してください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

これらの手順を完了したら、特定のコンテキストを使用して Microsoft 365 Defender API にアクセスする準備ができました。

## <a name="application-context-recommended"></a>アプリケーション コンテキスト (推奨)

バックグラウンド サービスやデーモンなど、サインインしているユーザーが存在せずに実行されるアプリには、このコンテキストを使用します。

1. Azure Active Directory Web アプリケーションを作成します。
2. 目的のアクセス許可をアプリケーションに割り当てる。
3. アプリケーションのキーを作成します。
4. アプリケーションとそのキーを使用してセキュリティ トークンを取得します。
5. トークンを使用して Microsoft 365 Defender API にアクセスします。

詳細については、「ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成 **[する」を参照してください](api-create-app-web.md)**。

## <a name="user-context"></a>ユーザー コンテキスト

このコンテキストを使用して、1 人のユーザーに代わってアクションを実行します。

1. Azure Active Directory ネイティブ アプリケーションを作成します。
2. 目的のアクセス許可をアプリケーションに割り当てる。
3. アプリケーションのユーザー資格情報を使用してセキュリティ トークンを取得します。
4. トークンを使用して Microsoft 365 Defender API にアクセスします。

詳細については、「ユーザーに代わって **[Microsoft 365 Defender API](api-create-app-user-context.md)** にアクセスするアプリを作成する」を参照してください。

## <a name="partner-context"></a>パートナー コンテキスト

複数のテナント間で多くのユーザーにアプリを提供する必要がある場合は、この [コンテキストを使用します](/azure/active-directory/develop/single-and-multi-tenant-apps)。

1. Azure Active Directory マルチテナント アプリケーションを作成します。
2. 目的のアクセス許可をアプリケーションに割り当てる。
3. 各 [テナントからアプリ](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) の管理者の同意を取得します。
4. 顧客のテナント ID に基づくユーザー資格情報を使用してセキュリティ トークンを取得します。
5. トークンを使用して Microsoft 365 Defender API にアクセスします。

詳細については **[、「Microsoft 365 Defender API](api-partner-access.md)** へのパートナー アクセスを使用してアプリを作成する」を参照してください。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [ユーザー サインインと API アクセスの OAuth 2.0 承認](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Azure Key Vault を使用してサーバー アプリのシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Microsoft 365 API にアクセスする 'Hello world' アプリケーションを作成する](api-hello-world.md)