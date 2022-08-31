---
title: Microsoft 365 Lighthouseでユーザー サインインをブロックする
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
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合、ユーザーがサインインできないように侵害されたと思われる場合は、ユーザー アカウントをブロックする方法について説明します。
ms.openlocfilehash: 27cfcff4fd3d56a276e1499d8241395f48551003
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477981"
---
# <a name="block-user-sign-in-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseでユーザー サインインをブロックする

侵害されたと思われる場合は、ユーザー アカウントをブロックできます。 ユーザー アカウントをブロックすると、すぐにすべてのユーザーがそのアカウントへのサインインをブロックします。 ユーザーがサインインしようとすると、60 分以内にすべての Microsoft 365 サービスから自動的にサインアウトされます。 ユーザー アカウントをブロックしてもデータは削除されません。また、アカウントがメールの受信を停止することはありません。

## <a name="block-sign-in-for-a-user"></a>ユーザーのサインインをブロックする

1. Lighthouse の左側のナビゲーション ウィンドウで、[**ユーザー****アカウント管理** >**検索ユーザー** > ] を選択します。

2. [ **検索ユーザー** ] タブで、検索ボックスにユーザーの名前を入力します。

3. 検索結果の一覧からユーザーを選択します。

4. ユーザーの詳細ウィンドウで、[ **サインインのブロック**] を選択します。

5. [ **サインインのブロック** ] ウィンドウで、[ **このユーザーのサインインをブロックする**] を選択します。

6. **[変更の保存]** を選択します。

## <a name="block-sign-in-for-risky-users"></a>危険なユーザーのサインインをブロックする

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **ユーザー** > **リスクの高いユーザー**] を選択します。

2. [ **危険なユーザー]** ページで、アクションを実行するユーザーのセットを選択します。

3. [ **サインインのブロック**] を選択します。

4. [ **サインインの管理] 状態ウィンドウで** 、[ **ユーザーのサインインのブロック**] を選択します。

5. **[保存]** を選択します。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 ユーザー アカウントの管理](../enterprise/manage-microsoft-365-accounts.md) (記事)\
[ユーザー パスワードのリセット](m365-lighthouse-reset-user-password.md) (記事)
