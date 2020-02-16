---
title: コネクタをアーカイブ Twitter データに展開する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Twitter データをインポートおよびアーカイブするためのネイティブコネクタを Microsoft 365 にセットアップできます。 このデータを Microsoft 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Twitter データのガバナンスを管理できます。
ms.openlocfilehash: 80c3ca71204b6050a1944250c20df4ff13bbd71e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075705"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>コネクタをアーカイブ Twitter データに展開する

この記事では、Office 365 インポートサービスを使用して組織の Twitter アカウントから Microsoft 365 にデータをインポートするコネクタを展開するための段階的なプロセスについて説明します。 このプロセスの概要と、Twitter コネクタを展開するために必要な前提条件の一覧については、「 [Set up a connector to Archive Twitter data ](archive-twitter-data-with-sample-connector.md)」を参照してください。 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

1. に<https://portal.azure.com>移動し、Office 365 グローバル管理者アカウントの資格情報を使用してサインインします。

   ![Azure にサインインする](../media/TCimage01.png)

2. 左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。

   ![Azure Active Directory に移動します。](../media/TCimage02.png)

3. 左側のナビゲーションウィンドウで、[**アプリの登録 (プレビュー)** ] をクリックし、[**新しい登録**] をクリックします。

   ![新しいアプリの登録を作成する](../media/TCimage03.png)

