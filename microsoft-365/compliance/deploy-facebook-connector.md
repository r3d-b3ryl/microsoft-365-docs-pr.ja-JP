---
title: コネクタをデプロイして Facebook Business ページデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、ネイティブ コネクタを設定して、Facebook Business ページをインポートしてMicrosoft 365にアーカイブできます。 このデータをMicrosoft 365にインポートした後は、訴訟ホールド、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織の Facebook データのガバナンスを管理できます。
ms.openlocfilehash: 126b4af3887632df5c8f83eac8e20fe5d88c8608
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64949181"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>コネクタをデプロイして Facebook Business ページデータをアーカイブする

この記事には、Office 365 Import サービスを使用して Facebook Business ページからMicrosoft 365にデータをインポートするコネクタをデプロイするためのステップ バイ ステップ プロセスが含まれています。 このプロセスの概要と、Facebook コネクタをデプロイするために必要な前提条件の一覧については、「Facebook [データをアーカイブするためのコネクタの設定」を](archive-facebook-data-with-sample-connector.md)参照してください。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directoryでアプリを作成する

1. <https://portal.azure.com>グローバル管理者アカウントの資格情報を使用して、アクセスしてサインインします。

    ![AADでアプリを作成します。](../media/FBCimage1.png)

2. 左側のナビゲーション ウィンドウで **[Azure Active Directory]** をクリックします。

    ![[Azure Active Directory] をクリックします。](../media/FBCimage2.png)

3. 左側のナビゲーション ウィンドウで、[**アプリの登録 (プレビュー)]** をクリックし、[**新しい登録**] をクリックします。

    ![[**アプリの登録 (プレビュー)]** をクリックし、[**新しい登録**] をクリックします。](../media/FBCimage3.png)

4. アプリケーションを登録します。 [リダイレクト URI] で、アプリケーションの種類ドロップダウン リストで [Web] を選択し、URI のボックスに入力 <https://portal.azure.com> します。

   ![アプリケーションを登録します。](../media/FBCimage4.png)

5. **アプリケーション (クライアント) ID** と **ディレクトリ (テナント) ID を** コピーし、テキスト ファイルまたはその他の安全な場所に保存します。 これらの ID は、後の手順で使用します。

   ![アプリケーション ID とディレクトリ ID をコピーして保存します。](../media/FBCimage5.png)

6. **新しいアプリの証明書&シークレットに** 移動します。

   ![新しいアプリの証明書&シークレットに移動します。](../media/FBCimage6.png)

7. [**新しいクライアント シークレット**] をクリックします。

   ![[新しいクライアント シークレット] をクリックします。](../media/FBCimage7.png)

8. 新しいシークレットを作成します。 説明ボックスにシークレットを入力し、有効期限を選択します。

    ![シークレットを入力し、有効期限を選択します。](../media/FBCimage8.png)

