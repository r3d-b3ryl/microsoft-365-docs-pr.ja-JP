---
title: Defender API Microsoft 365アクセスする
description: Defender API にアクセスする方法Microsoft 365説明します。
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
# <a name="access-the-microsoft-365-defender-apis"></a>Defender API Microsoft 365アクセスする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft 365Defender は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Defender の機能Microsoft 365活用するのに役立ちます。

一般に、API を使用するには、次の手順を実行する必要があります。

- アプリケーションのAzure Active Directoryする
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用して Defender API Microsoft 365アクセスする

> [!NOTE]
> API アクセスには、OAuth2.0 認証が必要です。 詳細については[、「OAuth 2.0 Authorization Code Flow」 を参照してください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

これらの手順を完了したら、特定のコンテキストを使用して Defender API Microsoft 365アクセスする準備が整いました。

## <a name="application-context-recommended"></a>アプリケーション コンテキスト (推奨)

バックグラウンド サービスやデーモンなど、サインインしているユーザーが存在せずに実行されるアプリには、このコンテキストを使用します。

1. Web アプリケーションAzure Active Directory作成します。
2. 目的のアクセス許可をアプリケーションに割り当てる。
3. アプリケーションのキーを作成します。
4. アプリケーションとそのキーを使用してセキュリティ トークンを取得します。
5. トークンを使用して、Defender API Microsoft 365アクセスします。

詳細については、「ユーザーなしで Defender にアクセスする **[アプリMicrosoft 365作成する」を参照してください](api-create-app-web.md)**。

## <a name="user-context"></a>ユーザー コンテキスト

このコンテキストを使用して、1 人のユーザーに代わってアクションを実行します。

1. ネイティブ アプリケーションAzure Active Directory作成します。
2. 目的のアクセス許可をアプリケーションに割り当てる。
3. アプリケーションのユーザー資格情報を使用してセキュリティ トークンを取得します。
4. トークンを使用して、Defender API Microsoft 365アクセスします。

詳細については、「ユーザーに代わって Defender API にアクセスMicrosoft 365アプリを作成する」**[を参照してください](api-create-app-user-context.md)**。

## <a name="partner-context"></a>パートナー コンテキスト

複数のテナント間で多くのユーザーにアプリを提供する必要がある場合は、この [コンテキストを使用します](/azure/active-directory/develop/single-and-multi-tenant-apps)。

1. 複数テナント アプリケーションAzure Active Directory作成します。
2. 目的のアクセス許可をアプリケーションに割り当てる。
3. 各 [テナントからアプリ](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) の管理者の同意を取得します。
4. 顧客のテナント ID に基づくユーザー資格情報を使用してセキュリティ トークンを取得します。
5. トークンを使用して、Defender API Microsoft 365アクセスします。

詳細については、「パートナー が Defender API にアクセスできるアプリ **[を作成Microsoft 365を参照してください](api-partner-access.md)**。

## <a name="related-articles"></a>関連記事

- [Microsoft 365Defender API の概要](api-overview.md)
- [ユーザー サインインと API アクセスの OAuth 2.0 承認](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Azure Key Vault を使用してサーバー アプリのシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/)
- [アプリケーション API にアクセスする 'Hello world' アプリケーションをMicrosoft 365する](api-hello-world.md)