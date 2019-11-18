---
title: Office 365 で Facebook データをアーカイブするためのコネクタの展開
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
description: 管理者は、Facebook のビジネスページをインポートおよびアーカイブするためのネイティブコネクタを Office 365 にセットアップすることができます。 このデータを Office 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Facebook データのガバナンスを管理できます。
ms.openlocfilehash: 786ff97c558a5618643783de803c742c50185f00
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "38686819"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a>Office 365 で Facebook データをアーカイブするためのコネクタの展開

この記事では、Office 365 インポートサービスを使用して Facebook のビジネスページから Office 365 にデータをインポートするコネクタを展開するための段階的なプロセスについて説明します。 このプロセスの概要と、Facebook コネクタを展開するために必要な前提条件の一覧については、「[サンプルコネクタを使用して Office 365 で facebook データをアーカイブする (プレビュー)](archive-facebook-data-with-sample-connector.md)」を参照してください。 

## <a name="step-1-download-the-package"></a>手順 1: パッケージをダウンロードする

の GitHub リポジトリのリリースセクションから、構築済みパッケージをダウンロード<https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>します。 最新リリースの下で、 **SampleConnector**という名前の zip ファイルをダウンロードします。 この zip ファイルを手順4で Azure にアップロードします。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>手順 2: Azure Active Directory でアプリを作成する

1. に<https://portal.azure.com>移動し、Office 365 グローバル管理者アカウントの資格情報を使用してサインインします。

    ![AAD でアプリを作成する](media/FBCimage1.png)

2. 左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。

    ![[Azure Active Directory] をクリックします。](media/FBCimage2.png)

3. 左側のナビゲーションウィンドウで、[**アプリの登録 (プレビュー)** ] をクリックし、[**新しい登録**] をクリックします。

    ![[* * アプリの登録 (プレビュー)] をクリックし、[* * 新しい登録] * * をクリックします。](media/FBCimage3.png)

4. アプリケーションを登録します。 [リダイレクト URI] で、[アプリケーションの種類] ドロップダウンリストから<https://portal.azure.com> [Web] を選択し、URI のボックスに入力します。

   ![アプリケーションの登録](media/FBCimage4.png)

5. **アプリケーション (クライアント) id**と**ディレクトリ (テナント) id**をコピーし、それをテキストファイルまたは他の安全な場所に保存します。 これらの Id は、後の手順で使用します。

   ![アプリケーション ID とディレクトリ ID をコピーして保存します。](media/FBCimage5.png)

6. [証明書] に移動して **、新しいアプリのシークレット & します。**

   ![新しいアプリの証明書 & シークレットに移動します。](media/FBCimage6.png)

7. [**新しいクライアントシークレット**] をクリックします。

   ![[新しいクライアントシークレット] をクリックします。](media/FBCimage7.png)

8. 新しいシークレットを作成します。 [説明] ボックスに、シークレットを入力し、有効期限を選択します。 

    ![シークレットを入力して、有効期限を選択する](media/FBCimage8.png)

9. シークレットの値をコピーして、テキストファイルまたは他の保存場所に保存します。 これは、後の手順で使用する AAD アプリケーションシークレットです。

   ![シークレットの値をコピーして保存する](media/FBCimage9.png)

