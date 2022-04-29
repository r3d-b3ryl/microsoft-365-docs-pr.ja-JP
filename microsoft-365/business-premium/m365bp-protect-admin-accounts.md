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
ms.openlocfilehash: b054267264b8440929559ad1a2e335449f3c0309
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091525"
---
# <a name="protect-your-administrator-accounts-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium で管理者アカウントを保護する

管理者アカウントには管理者特権が付与されているため、ハッカーやサイバー犯罪者にとって重要なターゲットです。 この記事の内容

- 緊急時に追加の管理者アカウントを設定する方法。
- これらのアカウントを保護する方法。

Microsoft 365 にサインアップして情報を入力すると、自動的にグローバル管理者 (社内管理者とも呼ばれます) になります。 グローバル管理者は、ユーザー アカウントとその他のすべての設定を Microsoft 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) で最終的に制御できますが、アクセス度が異なるさまざまな管理者アカウントが多数存在します。 [管理者ロールの](/office365/admin/add-users/about-admin-roles)種類ごとに異なるアクセス レベルについて詳しくは、管理者ロールに関するページをご覧ください。

## <a name="create-additional-admin-accounts"></a>追加の管理者アカウントを作成する

管理者アカウントは、管理にのみ使用します。 管理者は、Office アプリを定期的に使用するための別のユーザー アカウントを持ち、アカウントとデバイスを管理するために必要な場合にのみ管理アカウントを使用し、他の管理機能で作業する必要があります。 また、管理者アカウントから Microsoft 365 ライセンスを削除して、支払う必要がないようにすることをお勧めします。

管理者が別の信頼できる従業員にアクセスできるように、少なくとも 1 つの追加のグローバル管理者アカウントを設定する必要があります。 ユーザー管理用に別の管理者アカウントを作成することもできます (このロールは **ユーザー管理の管理者** と呼ばれます)。 詳細については、「[管理者の役割について](/office365/admin/add-users/about-admin-roles)」を参照してください。

追加の管理者アカウントを作成するには:

 1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Microsoft 365 管理センター</a>に移動し、左側のナビゲーションで **[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。

    ![左側のナビゲーションで [ユーザー] と [アクティブ なユーザー] の順に選択します。](../media/Activeusers.png)

 2. **[アクティブなユーザー]** ページで、ページの上部にある **[ユーザーの追加]** を選択し、**[新しいユーザー]** パネルで名前とその他の情報を入力します。

 3. **[ロール]** セクションを展開し、**[グローバル管理者]** を選択して、このユーザーにグローバル管理者アクセス権を付与します。 **[カスタマイズ済みの管理者]** を選択し、表示されるロールのいずれかを選択することもできます。

    [**代替メール アドレス**] テキスト ボックスに代替メールを入力します。 このアドレスを使用すると、ロックアウトされた場合にパスワード情報を回復できます。グローバル管理者の場合は、課金明細書もこのアドレスに送信されます。

    ![管理者の役割を選択します。](../media/adminroles.png)

 4. **[製品ライセンス]** セクションで、**Microsoft 365 Business** のセレクターを **[オフ]** に、**製品ライセンスのないユーザーを作成するセレクター** を **[オン]** に移動します。

    ![製品ライセンスを選択します。](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>緊急管理者アカウントを作成する

また、多要素認証 (MFA) で設定されていないバックアップ アカウントを作成して、誤ってロックアウトしないようにする必要があります (たとえば、2 つ目の検証形式として使用しているスマートフォンを紛失した場合)。 このアカウントのパスワードがフレーズであること、または 16 文字以上であることを確認します。 これは多くの場合、"ブレークグラス アカウント" と呼ばれます。

## <a name="create-a-user-account-for-yourself"></a>自分のユーザー アカウントを作成する

ユーザー アカウントを使用して、メールの確認など、組織との共同作業に参加します。 これは、管理者の資格情報が  *Alice.Chavez <span></span>@Contoso.org* に似ている可能性があり、通常のユーザー アカウントが *Alice <span></span>@Contoso.com* に似ている可能性があることを意味します。

新しいユーザー アカウントを作成するには:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Microsoft 365 管理センター</a>に移動し、左側のナビゲーションで **[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。

2. **[アクティブなユーザー]** ページで、ページの上部にある **[ユーザーの追加]** を選択し、**[新しいユーザー]** パネルで名前とその他の情報を入力します。

3. **[ロール]** セクションを展開し、**ユーザー (管理アクセスなし)** を選択します。

4. **[製品ライセンス]** セクションで、**Microsoft 365 Business** のセレクターを **[オン]** に移動します。

## <a name="additional-recommendations"></a>追加の推奨事項:

- 管理者アカウントを使用する前に、個人用メール アカウントを含め、無関係なすべてのブラウザー セッションとアプリを閉じます。 プライベート ウィンドウまたはシークレット ブラウザー ウィンドウでも使用できます。

- 管理者タスクを完了したら、必ずブラウザー セッションからサインアウトしてください。

## <a name="next-objective"></a>次の目標

[セキュリティの既定値を有効にする](m365bp-conditional-access.md)手順を実行します。

