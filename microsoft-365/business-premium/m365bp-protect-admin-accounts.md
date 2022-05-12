---
title: Microsoft 365 Business Premium で管理者アカウントを保護する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Microsoft 365 Business Premium で管理者アカウントを設定して保護する方法について説明します。
ms.openlocfilehash: 1428ee6b447f3f841e7e8e9b77cfd82c2f7a6444
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65320013"
---
# <a name="protect-your-administrator-accounts-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium で管理者アカウントを保護する

管理者アカウントには管理者特権が付与されているため、ハッカーやサイバー犯罪者にとっては重要なターゲットになります。この記事では、次の事項について説明します。

- 緊急時に追加の管理者アカウントを設定する方法。
- これらのアカウントを保護する方法。

Microsoft 365 にサインアップして情報を入力すると、自動的にグローバル管理者 (社内管理者とも呼ばれます) になります。 グローバル管理者は、ユーザー アカウントとその他のすべての設定を Microsoft 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で最終的に制御できますが、アクセス度が異なるさまざまな管理者アカウントが多数存在します。 [管理者ロールの](/office365/admin/add-users/about-admin-roles)種類ごとに異なるアクセス レベルについて詳しくは、管理者ロールに関するページをご覧ください。

## <a name="create-additional-admin-accounts"></a>追加の管理者アカウントを作成する

管理者アカウントは、管理にのみ使用します。 管理者は、Office アプリを定期的に使用するための別のユーザー アカウントを持ち、アカウントとデバイスを管理するために必要な場合にのみ管理アカウントを使用し、他の管理機能で作業する必要があります。 また、管理者アカウントから Microsoft 365 ライセンスを削除して、支払う必要がないようにすることをお勧めします。

管理者が別の信頼できる従業員にアクセスできるように、少なくとも 1 つの追加のグローバル管理者アカウントを設定する必要があります。 ユーザー管理用に別の管理者アカウントを作成することもできます (このロールは **ユーザー管理の管理者** と呼ばれます)。 詳細については、「[管理者の役割について](/office365/admin/add-users/about-admin-roles)」を参照してください。

追加の管理者アカウントを作成するには:

 1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Microsoft 365 管理センター</a>に移動し、左側のナビゲーションで **[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。

    ![左側のナビゲーションで [ユーザー] と [アクティブ なユーザー] の順に選択します。](../media/Activeusers.png)

 1. **[アクティブなユーザー]** ページで、ページの上部にある **[ユーザーの追加]** を選択します。 

 1. **[ユーザーの追加]** パネルで、名前やユーザー名の情報などの基本情報を入力します。

 1. **[製品ライセンス]** 情報を入力して設定します。

 1. **[オプションの設定]** で、管理センターへのアクセスを追加するなど、ユーザーのロールを必要に応じて定義します。

    :::image type="content" source="media/m365bp-global-admin.png" alt-text="新しいユーザー ロールを定義します。":::

 1. 設定を完了してから確認し、詳細を確定するために **[追加の完了]** を選択します。

## <a name="create-an-emergency-admin-account"></a>緊急管理者アカウントを作成する

また、多要素認証 (MFA) で設定されていないバックアップ アカウントを作成して、誤ってロックアウトしないようにする必要があります (たとえば、2 つ目の検証形式として使用しているスマートフォンを紛失した場合)。 このアカウントのパスワードがフレーズであること、または 16 文字以上であることを確認します。 これは多くの場合、"ブレークグラス アカウント" と呼ばれます。

## <a name="create-a-user-account-for-yourself"></a>自分のユーザー アカウントを作成する

ユーザー アカウントを使用して、メールの確認など、組織との共同作業に参加します。 つまり、管理者の資格情報が *Alice.Chavez <span></span>@Contoso.org* のようなものだとすると、通常のユーザー アカウントは *Alice <span></span>@Contoso.com* のようにするということです。

新しいユーザー アカウントを作成するには:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Microsoft 365 管理センター</a>に移動し、左側のナビゲーションで **[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。

1. **[アクティブなユーザー]** ページで、ページの上部にある **[ユーザーの追加]** を選択して、**[ユーザーの追加]** パネルで名前などの情報を入力します。

1. **[製品ライセンス]** セクションで、**[Microsoft 365 Business Premium (管理アクセスなし)]** のチェック ボックスをオンにします。

1. **[オプションの設定]** セクションにある、**[ユーザー (管理センターへのアクセスなし)]** ラジオ ボタンの選択は既定のままにします。

1. 設定を完了してから確認し、詳細を確定するために **[追加の完了]** を選択します。

## <a name="additional-recommendations"></a>追加の推奨事項:

- 管理者アカウントを使用する前に、個人用メール アカウントを含め、無関係なすべてのブラウザー セッションとアプリを閉じます。 プライベート ウィンドウまたはシークレット ブラウザー ウィンドウでも使用できます。

- 管理者タスクを完了したら、必ずブラウザー セッションからサインアウトしてください。

## <a name="next-objective"></a>次の目標

[セキュリティの既定値を有効にする](m365bp-conditional-access.md)手順を実行します。

