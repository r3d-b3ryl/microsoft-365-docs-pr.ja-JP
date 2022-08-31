---
title: Microsoft 365 Lighthouseで非アクティブなユーザーを管理する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、非アクティブなユーザーを管理する方法について説明します。
ms.openlocfilehash: 3763ed3ca8ed36ea9d944a2847a7465b73da647d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479601"
---
# <a name="manage-inactive-users-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseで非アクティブなユーザーを管理する

Microsoft 365 Lighthouseは、6 か月以上非アクティブになっているマネージド テナント全体のすべてのユーザーを可視化します。 非アクティブなアカウントでは、セキュリティ 上のリスクが発生し、未使用のライセンスが関連付けられる可能性があります。 **[非アクティブなユーザー**] ページから、非アクティブなアカウントを追跡してクリーンアップできます。

Lighthouse では、サインイン アクティビティを使用して非アクティブなユーザー アカウントを検出します。 **[非アクティブなユーザー]** ページには、テナントごとに最大 500 個の非アクティブなアカウントが表示されます。

## <a name="review-inactive-users"></a>非アクティブなユーザーを確認する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **ユーザー** > **アカウント管理] > [非アクティブなユーザー**] を選択します。

2. [ **非アクティブなユーザー** ] タブで、目的の結果にフィルターを設定します。

3. テナントの一覧から、テナントを展開して、テナント内の非アクティブなユーザーの一覧を表示します。

4. 任意のユーザーを選択してユーザーの詳細ウィンドウを開き、アカウントの詳細を表示します。

5. ユーザー アカウントが不要になったと判断したら、アカウントを削除またはブロックできます。 少なくとも、セキュリティ リスクを軽減するためにユーザー アカウントをブロックする必要があります。 ユーザーの詳細ウィンドウで、[ **サインインのブロック** ] または [ **ユーザーの削除**] を選択します。

## <a name="block-sign-in-for-multiple-user-accounts"></a>複数のユーザー アカウントのサインインをブロックする

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **ユーザー** > **アカウント管理] >** **[非アクティブユーザー**] を選択します。

2. [ **非アクティブなユーザー** ] タブで、一覧内の任意のテナントを展開してテナント内の非アクティブなユーザーの一覧を表示し、ブロックするユーザーを選択して、[ **サインインのブロック**] を選択します。

3. [ **サインインの管理] 状態ウィンドウで** 、[ **ユーザーのサインインのブロック**] を選択します。

4. **[保存]** を選択します。

## <a name="related-content"></a>関連コンテンツ

[Azure AD で非アクティブなユーザー アカウントを管理する方法](/azure/active-directory/reports-monitoring/howto-manage-inactive-user-accounts) (記事)
