---
title: コネクタを展開して Facebook ビジネス ページのデータをアーカイブする
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
description: 管理者は、Microsoft 365 に Facebook Business ページをインポートしてアーカイブするネイティブ コネクタを設定できます。 このデータを Microsoft 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Facebook データのガバナンスを管理できます。
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619953"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>コネクタを展開して Facebook ビジネス ページのデータをアーカイブする

この記事では、Office 365 インポート サービスを使用して Facebook Business ページから Microsoft 365 にデータをインポートするコネクタを展開する手順について説明します。 このプロセスの概要と、Facebook コネクタを展開するために必要な前提条件の一覧については、「コネクタをセットアップして Facebook データをアーカイブする」を参照 [してください](archive-facebook-data-with-sample-connector.md)。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

1. グローバル管理者 <https://portal.azure.com> アカウントの資格情報を使用して、アクセスしてサインインします。

    ![AAD でアプリを作成する](../media/FBCimage1.png)

2. 左側のナビゲーション ウィンドウで **、Azure Active Directory をクリックします**。

    ![[Azure Active Directory] をクリックします。](../media/FBCimage2.png)

3. 左側のナビゲーション ウィンドウで、アプリの登録 **(プレビュー)** をクリックし、[新しい登録] **をクリックします**。

    ![Click **App registrations (Preview)** and then click **New registration**](../media/FBCimage3.png)

4. アプリケーションを登録します。 [リダイレクト URI] で、アプリケーションの種類のドロップダウン リストで [Web] を選択し、URI のボックス <https://portal.azure.com> に入力します。

   ![アプリケーションの登録](../media/FBCimage4.png)

5. アプリケーション **(クライアント) ID と****ディレクトリ (テナント) ID** をコピーし、テキスト ファイルなどの安全な場所に保存します。 これらの ID は、後の手順で使用します。

   ![アプリケーション ID とディレクトリ ID をコピーして保存する](../media/FBCimage5.png)

6. 新しい **アプリの&証明書とシークレットに移動します。**

   ![新しいアプリの証明書&シークレットに移動します。](../media/FBCimage6.png)

7. [新 **しいクライアント シークレット] をクリックする**

   ![[新しいクライアント シークレット] をクリックする](../media/FBCimage7.png)

8. 新しいシークレットを作成します。 説明ボックスにシークレットを入力し、有効期限を選択します。

    ![シークレットを入力し、有効期限を選択する](../media/FBCimage8.png)

