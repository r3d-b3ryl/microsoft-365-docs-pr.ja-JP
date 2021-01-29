---
title: 管理者アカウントを保護する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 管理者アカウントを設定して保護する方法について学習します。
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044490"
---
# <a name="protect-your-administrator-accounts"></a>管理者アカウントを保護する

管理者アカウントには昇格された特権が付与されます。このため、管理者アカウントはハッカーやサイバー犯罪の重要なターゲットです。 この記事の内容

- 緊急事態に備え、追加の管理者アカウントを設定する方法。
- これらのアカウントを保護する方法。

Microsoft 365 にサインアップして情報を入力すると、自動的にグローバル管理者になります。グローバル管理者は、Microsoft 管理センターでユーザー アカウントと他のすべての設定を最終的に制御しますが、アクセスの程度が異なるさまざまな種類の管理者アカウントがあります。 管理者 [ロールの種類ごとに](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 異なるアクセス レベルの詳細については、管理者ロールに関するページを参照してください。

## <a name="create-additional-admin-accounts"></a>追加の管理者アカウントを作成する

管理アカウントは管理専用に使用します。 管理者は、Office アプリを定期的に使用するために別のユーザー アカウントを持ち、アカウントやデバイスの管理や他の管理機能の作業に必要な場合にのみ管理アカウントを使用する必要があります。 また、管理者アカウントから Microsoft 365 ライセンスを削除して、料金を支払う必要がなさらないのも良い方法です。

別の信頼できる従業員に管理者アクセス権を付与するために、少なくとも 1 つの追加のグローバル管理者アカウントを設定する必要があります。 ユーザー管理用に個別の管理者アカウントを作成することもできます (この役割はユーザー管理 **管理者と呼ばれています**)。 詳細については、「管理者ロール [」を参照してください](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

追加の管理者アカウントを作成するには:

 1. 管理センターに <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">移動し、</a> 左側のナビゲーションで **[アクティブ** な \> **ユーザー** ] を選択します。

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. [**アクティブなユーザー]** ページで、ページの上部にある [ユーザーの追加]を選択し、[新しいユーザー] パネルで名前と他の情報を入力します。
 3. [ロール **] セクションを展開** し、[グローバル管理者] を **選択して、** このユーザーにグローバル管理者アクセス権を付与します。 カスタマイズされた管理者を **選択し** 、表示される役割を選択することもできます。

    [代替メール アドレス] テキスト ボックス **に代替メールを** 入力します。 ロックアウトされた場合は、このアドレスを使用してパスワード情報を復元できます。グローバル管理者の場合は、請求明細書もこの住所に送信されます。

    ![管理者ロールを選択する](../media/adminroles.png)

 4. [製品ライセンス **]** セクションで **、Microsoft 365 Business** のセレクターを [オフ] に、製品ライセンスのないユーザーの作成を [オン **]** に **移動します**。

    ![製品ライセンスを選択する](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>緊急管理者アカウントを作成する

また、多要素認証 (MFA) でセットアップされていないバックアップ アカウントを作成して、誤って自分自身をロックアウトしないようにする必要があります (たとえば、2 番目の形式の検証として使用している電話を紛失した場合など)。 このアカウントのパスワードが語句または 16 文字以上である必要があります。 これは、多くの場合、"割れ子アカウント" と呼ばれます。

## <a name="create-a-user-account-for-yourself"></a>自分用のユーザー アカウントを作成する

ユーザー アカウントを使用して、メールの確認など、組織との共同作業に参加します。 つまり、管理者の資格情報は  *Alice.Chavez <span></span> @Contoso.org* に似ている可能性があります。また、通常のユーザー アカウントは *Alice <span></span> @Contoso.com* に似ています。

新しいユーザー アカウントを作成するには:

1. 管理センターに <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">移動し、</a> 左側のナビゲーションで **[アクティブ** \> **なユーザー** ] を選択します。
2. [**アクティブなユーザー]** ページで、ページの上部にある [ユーザーの追加]を選択し、[新しいユーザー] パネルで名前と他の情報を入力します。
3. [役割 **] セクションを** 展開し、[ユーザー **](管理アクセス権なし) を選択します**。
4. [製品ライセンス **] セクション** で **、Microsoft 365 Business** のセレクターを [オン] に **移動します**。

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>多要素認証用にこれらの各アカウントを登録する

これらのアカウントが多要素認証 [を使用している必要があります](m365-campaigns-multifactor-authenication.md)。

## <a name="additional-recommendations"></a>その他の推奨事項

- 管理者アカウントも多要素認証用に設定してください。 これを行う方法については、「条件付きアクセス ポリシーを構成 [する」を参照してください](m365-campaigns-conditional-access.md)。
- 管理者アカウントを使用する前に、個人用の電子メール アカウントを含む、関連のないブラウザー セッションとアプリを閉じてください。 プライベート ウィンドウまたはシークレット ブラウザー ウィンドウでも使用できます。
- 管理タスクを完了した後、必ずブラウザー セッションからサインアウトしてください。