4. アプリケーションを登録します。 [**リダイレクト URI (オプション)**] で**** 、[アプリケーションの種類] ドロップダウンリストから`https://portal.azure.com` [WEB] を選択し、URI のボックスに入力します。

   ![リダイレクトhttps://portal.azure.com URI の種類 ](../media/TCimage04.png)

5. **アプリケーション (クライアント) id**と**ディレクトリ (テナント) id**をコピーし、それをテキストファイルまたは他の安全な場所に保存します。 これらの Id は、後の手順で使用します。

    ![アプリケーション Id とディレクトリ Id をコピーして保存する](../media/TCimage05.png)

6. [**証明書 & 新しいアプリのシークレット**] および [**クライアントシークレット**] の下で、[**新しいクライアントシークレット**] をクリックします。

   ![新しいクライアントシークレットを作成する](../media/TCimage06.png)

7. 新しいシークレットを作成します。 [説明] ボックスに、シークレットを入力し、有効期限を選択します。 

   ![シークレットを入力して、[有効期限の期間] を選択する](../media/TCimage08.png)

8. シークレットの値をコピーして、テキストファイルまたは他の保存場所に保存します。 これは、後の手順で使用する AAD アプリケーションシークレットです。

   ![シークレットをコピーして保存する](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>手順 2: GitHub から Azure アカウントにコネクタ web サービスを展開する

1. [この GitHub サイト](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)に移動し、[ **Azure への展開] を**クリックします。

    ![Azure ホームページに移動する](../media/FBCimage11.png)

2. [ **Azure への展開**] をクリックすると、カスタムテンプレートページを使用して azure portal にリダイレクトされます。 [**基本**と**設定**] の詳細を入力し、[**購入**] をクリックします。

   ![[リソースを作成し、ストレージアカウントを入力してください] をクリックします。](../media/FBCimage12.png)

    - **サブスクリプション:** Twitter connector web サービスを展開する Azure サブスクリプションを選択します。
    
    - **リソースグループ:** 新しいリソースグループを選択または作成します。 リソースグループは、Azure ソリューションの関連リソースを保持するコンテナーです。

    - **場所:** 場所を選択します。

    - **Web アプリ名:** コネクタ web アプリの一意の名前を指定します。 名前の長さは 3 ~ 18 文字でなければなりません。 この名前は、Azure app service の URL を作成するために使用されます。たとえば、 **twitterconnector**の Web アプリ名を指定すると、Azure app SERVICE の URL は**twitterconnector.azurewebsites.net**になります。
    
    - **tenantId:** 手順1で Azure Active Directory に Facebook connector アプリを作成した後にコピーした、Microsoft 365 組織のテナント ID。
    
   - **APISecretKey:** 任意の値をシークレットとして入力できます。 これは、手順5でコネクタ web アプリにアクセスするために使用されます。

3. 展開に成功すると、ページは次のスクリーンショットのようになります。

    ![[記憶域] をクリックし、[ストレージアカウント] をクリックします。](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>手順 3: Twitter アプリを作成する

1. にhttps://developer.twitter.com移動して、組織の開発者アカウントの資格情報を使用してログインし、[**アプリ**] をクリックします。

   ![にhttps://developer.twitter.com移動し、ログインします。](../media/TCimage25-5.png)
2. [**アプリの作成**] をクリックします。
   
   ![アプリページに移動してアプリを作成する](../media/TCimage26.png)

3. [**アプリの詳細**] で、アプリケーションに関する情報を追加します。

   ![アプリに関する情報を入力する](../media/TCimage27.png)

4. Twitter 開発者ダッシュボードで、作成したばかりのアプリを選択し、表示されたアプリ ID をコピーして、テキストファイルまたはその他の保存場所に保存します。 [**詳細**] をクリックします。
   
   ![アプリ Id をコピーして保存する](../media/TCimage28.png)

5. [**キーとトークン**] タブの [**コンシューマー api キー** ] で、api シークレットキーをコピーして、テキストファイルまたは他の保存場所に保存します。 次に、[**作成**] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。
   
   ![API シークレットキーにコピーして保存する](../media/TCimage29.png)

   次に、[**作成**] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。

6. [**アクセス許可**] タブをクリックし、次のスクリーンショットに示されているようにアクセス許可を構成します。

   ![アクセス許可を構成する](../media/TCimage30.png)

7. アクセス許可の設定を保存した後、[**アプリの詳細**] タブをクリックし、[編集] をクリックして [**詳細の編集 >** します。

   ![アプリの詳細を編集する](../media/TCimage31.png)

8. 次のタスクを実行します。

   - チェックボックスをオンにして、コネクタアプリが Twitter にサインインできるようにします。
   
   - 次の形式を使用して OAuth リダイレクト Uri を追加します: ** \<コネクタ>/views/twitteroauth**。この場合、*コネクタサービス uri*の値は組織の Azure app service URL になります。たとえば、 https://twitterconnector.azurewebsites.net/Views/TwitterOAuthのようになります。

    ![コネクタアプリが Twitter にサインインして OAuth リダイレクト Uri を追加できるようにする](../media/TCimage32.png)

Twitter 開発者アプリを使用する準備ができました。

## <a name="step-4-configure-the-connector-web-app"></a>手順 4: コネクタ web アプリを構成する 

1. Https://\<AzureAppResourceName> に移動します (ここで、 **AzureAppResourceName**は、手順4で名前を付けた Azure app リソースの名前です)。 たとえば、名前が**twitterconnector**の場合は、にhttps://twitterconnector.azurewebsites.net移動します。 アプリのホームページは、次のスクリーンショットのようになります。

   ![Azure app リソースページに移動します。](../media/FBCimage41.png)

2. [**構成**] をクリックして、サインインページを表示します。

   ![[構成] をクリックしてサインインページを表示する](../media/FBCimage42.png)

3. [テナント Id] ボックスに、テナント Id を入力するか貼り付けます (手順2で取得したもの)。 [パスワード] ボックスに、APISecretKey (手順2で取得した) を入力するか貼り付け、[**構成設定の設定**] をクリックして構成の詳細ページを表示します。

   ![テナント Id と API シークレットキーを使用してサインインする](../media/TCimage35.png)

4. 次の構成設定を入力します。 

   - **Twitter Api キー:** 手順3で作成した Twitter アプリケーションのアプリ ID。
   
   - **Twitter Api の秘密キー:** 手順3で作成した Twitter アプリケーションの API シークレットキー。
   
   - **Twitter アクセストークン:** 手順3で作成したアクセストークン。
   
   - **Twitter アクセストークンシークレット:** 手順3で作成したアクセストークンシークレット。
   
   - **AAD アプリケーション ID:** 手順1で作成した Azure Active Directory アプリのアプリケーション ID
   
   - **AAD アプリケーションシークレット:** 手順1で作成した APISecretKey シークレットの値。

5. [**保存**] をクリックしてコネクタの設定を保存します。

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>手順 5: Microsoft 365 コンプライアンスセンターで Twitter connector をセットアップする

1. に[https://compliance.microsoft.com](https://compliance.microsoft.com)移動し、左側のナビゲーションで [**データコネクタ**] をクリックします。

2. [**データコネクタ] (プレビュー)** ページの [ **Twitter**] で、[**表示**] をクリックします。

3. **Twitter**ページで、[**コネクタの追加**] をクリックします。

4. [**サービス利用規約**] ページで、[**同意**する] をクリックします。

5. [**コネクタアプリの資格情報の追加**] ページで、次の情報を入力し、[**接続の検証**] をクリックします。

   ![Connector アプリの資格情報を入力する](../media/TCimage38.png)

    - [**名前**] ボックスに、 **Twitter ヘルプハンドル**などのコネクタの名前を入力します。
    
    - [**コネクタの url** ] ボックスに、Azure app SERVICE の url を入力するか貼り付けます。例`https://twitterconnector.azurewebsites.net`を示します。
    
    - [**パスワード**] ボックスに、手順2で作成した APISecretKey の値を入力するか貼り付けます。
    
    - [ **Azure APP id** ] ボックスに、手順1で取得した Azure アプリケーションアプリ id (*クライアント ID*とも呼ばれる) の値を入力するか貼り付けます。

6. 接続が正常に検証されたら、[**次へ**] をクリックします。

7. [ **Microsoft 365 にデータをインポートするための承認**] ページで、APISecretKey をもう一度入力するか貼り付けて、[ **Login web app**] をクリックします。

8. [ **Twitter でログイン] を**クリックします。

9. [Twitter サインイン] ページで、組織の Twitter アカウントの資格情報を使用してサインインします。

   ![Twitter アカウントにサインインする](../media/TCimage42.png)

   サインインした後、Twitter ページに次のメッセージが表示されます。 "Twitter Connector ジョブは正常にセットアップされました。"

10. [**続行**] をクリックして、Twitter connector の設定を完了します。

11. [**フィルターの設定**] ページでは、特定の年齢のアイテムを最初にインポートするためのフィルターを適用できます。 年齢を選択し、[**次へ**] をクリックします。

12. [**ストレージの場所の選択**] ページで、Twitter アイテムがインポートされる Microsoft 365 メールボックスの電子メールアドレスを入力し、[**次へ**] をクリックします。

13. [**管理者に同意**する] で、[**同意を提供**する] をクリックし、手順に従います。 組織内のデータにアクセスするために Office 365 Import service への同意を提供するには、グローバル管理者である必要があります。

14. [**次**へ] をクリックしてコネクタの設定を確認し、[**完了**] をクリックしてコネクタのセットアップを完了します。

15. コンプライアンスセンターで**データコネクタ**ページに移動し、[**コネクタ**] タブをクリックしてインポートプロセスの進行状況を表示します。
