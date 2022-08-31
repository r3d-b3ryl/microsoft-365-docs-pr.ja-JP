---
title: Microsoft 365 Defender API にアクセスする
description: Microsoft 365 Defender API にアクセスする方法について説明します
keywords: access, apis, アプリケーション コンテキスト, ユーザー コンテキスト, aad アプリケーション, アクセス トークン
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.custom: api
ms.openlocfilehash: 0562ff901aa8021973fb1ed36e8caf464f22d672
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481572"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Microsoft 365 Defender API にアクセスする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft 365 Defenderは、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Microsoft 365 Defenderの機能を最大限に活用するのに役立ちます。

一般に、API を使用するには、次の手順を実行する必要があります。

- Azure Active Directory アプリケーションを作成する
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用してMicrosoft 365 Defender API にアクセスする

> [!NOTE]
> API アクセスには、OAuth2.0 認証が必要です。 詳細については、「 [OAuth 2.0 承認コード フロー」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

これらの手順を完了したら、特定のコンテキストを使用してMicrosoft 365 Defender API にアクセスする準備が整いました。

## <a name="application-context-recommended"></a>アプリケーション コンテキスト (推奨)

バックグラウンド サービスやデーモンなど、サインインしているユーザーがいない状態で実行されるアプリには、このコンテキストを使用します。

1. Azure Active Directory Web アプリケーションを作成します。
2. 目的のアクセス許可をアプリケーションに割り当てます。
3. アプリケーションのキーを作成します。
4. アプリケーションとそのキーを使用してセキュリティ トークンを取得します。
5. トークンを使用して、Microsoft 365 Defender API にアクセスします。

詳細については、「**[ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する](api-create-app-web.md)**」を参照してください。

## <a name="user-context"></a>ユーザー コンテキスト

このコンテキストを使用して、1 人のユーザーに代わってアクションを実行します。

1. Azure Active Directory ネイティブ アプリケーションを作成します。
2. 目的のアクセス許可をアプリケーションに割り当てます。
3. アプリケーションのユーザー資格情報を使用してセキュリティ トークンを取得します。
4. トークンを使用して、Microsoft 365 Defender API にアクセスします。

詳細については、「ユーザーの **[代わりにMicrosoft 365 Defender API にアクセスするアプリを作成](api-create-app-user-context.md)** する」を参照してください。

## <a name="partner-context"></a>パートナー コンテキスト

[複数のテナント](/azure/active-directory/develop/single-and-multi-tenant-apps)にまたがる多くのユーザーにアプリを提供する必要がある場合は、このコンテキストを使用します。

1. Azure Active Directory マルチテナント アプリケーションを作成します。
2. 目的のアクセス許可をアプリケーションに割り当てます。
3. 各テナントからアプリの [管理者の同意](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) を取得します。
4. 顧客のテナント ID に基づいて、ユーザー資格情報を使用してセキュリティ トークンを取得します。
5. トークンを使用して、Microsoft 365 Defender API にアクセスします。

詳細については、「**[Microsoft 365 Defender API へのパートナー アクセス権を持つアプリを作成する」を参照してください](api-partner-access.md)**。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [ユーザー サインインと API アクセスに対する OAuth 2.0 承認](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Azure Key Vaultを使用してサーバー アプリのシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Microsoft 365 API にアクセスする "Hello world" アプリケーションを作成する](api-hello-world.md)