9. シークレットの値をコピーし、テキスト ファイルまたは他の保存場所に保存します。 これは、後の手順で使用する AAD アプリケーション シークレットです。

   ![シークレットの値をコピーして保存する](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>手順 2: GitHub から Azure アカウントにコネクタ Web サービスを展開する

1. この [GitHub サイトに移動し、[Azure](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) に展開 **] をクリックします**。

    ![[Azure への展開] をクリックします。](../media/FBCGithubApp.png)

2. [Azure に **展開] を** クリックすると、カスタム テンプレート ページを使用して Azure Portal にリダイレクトされます。 [基本と **設定] の詳細** を **入力し、[** 購入] をクリック **します**。

   - **サブスクリプション:** Facebook Business ページ コネクタ Web サービスを展開する Azure サブスクリプションを選択します。

   - **リソース グループ:** 新しいリソース グループを選択または作成します。 リソース グループは、Azure ソリューションの関連リソースを保持するコンテナーです。

   - **場所:** 場所を選択します。

   - **Web アプリ名:** コネクタ Web アプリの一意の名前を指定します。 名前の長さは 3 ~ 18 文字です。 この名前は、Azure アプリ サービスの URL を作成するために使用されます。たとえば **、fbconnector** の Web アプリ名を指定すると、Azure アプリ サービスの URL が **fbconnector.azurewebsites.net。**

   - **tenantId:** 手順 1 で Azure Active Directory で Facebook コネクタ アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。

   - **APISecretKey:** 任意の値をシークレットとして入力できます。 これは、手順 5 でコネクタ Web アプリにアクセスするために使用されます。

     ![[リソースの作成] をクリックし、ストレージ アカウントを入力します。](../media/FBCimage12.png)

3. 展開が成功すると、ページは次のスクリーンショットのようになります。

   ![[ストレージ] をクリックし、[ストレージ アカウント] をクリックします。](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>手順 3: Facebook アプリを登録する

1. に移動し、組織の Facebook Business ページのアカウントの資格情報を使用してログインし、[新しいアプリの追加] を <https://developers.facebook.com> **クリックします**。

   ![Facebook ビジネス ページ用の新しいアプリを追加する](../media/FBCimage25.png)

2. 新しいアプリ ID を作成します。

   ![新しいアプリ ID を作成する](../media/FBCimage26.png)

3. 左側のナビゲーション ウィンドウで、[製品の追加]をクリックし、[Facebook ログイン] タイルの [**セットアップ] をクリック** します。

   ![[製品の追加] をクリックします。](../media/FBCimage27.png)

4. [Facebook ログインの統合] ページで **、[Web] をクリックします**。

   ![[Facebook ログインの統合] ページで [Web] をクリックする](../media/FBCimage28.png)

5. Azure アプリ サービスの URL を追加します。次に例を示します `https://fbconnector.azurewebsites.net` 。

   ![Azure アプリ サービスの URL を追加する](../media/FBCimage29.png)

6. Facebook ログインのセットアップのクイック スタート セクションに入力します。

   ![クイック スタート セクションを完了する](../media/FBCimage30.png)

7. 左側のナビゲーション ウィンドウの **Facebook** ログインで、[設定] をクリックし、[有効な OAuth リダイレクト URI] ボックスに OAuth リダイレクト URI **を追加** します。 **\<connectorserviceuri> 形式 /Views/FacebookOAuth** を使用します。connectorserviceuri の値は、組織の Azure アプリ サービスの URL です。たとえば `https://fbconnector.azurewebsites.net` 、 .

   ![[有効な OAuth リダイレクト URI] ボックスに OAuth リダイレクト URI を追加する](../media/FBCimage31.png)

8. 左側のナビゲーション ウィンドウで、[製品の追加]**をクリックし****、[Webhook] をクリックします。** [ページ **] の** プル ダウン メニューで、[ページ] を **クリックします**。

   ![[製品の追加] をクリックし、[**Webhooks] をクリックします。](../media/FBCimage32.png)

9. Webhook コールバック URL を追加し、確認トークンを追加します。 コールバック URL の形式は **<connectorserviceuri> 、/api/FbPageWebhook** という形式を使用します。ここで、connectorserviceuri の値は組織の Azure アプリ サービス URL です。たとえば `https://fbconnector.azurewebsites.net` 、 .

   検証トークンは強力なパスワードに似ている必要があります。 検証トークンをテキスト ファイルまたは他の保存場所にコピーします。

   ![確認トークンを追加する](../media/FBCimage33.png)

10. フィード用にエンドポイントをテストしてサブスクライブします。

    ![エンドポイントのテストとサブスクライブ](../media/FBCimage34.png)

11. プライバシー URL、アプリ アイコン、およびビジネスでの使用を追加します。 また、アプリ ID とアプリ シークレットをテキスト ファイルまたは他の保存場所にコピーします。

    ![プライバシー URL、アプリ アイコン、およびビジネスでの使用を追加する](../media/FBCimage35.png)

12. アプリを公開します。

    ![アプリを公開する](../media/FBCimage36.png)

13. 管理者ロールまたはテスター ロールにユーザーを追加します。

    ![管理者またはテスターロールにユーザーを追加する](../media/FBCimage37.png)

14. ページ パブリック **コンテンツ アクセスのアクセス許可を追加** します。

    ![ページ パブリック コンテンツ アクセスのアクセス許可を dd](../media/FBCimage38.png)

15. ページの管理権限を追加します。

    ![ページの管理権限を追加する](../media/FBCimage39.png)

16. Facebook によってレビューされたアプリケーションを取得します。

    ![Facebook によってレビューされたアプリケーションを取得する](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>手順 4: コネクタ Web アプリを構成する

1. (AzureAppResourceName は手順 4 で指定した Azure アプリ リソースの名前です) に `https://<AzureAppResourceName>.azurewebsites.net` 移動します。 たとえば、名前が **fbconnector の場合は**、移動します `https://fbconnector.azurewebsites.net` 。 アプリのホーム ページは、次のスクリーンショットのようになります。

   ![Go to you connector web app](../media/FBCimage41.png)

2. [ **構成] を** クリックしてサインイン ページを表示します。

   ![[構成] をクリックしてサインイン ページを表示する](../media/FBCimage42.png)

3. [テナント ID] ボックスに、テナント ID (手順 2 で取得した ID) を入力するか貼り付けます。 パスワード ボックスに、APISecretKey (手順 2 で取得したキー) を入力するか貼り付け、[構成設定の設定] をクリックして構成の詳細ページを表示します。

    ![テナント ID とパスワードを使用してサインインし、構成の詳細ページに移動する](../media/FBCimage43.png)

4. 次の構成設定を入力します。

   - **Facebook アプリケーション ID:** 手順 3 で取得した Facebook アプリケーションのアプリ ID。

   - **Facebook アプリケーション シークレット:** 手順 3 で取得した Facebook アプリケーションのアプリ シークレット。

   - **Facebook webhooks はトークンを確認します。** 手順 3 で作成した検証トークン。

   - **AAD アプリケーション ID:** 手順 1 で作成した Azure Active Directory アプリのアプリケーション ID。

   - **AAD アプリケーション シークレット:** 手順 1 で作成した APISecretKey シークレットの値。

5. [ **保存] を** クリックしてコネクタの設定を保存します。

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>手順 5: Microsoft 365 コンプライアンス センターで Facebook コネクタをセットアップする

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの [ **データ コネクタ]** に移動してクリックします。

2. [データ **コネクタ] ページの** Facebook ビジネス ページ **で、[表示**] を **クリックします**。

3. Facebook の **ビジネス ページで、[コネクタの** 追加] **をクリックします**。

4. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

5. [コネクタ **アプリの資格情報の追加** ] ページで、次の情報を入力し、[接続の検証] **をクリックします**。

   ![コネクタ アプリの資格情報を入力する](../media/TCimage38.png)

   - [名前 **] ボックス** に、コネクタの名前 (Facebook のニュース ページなど) **を入力します**。

   - [接続 **URL] ボックス** に、Azure アプリ サービスの URL を入力するか貼り付けます。次に例を示します `https://fbconnector.azurewebsites.net` 。

   - [パスワード **] ボックス** に、手順 2 で追加した APISecretKey の値を入力するか貼り付けます。

   - **[Azure アプリ ID]** ボックスに、手順 1 で作成した AAD アプリケーション ID とも呼ばれるアプリケーション (クライアント) ID の値を入力するか貼り付けます。

6. 接続が正常に検証された後、[次へ] をクリック **します**。

7. [ **データのインポートを承認する Microsoft 365]** ページで、APISecretKey を再び入力または貼り付け、[ **ログイン] Web アプリをクリックします**。

8. [Facebook **コネクタ アプリ** の構成] ページで **、[Facebook** でログイン] をクリックし、組織の Facebook Business ページのアカウントの資格情報を使用してログインします。 ログインした Facebook アカウントに、組織の Facebook Business ページの管理者ロールが割り当てられている必要があります。

   ![Facebook でログインする](../media/FBCimage50.png)

9. ログインした Facebook アカウントによって管理されているビジネス ページのリストが表示されます。 アーカイブするページを選択し、[次へ] を **クリックします**。

   ![アーカイブする組織のビジネス ページを選択する](../media/FBCimage52.png)

10. [ **続行]** をクリックして、コネクタ サービス アプリのセットアップを終了します。

11. [フィルター **の設定]** ページでは、フィルターを適用して、特定の年齢のアイテムを最初にインポートできます。 年齢を選択し、[次へ] を **クリックします**。

12. [保存 **場所の** 選択] ページで、Facebook アイテムのインポート先の Microsoft 365 メールボックスのメール アドレスを入力し、[次へ] をクリック **します**。

13. [ **次へ]** をクリックしてコネクタの設定を確認し、[完了] **をクリックして** コネクタのセットアップを完了します。

14. コンプライアンス センターで、[データ コネクタ] ページに移動し、[コネクタ] タブをクリックしてインポート プロセスの進行状況を確認します。
