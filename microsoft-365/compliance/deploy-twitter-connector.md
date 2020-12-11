---
title: コネクタを展開して Twitter データをアーカイブする
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Microsoft 365 に Twitter データをインポートしてアーカイブするネイティブ コネクタを設定できます。 このデータを Microsoft 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Twitter データのガバナンスを管理できます。
ms.openlocfilehash: 0dd996802964b2a2fc58d26e23af57193c89ee8c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619913"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>コネクタを展開して Twitter データをアーカイブする

この記事では、Office 365 インポート サービスを使用して組織の Twitter アカウントから Microsoft 365 にデータをインポートするコネクタを展開する手順について説明します。 このプロセスの概要と、Twitter コネクタを展開するために必要な前提条件の一覧については、「コネクタをセットアップして Twitter データをアーカイブする」を参照 [してください ](archive-twitter-data-with-sample-connector.md)。 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

1. グローバル管理者 <https://portal.azure.com> アカウントの資格情報を使用して、アクセスしてサインインします。

   ![Azure にサインインする](../media/TCimage01.png)

2. 左側のナビゲーション ウィンドウで **、Azure Active Directory をクリックします**。

   ![Azure Active Directory に移動する](../media/TCimage02.png)

3. 左側のナビゲーション ウィンドウで、アプリの登録 **(プレビュー)** をクリックし、[新しい登録] **をクリックします**。

   ![新しいアプリ登録を作成する](../media/TCimage03.png)

