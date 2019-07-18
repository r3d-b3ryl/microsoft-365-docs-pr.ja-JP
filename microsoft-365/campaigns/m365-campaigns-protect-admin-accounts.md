---
title: 管理者アカウントを保護する
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 管理者アカウントをセットアップして保護する方法について説明します。
ms.openlocfilehash: 33bf7f8a2a1e666a7822be1d52ac2d81fc681230
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772474"
---
# <a name="protect-your-administrator-accounts"></a>管理者アカウントを保護する

管理者アカウントには昇格された特権があるため、これらはハッカーおよびサイバー犯罪にとって重要な目標となります。 この記事の内容

- 緊急対応のための追加の管理者アカウントをセットアップする方法について説明します。
- これらのアカウントを保護する方法。
 
Microsoft 365 Business にサインアップして、情報を入力すると、自動的にグローバル管理者になります。グローバル管理者は、Microsoft 管理センターのユーザーアカウントとその他のすべての設定を最終的に制御しますが、さまざまなレベルのアクセス権を持つ管理者アカウントの種類が多数あります。 それぞれの種類の管理者の役割の異なるアクセスレベルについては、「[管理者ロールについ](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください。


## <a name="create-additional-admin-accounts"></a>追加の管理者アカウントを作成する

管理用にのみ管理者アカウントを使用します。 管理者は、Office アプリを定期的に使用するための個別のユーザーアカウントを持ち、他の管理者機能の管理に必要な場合にのみ管理者アカウントを使用する必要があります。 また、管理者アカウントから Microsoft 365 Business license を削除して、料金を支払う必要がないようにすることをお勧めします。

他の信頼された従業員に対する管理者アクセス権を与えるには、少なくとも1つのグローバル管理者アカウントを設定する必要があります。 また、ユーザー管理用に別の管理者アカウントを作成することもできます (この役割は、**ユーザー管理の管理者**と呼ばれます)。 詳細については、「[管理者ロールについ](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください。

追加の管理者アカウントを作成するには:

 1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理センター</a>に移動し、左側のナビゲーションで [**ユーザー** \>の**アクティブなユーザー** ] を選択します。

    ![左側のナビゲーションで、[ユーザー]、[アクティブユーザー] の順に選択します。](media/Activeusers.png)

2. [**アクティブなユーザー** ] ページで、ページの上部にある [**ユーザーの追加**] を選択し、[**新しいユーザー** ] パネルで名前とその他の情報を入力します。
3. [**役割**] セクションを展開し、[**グローバル管理者**] を選択して、このユーザーにグローバル管理者アクセス権を付与します。 [カスタマイズされた**管理者**] を選択して、表示される役割のいずれかを選択することもできます。

    [代替メールアドレス] テキストボックスに別の電子メールを入力します。 ロックアウトされている場合は、このアドレスを使用してパスワード情報を回復できます。グローバル管理者の場合、billing ステートメントはこのアドレスにも送信されます。

    ![管理者の役割を選択する](media/adminroles.png)
    
4. [**製品ライセンス**] セクションで、 **Microsoft 365 Business**のセレクターを**オフ**にし、[**製品ライセンスなしでユーザーを作成**する] を **[オン**] に移動します。

    ![製品ライセンスを選択する](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>緊急管理者アカウントを作成する

また、多要素認証 (MFA) で設定されていないバックアップアカウントを作成して、誤ってロックしないようにする必要があります (たとえば、検証から第2秒として使用している電話が失われた場合など)。 このアカウントのパスワードが、語句または16文字以上の長さであることを確認してください。 これは、"ブレイクガラスアカウント" と呼ばれることがよくあります。

## <a name="create-a-user-account-for-yourself"></a>自分のユーザーアカウントを作成する

ユーザーアカウントを使用して、メールのチェックを含む、組織とのグループ作業に参加します。 これは、管理者の資格情報が*alice の @Contoso<span></span>Chavez*に似ている可能性があることを意味し、通常のユーザーアカウントは*<span></span>alice @Contoso*に似ている場合があります。

新しいユーザーアカウントを作成するには、次のようにします。
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">管理センター</a>に移動し、左側のナビゲーションで [**ユーザー** \>の**アクティブなユーザー** ] を選択します。
2. [**アクティブなユーザー** ] ページで、ページの上部にある [**ユーザーの追加**] を選択し、[**新しいユーザー** ] パネルで名前とその他の情報を入力します。
3. [**役割**] セクションを展開し、[**ユーザー (管理者権限なし)**] を選択します。
1. [**製品ライセンス**] セクションで、 **Microsoft 365 Business**のセレクターを **[オン**] に移動します。 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>多要素認証のためにこれらの各アカウントを登録する


## <a name="additional-recommendations"></a>その他の推奨事項

- 管理者アカウントが多要素認証にも設定されていることを確認してください。 これを行う方法については、「[条件付きアクセスポリシーを構成](m365-campaigns-conditional-access.md)する」で説明します。
- 管理者アカウントを使用する前に、個人の電子メールアカウントを含む、関連のないブラウザーセッションとアプリをすべて閉じてください。 プライベートまたは incognito ブラウザウィンドウでも使用できます。
- 管理タスクを完了した後、ブラウザーセッションからサインアウトしてください。