9. シークレットの値をコピーし、テキスト ファイルまたはその他の保存場所に保存します。 これは、後の手順で使用するAADアプリケーション シークレットです。

   ![シークレットの値をコピーして保存します。](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>手順 2: GitHubから Azure アカウントにコネクタ Web サービスをデプロイする

1. [このGitHub サイト](https://github.com/microsoft/m365-sample-connector-csharp-aspnet)に移動し、[**Azure へのデプロイ**] をクリックします。

    ![[Azure へのデプロイ] をクリックします。](../media/FBCGithubApp.png)

2. **[Azure へのデプロイ**] をクリックすると、カスタム テンプレート ページを含むAzure portalにリダイレクトされます。 **基本** と **設定** の詳細を入力し、[**購入**] をクリックします。

   - **サブスクリプション：** Facebook Business ページ コネクタ Web サービスをデプロイする Azure サブスクリプションを選択します。

   - **リソース グループ:** 新しいリソース グループを選択または作成します。 リソース グループは、Azure ソリューションの関連リソースを保持するコンテナーです。

   - **場所：** 場所を選択します。

   - **Web アプリ名:** コネクタ Web アプリの一意の名前を指定します。 名前の長さは 3 文字から 18 文字にする必要があります。 この名前は、Azure アプリ サービスの URL を作成するために使用されます。たとえば、 **fbconnector** の Web アプリ名を指定すると、Azure アプリ サービスの URL **が fbconnector.azurewebsites.net** されます。

   - **tenantId:** 手順 1 のAzure Active Directoryで Facebook コネクタ アプリを作成した後にコピーしたMicrosoft 365組織のテナント ID。

   - **APISecretKey:** 任意の値をシークレットとして入力できます。 これは、手順 5. のコネクタ Web アプリにアクセスするために使用されます。

     ![[リソースの作成] をクリックし、ストレージ アカウントを入力します。](../media/FBCimage12.png)

3. デプロイが成功すると、ページは次のスクリーンショットのようになります。

   ![[Storage] をクリックし、[Storage アカウント] をクリックします。](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>手順 3: Facebook アプリを登録する

1. に移動し <https://developers.facebook.com>、組織の Facebook Business ページのアカウントの資格情報を使用してログインし、[ **新しいアプリの追加**] をクリックします。

   ![Facebook ビジネス ページ用の新しいアプリを追加します。](../media/FBCimage25.png)

2. 新しいアプリ ID を作成します。

   ![新しいアプリ ID を作成します。](../media/FBCimage26.png)

3. 左側のナビゲーション ウィンドウで、[**製品の追加**] をクリックし、**Facebook ログイン** タイルで **[セットアップ**] をクリックします。

   ![[製品の追加] をクリックします。](../media/FBCimage27.png)

4. [Facebook ログインの統合] ページで、[ **Web**] をクリックします。

   ![[Facebook ログインの統合] ページで [Web] をクリックします。](../media/FBCimage28.png)

5. Azure アプリ サービスの URL を追加します。たとえば.`https://fbconnector.azurewebsites.net`

   ![Azure アプリ サービスの URL を追加します。](../media/FBCimage29.png)

6. Facebook ログイン設定のクイック スタート セクションを完了します。

   ![[クイック スタート] セクションを完了します。](../media/FBCimage30.png)

7. **Facebook ログイン** の下の左側のナビゲーション ウィンドウで **、[設定**] をクリックし、[**有効な OAuth リダイレクト URI] ボックスに OAuth リダイレクト URI を** 追加します。 **/Views/FacebookOAuth の形式\<connectorserviceuri>** を使用します。connectorserviceuri の値は組織の Azure アプリ サービス URL です。たとえば、 `https://fbconnector.azurewebsites.net`

   ![OAuth リダイレクト URI を [有効な OAuth リダイレクト URI] ボックスに追加します。](../media/FBCimage31.png)

8. 左側のナビゲーション ウィンドウで [**製品の追加**] をクリックし、[**Webhook**] をクリックします。 **[ページ**] プルダウン メニューの [**ページ**] をクリックします。

   ![[製品の追加] をクリックし、[**Webhook] をクリックします。](../media/FBCimage32.png)

9. Webhooks コールバック URL を追加し、検証トークンを追加します。 コールバック URL の形式は、connectorserviceuri の値が組織の Azure アプリ サービス URL である形式 `<connectorserviceuri>/api/FbPageWebhook`を使用します。たとえば `https://fbconnector.azurewebsites.net`、

   検証トークンは、強力なパスワードに似ている必要があります。 検証トークンをテキスト ファイルまたはその他の保存場所にコピーします。

   ![検証トークンを追加します。](../media/FBCimage33.png)

10. フィードのエンドポイントをテストしてサブスクライブします。

    ![エンドポイントをテストしてサブスクライブします。](../media/FBCimage34.png)

11. プライバシー URL、アプリ アイコン、ビジネスユースを追加します。 また、アプリ ID とアプリ シークレットをテキスト ファイルまたはその他の保存場所にコピーします。

    ![プライバシー URL、アプリ アイコン、ビジネスユースを追加します。](../media/FBCimage35.png)

12. アプリをパブリックにします。

    ![アプリをパブリックにします。](../media/FBCimage36.png)

13. 管理者ロールまたはテスター ロールにユーザーを追加します。

    ![管理者ロールまたはテスター ロールにユーザーを追加します。](../media/FBCimage37.png)

14. **ページパブリック コンテンツ アクセス** 許可を追加します。

    ![dd the Page Public Content Access permission.](../media/FBCimage38.png)

15. ページの管理アクセス許可を追加します。

    ![ページの管理アクセス許可を追加します。](../media/FBCimage39.png)

16. Facebook によってレビューされたアプリケーションを取得します。

    ![Facebook によってレビューされたアプリケーションを取得します。](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>手順 4: コネクタ Web アプリを構成する

1. (AzureAppResourceName は、手順 4. で指定した Azure アプリ リソースの名前です) に `https://<AzureAppResourceName>.azurewebsites.net` 移動します。 たとえば、名前が **fbconnector** の場合は、 `https://fbconnector.azurewebsites.net`. アプリのホーム ページは、次のスクリーンショットのようになります。

   ![コネクタ Web アプリに移動します。](../media/FBCimage41.png)

2. [ **構成] を** クリックしてサインイン ページを表示します。

   ![[構成] をクリックしてサインイン ページを表示します。](../media/FBCimage42.png)

3. [テナント ID] ボックスに、テナント ID (手順 2 で取得した) を入力または貼り付けます。 パスワード ボックスに、APISecretKey (手順 2 で取得した) を入力または貼り付け、**構成設定の設定** をクリックして構成の詳細ページを表示します。

    ![テナント ID とパスワードを使用してサインインし、構成の詳細ページに移動します。](../media/FBCimage43.png)

4. 次の構成設定を入力します

   - **Facebook アプリケーション ID:** 手順 3 で取得した Facebook アプリケーションのアプリ ID。

   - **Facebook アプリケーション シークレット:** 手順 3 で取得した Facebook アプリケーションのアプリ シークレット。

   - **Facebook Webhook はトークンを確認します。** 手順 3 で作成した検証トークン。

   - **AAD アプリケーション ID:** 手順 1. で作成したAzure Active Directory アプリのアプリケーション ID。

   - **AAD アプリケーション シークレット:** 手順 1 で作成した APISecretKey シークレットの値。

5. [ **保存] を** クリックしてコネクタの設定を保存します。

## <a name="step-5-set-up-a-facebook-connector-in-the-compliance-portal"></a>手順 5: コンプライアンス ポータルで Facebook コネクタを設定する

1. Microsoft Purview コンプライアンス ポータルに移動し、/a<**データ コネクタ** を選択します<a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">。

2. **Facebook Business** ページ **の [データ コネクタ**] ページで、[**表示**] をクリックします。

3. **Facebook ビジネス ページ ページ** で、[コネクタの **追加**] をクリックします。

4. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

5. [ **コネクタ アプリの資格情報の追加]** ページで、次の情報を入力し、[ **接続の検証**] をクリックします。

   ![コネクタ アプリの資格情報を入力します。](../media/TCimage38.png)

   - [ **名前]** ボックスに、 **Facebook ニュース ページ** などのコネクタの名前を入力します。

   - [**接続 URL**] ボックスに、Azure アプリ サービスの URL を入力または貼り付けます。たとえば.`https://fbconnector.azurewebsites.net`

   - [ **パスワード** ] ボックスに、手順 2. で追加した APISecretKey の値を入力または貼り付けます。

   - **[Azure アプリ ID**] ボックスに、手順 1 で作成したアプリケーション ID とも呼ばれるアプリケーション (クライアント) ID の値AAD入力または貼り付けます。

6. 接続が正常に検証されたら、[ **次へ**] をクリックします。

7. [**データをインポートするための承認Microsoft 365**] ページで、APISecretKey をもう一度入力または貼り付けてから、[**ログイン Web アプリ**] をクリックします。

8. **[Facebook コネクタ アプリの構成]** ページ **で、[Facebook でログイン**] をクリックし、組織の Facebook Business ページのアカウントの資格情報を使用してログインします。 ログインした Facebook アカウントに、組織の Facebook Business ページの管理者ロールが割り当てられていることを確認します。

   ![Facebook でログインします。](../media/FBCimage50.png)

9. ログインした Facebook アカウントによって管理されているビジネス ページの一覧が表示されます。 アーカイブするページを選択し、[ **次へ**] をクリックします。

   ![アーカイブする組織のビジネス ページを選択します。](../media/FBCimage52.png)

10. [ **続行]** をクリックして、コネクタ サービス アプリのセットアップを終了します。

11. [ **フィルターの設定** ] ページで、フィルターを適用して、特定の年齢のアイテムを最初にインポートできます。 年齢を選択し、[ **次へ**] をクリックします。

12. [**ストレージの場所の選択]** ページで、Facebook アイテムのインポート先となるメールボックスMicrosoft 365メール アドレスを入力し、[**次へ**] をクリックします。

13. [ **次へ** ] をクリックしてコネクタの設定を確認し、[ **完了]** をクリックしてコネクタの設定を完了します。

14. コンプライアンス センターの [ **データ コネクタ** ] ページに移動し、[ **コネクタ** ] タブをクリックしてインポート プロセスの進行状況を確認します。