4. アプリケーションを登録します。 [ **リダイレクト URI] (オプション)** で、アプリケーションの種類のドロップダウン リストで **[Web]** を選択し、URI のボックス `https://portal.azure.com` に入力します。

   ![リダイレクト https://portal.azure.com URI の種類 ](../media/TCimage04.png)

5. アプリケーション **(クライアント) ID と****ディレクトリ (テナント) ID** をコピーし、テキスト ファイルなどの安全な場所に保存します。 これらの ID は、後の手順で使用します。

    ![アプリケーション ID とディレクトリ ID をコピーして保存する](../media/TCimage05.png)

6. 新しいアプリ **の証明書&シークレット** に移動し、[クライアント シークレット]で [新しいクライアント シークレット **] をクリックします**。

   ![新しいクライアント シークレットを作成する](../media/TCimage06.png)

7. 新しいシークレットを作成します。 説明ボックスにシークレットを入力し、有効期限を選択します。 

   ![シークレットを入力して有効期限を選択する](../media/TCimage08.png)

8. シークレットの値をコピーし、テキスト ファイルまたは他の保存場所に保存します。 これは、後の手順で使用する AAD アプリケーション シークレットです。

   ![シークレットをコピーして保存する](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>手順 2: GitHub から Azure アカウントにコネクタ Web サービスを展開する

1. この [GitHub サイトに移動し、[Azure](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) に展開 **] をクリックします**。

    ![Azure ホーム ページに移動する](../media/FBCimage11.png)

2. [Azure に **展開] を** クリックすると、カスタム テンプレート ページを使用して Azure Portal にリダイレクトされます。 [基本と **設定] の詳細** を **入力し、[** 購入] をクリック **します**。

   ![[リソースの作成] をクリックし、ストレージ アカウントを入力します。](../media/FBCimage12.png)

    - **サブスクリプション:** Twitter コネクタ Web サービスを展開する Azure サブスクリプションを選択します。
    
    - **リソース グループ:** 新しいリソース グループを選択または作成します。 リソース グループは、Azure ソリューションの関連リソースを保持するコンテナーです。

    - **場所:** 場所を選択します。

    - **Web アプリ名:** コネクタ Web アプリの一意の名前を指定します。 名前の長さは 3 ~ 18 文字です。 この名前は、Azure アプリ サービスの URL を作成するために使用されます。たとえば **、twitterconnector** の Web アプリ名を指定すると、Azure アプリ サービスの URL が **twitterconnector.azurewebsites.net。**
    
    - **tenantId:** 手順 1 で Azure Active Directory で Facebook コネクタ アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。
    
   - **APISecretKey:** 任意の値をシークレットとして入力できます。 これは、手順 5 でコネクタ Web アプリにアクセスするために使用されます。

3. 展開が成功すると、ページは次のスクリーンショットのようになります。

    ![[ストレージ] をクリックし、[ストレージ アカウント] をクリックします。](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>手順 3: Twitter アプリを作成する

1. に移動 https://developer.twitter.com し、組織の開発者アカウントの資格情報を使用してログインし、[アプリ] をクリック **します**。

   ![移動して https://developer.twitter.com ログインする](../media/TCimage25-5.png)
2. [アプリ **の作成] をクリックします**。
   
   ![[アプリ] ページに移動してアプリを作成する](../media/TCimage26.png)

3. [ **アプリの詳細] で**、アプリケーションに関する情報を追加します。

   ![アプリに関する情報を入力する](../media/TCimage27.png)

4. Twitter 開発者ダッシュボードで、作成したアプリを選択し、[詳細] をクリック **します**。
   
   ![アプリ ID をコピーして保存する](../media/TCimage28.png)

5. [キー **と** トークン] タブの **コンシューマー API** キーの下で、API キーと API 秘密キーの両方をコピーし、テキスト ファイルまたは他の保存場所に保存します。 次に **、[作成]** をクリックしてアクセス トークンとアクセス トークン シークレットを生成し、テキスト ファイルまたは他の保存場所にコピーします。
   
   ![API 秘密キーをコピーして保存する](../media/TCimage29.png)

   次に **、[作成]** をクリックしてアクセス トークンとアクセス トークン シークレットを生成し、これらをテキスト ファイルまたは他の保存場所にコピーします。

6. 次の **スクリーンショットに示** すように、[アクセス許可] タブをクリックし、アクセス許可を構成します。

   ![アクセス許可を構成する](../media/TCimage30.png)

7. アクセス許可の設定を保存したら、[アプリの詳細] タブをクリックし、[詳細の編集] >**クリックします**。

   ![アプリの詳細を編集する](../media/TCimage31.png)

8. 次のタスクを実行します。

   - コネクタ アプリが Twitter にサインインするには、チェック ボックスをオンにします。
   
   - 次の形式を使用して OAuth リダイレクト URI を追加します: **\<connectorserviceuri> /Views/TwitterOAuth**。*ここで、connectorserviceuri* の値は組織の Azure アプリ サービス URL です。たとえば https://twitterconnector.azurewebsites.net/Views/TwitterOAuth 、 .

    ![コネクタ アプリが Twitter にサインインして OAuth リダイレクト URI を追加する](../media/TCimage32.png)

Twitter 開発者アプリを使用する準備ができました。

## <a name="step-4-configure-the-connector-web-app"></a>手順 4: コネクタ Web アプリを構成する 

1. https:// \<AzureAppResourceName> .azurewebsites.net に移動します **(AzureAppResourceName** は手順 4 で指定した Azure アプリ リソースの名前です)。 たとえば、名前が **twitterconnector の場合は**、次のリンク先に移動します https://twitterconnector.azurewebsites.net 。 アプリのホーム ページは、次のスクリーンショットのようになります。

   ![[Azure アプリ リソース] ページに移動する](../media/FBCimage41.png)

2. [ **構成] を** クリックしてサインイン ページを表示します。

   ![[構成] をクリックしてサインイン ページを表示する](../media/FBCimage42.png)

3. [テナント ID] ボックスに、テナント ID (手順 2 で取得した ID) を入力するか貼り付けます。 パスワード ボックスに、APISecretKey (手順 2 で取得したキー) を入力するか貼り付け、[構成設定の設定] をクリックして構成の詳細ページを表示します。

   ![テナント ID と API 秘密キーを使用してサインインする](../media/TCimage35.png)

4. 次の構成設定を入力します。 

   - **Twitter Api キー:** 手順 3 で作成した Twitter アプリケーションの API キー。
   
   - **Twitter Api の秘密キー:** 手順 3 で作成した Twitter アプリケーションの API 秘密鍵。
   
   - **Twitter アクセス トークン:** 手順 3 で作成したアクセス トークン。
   
   - **Twitter アクセス トークン シークレット:** 手順 3 で作成したアクセス トークン シークレット。
   
   - **AAD アプリケーション ID:** 手順 1 で作成した Azure Active Directory アプリのアプリケーション ID
   
   - **AAD アプリケーション シークレット:** 手順 1 で作成した APISecretKey シークレットの値。

5. [ **保存] を** クリックしてコネクタの設定を保存します。

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>手順 5: Microsoft 365 コンプライアンス センターで Twitter コネクタをセットアップする

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの [ **データ コネクタ]** に移動してクリックします。

2. Twitter の **[データ コネクタ] ページ** で、[ **表示**] を **クリックします**。

3. Twitter ページ **で、[コネクタの** 追加] **をクリックします**。

4. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

5. [コネクタ **アプリの資格情報の追加** ] ページで、次の情報を入力し、[接続の検証] **をクリックします**。

   ![コネクタ アプリの資格情報を入力する](../media/TCimage38.png)

    - [名前 **] ボックス** に、コネクタの名前 (Twitter のヘルプ ハンドルなど) **を入力します**。
    
    - [コネクタ **の URL] ボックス** に、Azure アプリ サービスの URL を入力するか貼り付けます。次に例を示します `https://twitterconnector.azurewebsites.net` 。
    
    - [パスワード **] ボックス** に、手順 2 で作成した APISecretKey の値を入力するか貼り付けます。
    
    - **[Azure アプリ ID]** ボックスに、手順 1 で取得した Azure アプリケーション アプリ ID (クライアント *ID* とも呼ばれる) の値を入力するか貼り付けます。

6. 接続が正常に検証された後、[次へ] をクリック **します**。

7. [ **データのインポートを承認する Microsoft 365]** ページで、APISecretKey を再び入力または貼り付け、[  **ログイン] Web アプリをクリックします**。

8. Twitter で **ログインをクリックします**。

9. Twitter のサインイン ページで、組織の Twitter アカウントの資格情報を使用してサインインします。

   ![Twitter アカウントにサインインする](../media/TCimage42.png)

   サインインすると、Twitter ページに「Twitter Connector ジョブが正常にセットアップされました」というメッセージが表示されます。

10. [ **続行] を** クリックして、Twitter コネクタの設定を完了します。

11. [フィルター **の設定]** ページでは、フィルターを適用して、特定の年齢のアイテムを最初にインポートできます。 年齢を選択し、[次へ] を **クリックします**。

12. [保存 **場所の** 選択] ページで、Twitter アイテムのインポート先の Microsoft 365 メールボックスのメール アドレスを入力し、[次へ] をクリック **します**。

13. [ **次へ]** をクリックしてコネクタの設定を確認し、[完了] **をクリックして** コネクタのセットアップを完了します。

14. コンプライアンス センターで、[データ コネクタ] ページに移動し、[コネクタ] タブをクリックしてインポート プロセスの進行状況を確認します。