10. **マニフェスト**に移動し、次のスクリーンショットで強調表示されているように、identifieruris (AAD アプリケーション Uri とも呼ばれる) をコピーします。 AAD アプリケーション Uri をテキストファイルまたは他の保存場所にコピーします。 手順6で使用します。

   ![マニフェストに移動し、AAD アプリケーション Uri をコピーします。](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>手順 3: Azure storage アカウントを作成する

1. 組織の Azure ホームページに移動します。

    ![Azure ホームページに移動する](media/FBCimage11.png)

2. [**リソースの作成**] をクリックし、検索ボックスに「 **storage account** 」と入力します。

    ![[リソースを作成し、ストレージアカウントを入力してください] をクリックします。](media/FBCimage12.png)

3. [**記憶域**] をクリックし、[**ストレージアカウント**] をクリックします。

    ![[記憶域] をクリックし、[ストレージアカウント] をクリックします。](media/FBCimage13.png)

4. [**ストレージアカウントの作成**] ページの [サブスクリプション] ボックスで、使用している Azure サブスクリプションの種類に応じて、[**購入時に支払う**] または [**無料試用版**] を選択します。 次に、リソースグループを選択または作成します。

    ![[お支払い方法] または [無料試用版] を選択する](media/FBCimage14.png)

5. ストレージアカウントの名前を入力します。

    ![ストレージアカウントの名前を入力します。](media/FBCimage15.png)

6. 確認してから [**作成**] をクリックして、ストレージアカウントを作成します。

    ![ストレージアカウントを作成する](media/FBCimage16.png)

7. しばらくしてから、[**更新**] をクリックし、[**リソースに移動**] をクリックして、ストレージアカウントに移動します。

    ![ストレージアカウントに移動します。](media/FBCimage17.png)

8. 左側のナビゲーションウィンドウで [**アクセスキー** ] をクリックします。

    ![[アクセスキー] をクリックします。](media/FBCimage18.png)

9. **接続文字列**をコピーし、テキストファイルまたは他の保存場所に保存します。 これは、web アプリケーションリソースを作成するときに使用します。

    ![接続文字列をコピーして保存する](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>手順 4: Azure で新しい web app リソースを作成する

1. Azure portal の**ホーム**ページで、[**リソース\>すべて\>の Web アプリの作成**] をクリックします。 [ **Web アプリ**] ページで、[**作成**] をクリックします。 

   ![新しい web app リソースを作成する](media/FBCimage20.png)

2. 詳細を入力し (次の図を参照)、Web アプリを作成します。 [**アプリケーション名**] ボックスに入力した名前が Azure App SERVICE の URL を作成するために使用されることに注意してください。たとえば、fbconnector.azurewebsites.net のようになります。

   ![詳細を入力してから Web アプリを作成する](media/FBCimage21.png)

3. 新しく作成した web app リソースに移動し、左側のナビゲーションウィンドウで [**アプリケーション設定**] をクリックします。 [アプリケーションの設定] で、[新しい設定の追加] をクリックし、次の3つの設定を追加します。値 (前の手順で入力したテキストファイルにコピーした値) を使用します。 

    - **APISecretKey** –任意の値をシークレットとして入力できます。 これは、手順7でコネクタ web アプリにアクセスするために使用されます。

    - **Storageaccountconnectionstring** —手順3で Azure storage アカウントを作成した後にコピーした接続文字列 Uri。

    - **tenantId** –手順2で Azure Active Directory で Facebook connector アプリを作成した後にコピーした Office 365 組織のテナント ID。

    ![アプリケーション設定を入力します。](media/FBCimage22.png)

4. [**全般設定**] で、[**常にオン**] の横にある [**オン**] をクリックします。 ページの上部にある [**保存**] をクリックして、アプリケーションの設定を保存します。

   ![アプリケーションの設定を保存する](media/FBCimage23.png)

5. 最後の手順では、手順1でダウンロードしたコネクタアプリソースコードを Azure にアップロードします。 Web ブラウザーで、https://<AzureAppResourceName>に移動します。 たとえば、Azure app リソース (このセクションの手順2で名前を付けた) の名前が**fbconnector**の場合は、にhttps://fbconnector.scm.azurewebsites.net/ZipDeployUi移動します。 

6. 手順1でダウンロードした SampleConnector をドラッグアンドドロップして、このページに移動します。 ファイルがアップロードされ、展開が正常に完了すると、ページは次のスクリーンショットのようになります。

   ![このページに SampleConnector をドラッグアンドドロップします。](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a>手順 5: Facebook アプリを登録する

1. に<https://developers.facebook.com>移動して、組織の Facebook ビジネスページのアカウントの資格情報を使用してログインし、[**新しいアプリの追加**] をクリックします。

   ![[Facebook ビジネス用の新しいアプリの追加] ページ](media/FBCimage25.png)

2. 新しいアプリ ID を作成します。

   ![新しいアプリ ID を作成する](media/FBCimage26.png)

3. 左側のナビゲーションウィンドウで、[**製品の追加**] をクリックし、 **Facebook ログイン**タイルで [**設定**] をクリックします。

   ![[製品の追加] をクリックします。](media/FBCimage27.png)

4. [Facebook ログインの統合] ページで、[ **Web**] をクリックします。

   ![[Facebook ログインの統合] ページで、[Web] をクリックします。](media/FBCimage28.png)

5. Azure app service の URL を追加します。例`https://fbconnector.azurewebsites.net`を示します。

   ![Azure app service の URL を追加する](media/FBCimage29.png)

6. Facebook ログインセットアップのクイックスタートセクションを完了します。

   ![クイックスタートセクションを完了する](media/FBCimage30.png)

7. [ **Facebook ログイン**] の左側のナビゲーションウィンドウで、[**設定**] をクリックし、[**有効な oauth リダイレクト**URI] ボックスに oauth リダイレクト uri を追加します。 ** \</Views/facebookoauth の>** 形式を使用します。この場合は、を使用します。この場合、コネクタサービス uri の値は組織の Azure app service URL になります。たとえば、 `https://fbconnector.azurewebsites.net`のようになります。

   ![OAuth リダイレクト URI を [有効な OAuth リダイレクト uri] ボックスに追加する](media/FBCimage31.png)

8. 左側のナビゲーションウィンドウで、[**製品の追加**] をクリックし、[webhooks] をクリックし**ます。** **ページ**のプルダウンメニューで、[**ページ**] をクリックします。 

   ![[製品の追加] をクリックし、[* * Webhooks] をクリックします。](media/FBCimage32.png)

9. Webhooks コールバック URL を追加し、検証トークンを追加します。 コールバック URL の形式。 ** <connectorserviceuri>/api/fbpagewebhook**の形式を使用します。ここで、コネクタサービス uri の値は、組織の Azure app service URL になります。例`https://fbconnector.azurewebsites.net`を示します。 

    Verify トークンは、強力なパスワードと類似している必要があります。 検証トークンをテキストファイルまたは他の保存場所にコピーします。

        ![Add the verify token](media/FBCimage33.png)

10. フィードのエンドポイントをテストし、サブスクライブします。

    ![エンドポイントをテストおよびサブスクライブする](media/FBCimage34.png)

11. プライバシー URL、アプリアイコン、およびビジネス用途を追加します。 また、アプリケーション ID とアプリシークレットをテキストファイルまたは他の保存場所にコピーします。

    ![プライバシー URL、アプリアイコン、およびビジネス用途を追加する](media/FBCimage35.png)

12. アプリを公開します。

    ![アプリを公開する](media/FBCimage36.png)

13. 管理者またはテスト担当者の役割にユーザーを追加します。

    ![管理者またはテスト担当者の役割にユーザーを追加する](media/FBCimage37.png)

14. ページの**パブリックコンテンツのアクセス**許可を追加します。

    ![dd ページのパブリックコンテンツアクセス許可](media/FBCimage38.png)

15. [ページの管理] アクセス許可を追加します。

    ![ページの管理アクセス許可を追加する](media/FBCimage39.png)

16. Facebook によって確認されたアプリケーションを取得します。

    ![Facebook によって確認されたアプリケーションを取得する](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a>手順 6: コネクタ web アプリを構成する

1. Https://\<AzureAppResourceName> に移動します (ここで、AzureAppResourceName は、手順4で名前を付けた Azure app リソースの名前です)。たとえば、名前が**fbconnector**の場合`https://fbconnector.azurewebsites.net`は、に移動します。 アプリのホームページは、次のスクリーンショットのようになります。

   ![「Go connector web app」に移動します。](media/FBCimage41.png)

2. [**構成**] をクリックして、サインインページを表示します。
 
   ![[構成] をクリックしてサインインページを表示する](media/FBCimage42.png)

3. [テナント Id] ボックスに、テナント Id を入力するか貼り付けます (手順2で取得したもの)。 [パスワード] ボックスに、APISecretKey (手順2で取得した) を入力するか貼り付け、[**構成設定の設定**] をクリックして**構成の詳細**ページを表示します。

    ![テナント Id とパスワードを使用してサインインし、[構成の詳細] ページに移動します。](media/FBCimage43.png)

4. [**構成の詳細**] で、次の構成設定を入力します。 

   - **Facebook アプリケーション id** –手順5で取得した facebook アプリケーションのアプリ id。
   - **Facebook アプリケーションシークレット**–手順5で取得した facebook アプリケーションのアプリシークレット。
   - **Facebook webhook verify token** –手順5で作成した verify トークン。
   - **AAD アプリケーション id** –手順2で作成した Azure Active Directory アプリのアプリケーション id。
   - **AAD アプリケーションシークレット**–手順4で作成した APISecretKey シークレットの値。
   - **Aad アプリケーション uri** –手順2で取得した Aad アプリケーション uri。たとえば、 `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`のようになります。
   - **App insights インストルメンテーションキー** –このボックスは空白のままにします。

5. [**保存**] をクリックしてコネクタの設定を保存します。

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>手順 7: セキュリティ & コンプライアンスセンターでカスタムコネクタをセットアップする

1. に移動<https://protection.office.com>して、[**データ\>ガバナンス\> ] [サードパーティデータのインポート**] をクリックします。

   ![セキュリティ/コンプライアンスセンターに移動し、[データガバナンス] をクリックして、サードパーティのデータのインポート > アーカイブ >](media/FBCimage44.png)

2.  [**コネクタの追加**] をクリックし、[ **Facebook のページ**] をクリックします。

    ![Facebook コネクタを追加するコネクタを構成する](media/FBCimage46.png)

3.  [**コネクタアプリの追加**] ページで、次の情報を入力し、[**コネクタの検証**] をクリックします。

    - 最初のボックスに、 **Facebook**などのコネクタの名前を入力します。
    - 2番目のボックスに、手順4で追加した APISecretKey の値を入力するか貼り付けます。
    - 3番目のボックスに、Azure app service の URL を入力するか、貼り付けます。例`https://fbconnector.azurewebsites.net`を示します。
 
    コネクタの検証が正常に完了したら、[**次へ**] をクリックします。
    
    ![コネクタが正常に検証されたら、[次へ] をクリックします。](media/FBCimage47.png)

4.  [**コネクタアプリを使用してログイン] を**クリックします。

    ![[コネクタアプリを使用してログイン] をクリックします。](media/FBCimage45.png)

5. APISecretKey をもう一度入力するか貼り付け、[**コネクタサービスにログイン] を**クリックします。

   ![APISecretKey を入力するか貼り付け、[ログイン] ボタンをクリックします。](media/FBCimage48.png)

6. [ **Facebook でログイン] を**クリックします。

   ![[Facebook でログイン] をクリックします。](media/FBCimage49.png)

7. [ **Facebook へのログイン**] ページで、組織の facebook ビジネスページのアカウントの資格情報を使用してログインします。 ログインした Facebook アカウントに、組織の Facebook ビジネスページの管理者の役割が割り当てられていることを確認してください。

   ![Facebook へのログイン](media/FBCimage50.png)

8. [**ページの選択**] をクリックして、Office 365 でアーカイブする組織のビジネスページを選択します。

   ![[ページの選択] をクリックして、組織のビジネスページを表示します。](media/FBCimage51.png)

9. ログインした Facebook アカウントによって管理されるビジネスページの一覧が表示されます。 アーカイブするページを選択し、[**保存**] をクリックします。

    ![アーカイブする組織のビジネスページを選択します。](media/FBCimage52.png)

10. [**完了**] をクリックして、connector service アプリのセットアップを終了します。

    ![[完了] をクリックしてコネクタサービスアプリを終了します。](media/FBCimage53.png)

11. [**フィルターの設定**] ページでは、特定の年齢のアイテムをインポート (およびアーカイブ) するためのフィルターを適用できます。 **[次へ]** をクリックします。

    ![特定の期間のアイテムをインポートするためのフィルターを適用する](media/FBCimage54.png)

12. [**ストレージアカウントの設定**] ページで、以前に選択した Facebook ビジネスページのアイテムがインポートされる Office 365 メールボックスを選択します。

    ![Facebook からインポートされた Office 365 メールボックスアーカイブアイテムを指定する](media/FBCimage55.png)

13. 設定を確認し、[**完了**] をクリックして、セキュリティ & コンプライアンスセンターでコネクタの設定を完了します。

    ![コネクタの設定を確認する](media/FBCimage56.png)

14. [**サードパーティのデータをアーカイブ**する] ページに移動して、インポートプロセスの進行状況を表示します。

    ![[サードパーティのデータをアーカイブする] ページに移動してインポートプロセスを追跡する](media/FBCimage58.png)
