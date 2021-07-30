---
title: Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開
description: Microsoft Defender for Endpoint を Android に展開する方法について説明Microsoft Intune
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mde, android, installation, deploy, uninstallation,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e502c63cb30de23b190a0d6844c9e87d6720d707
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53657005"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

登録されているデバイスで Android に Defender for Endpoint を展開するIntune ポータル サイト説明します。 Intune デバイスの登録の詳細については、「デバイスの登録  [」を参照してください](/mem/intune/user-help/enroll-device-android-company-portal)。

> [!NOTE]
> **Android 上のエンドポイントの Defender が Google Play で [利用できる](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**
>
> Intune から Google Play に接続して、デバイス管理者と Android ユーザー登録モード全体に Defender for Endpoint アプリを展開Enterpriseできます。
>
> アプリの更新は、Google Play 経由で自動的に行います。

## <a name="deploy-on-device-administrator-enrolled-devices"></a>デバイス管理者が登録したデバイスに展開する

**デバイス管理者が登録したデバイスで Android Intune ポータル サイト Defender for Endpoint を展開する**

Android に Defender for Endpoint を展開する方法について、Intune ポータル サイトデバイス管理者が登録したデバイスについて説明します。

### <a name="add-as-android-store-app"></a>Android ストア アプリとして追加する

1. 管理 [Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)アプリ] [Androidアプリ] [Android ストア アプリの追加] に移動し、[ \>  \> 選択] を **選択します**。 **\>**

   ![管理センターのMicrosoft エンドポイント マネージャー Android ストア アプリケーションを追加する](images/mda-addandroidstoreapp.png)

2. [アプリの **追加] ページで** 、[アプリ情報] *セクションに次の情報* を入力します。

   - **名前**
   - **説明**
   - **Publisher** Microsoft として設定します。
   - **アプリ ストア URL as** https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play ストア URL)

   その他のフィールドはオプションです。 **[次へ]** を選択します。

   ![管理センターのMicrosoft エンドポイント マネージャーアプリ情報を追加する](images/mda-addappinfo.png)

3. [割り *当て] セクション* で、[必須] セクションに移動 **し** 、[グループの追加] **を選択します。** その後、Android アプリで Defender for Endpoint をターゲットとするユーザー グループを選択できます。 [選択 **] と [** 次へ] の順 **に選択します**。

    > [!NOTE]
    > 選択したユーザー グループは、Intune に登録されたユーザーで構成する必要があります。

    > [!div class="mx-imgBorder"]

    > ![管理センターで選択Microsoft エンドポイント マネージャーグループのイメージ](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. [レビュー **+ 作成] セクション** で、入力した情報が正しいか確認し、[作成] を **選択します**。

    しばらくすると、Defender for Endpoint アプリが正常に作成され、ページの右上隅に通知が表示されます。

    ![Defender エンドポイント アプリMicrosoft エンドポイント マネージャー管理センター通知のイメージ](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. 表示されるアプリ情報ページの [モニター]セクションで、[デバイスのインストール状態] を選択して、デバイスのインストールが正常に完了したと確認します。

    > [!div class="mx-imgBorder"]
    > ![管理センター Microsoft エンドポイント マネージャーインストールのイメージ](images/513cf5d59eaaef5d2b5bc122715b5844.png)

### <a name="complete-onboarding-and-check-status"></a>オンボーディングとチェックの状態を完了する

1. Android 上の Defender for Endpoint がデバイスにインストールされた後、アプリ アイコンが表示されます。

    ![モバイル デバイスのアイコン](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. Microsoft Defender for Endpoint アプリ アイコンをタップし、画面の指示に従ってアプリのオンボーディングを完了します。 詳細には、Android の Defender for Endpoint で必要な Android アクセス許可のエンド ユーザーによる承諾が含まれます。

3. オンボードが正常に完了すると、デバイスはデバイス の [デバイス] リストに表示Microsoft Defender セキュリティ センター。

    ![Defender for Endpoint ポータルのデバイスのイメージ](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>登録済みデバイスEnterprise Android に展開する

Android 上のエンドポイントの Defender は、登録Enterprise Android をサポートします。

Intune でサポートされる登録オプションの詳細については、「登録オプション」 [を参照してください](/mem/intune/enrollment/android-enroll)。

**現在、仕事用プロファイルと企業所有の完全に管理されたユーザー デバイス登録を持つ個人所有のデバイスは、展開のためにサポートされています。**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>Android に Microsoft Defender for Endpoint を Managed Google Play アプリとして追加する

管理された Google Play に Microsoft Defender for Endpoint アプリを追加するには、以下の手順に従います。

1. 管理 [Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)アプリの Androidアプリの追加] に移動 \>  \> **し、[** 管理された Google Play アプリ]**を選択します**。

    > [!div class="mx-imgBorder"]
    > ![管理センター Microsoft エンドポイント マネージャー Google play の画像](images/579ff59f31f599414cedf63051628b2e.png)

2. その後読み込まれる管理された Google Play ページで、検索ボックスに移動し **、Microsoft Defender を参照します。** 検索では、Managed Google Play に Microsoft Defender for Endpoint アプリが表示されます。 アプリの検索結果から Microsoft Defender for Endpoint アプリをクリックします。

    ![管理センター Microsoft エンドポイント マネージャーアプリ検索の画像](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. 次に表示される [アプリの説明] ページで、Defender for Endpoint でアプリの詳細を確認できる必要があります。 ページの情報を確認し、[承認] を **選択します**。

    > [!div class="mx-imgBorder"]
    > ![Managed Google Play のスクリーンショット](images/07e6d4119f265037e3b80a20a73b856f.png)

4. Defender for Endpoint が動作するために取得するアクセス許可が表示されます。 それらを確認し、[承認] を **選択します**。

    ![Defender for Endpoint プレビュー アプリ承認のスクリーンショット](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. [承認の設定] ページが表示されます。 このページでは、Android 上の Defender for Endpoint が要求する可能性がある新しいアプリのアクセス許可を処理する設定が確認されます。 選択肢を確認し、希望するオプションを選択します。 **[完了]** を選択します。

    既定では、[アプリが新しいアクセス許可を要求するときに承認済みの状態を維持する] を *選択します。*

    > [!div class="mx-imgBorder"]
    > ![[通知のイメージ] タブ](images/ffecfdda1c4df14148f1526c22cc0236.png)

6. アクセス許可処理の選択が行われたら、[同期] を **選択して** Microsoft Defender for Endpoint をアプリの一覧に同期します。

    > [!div class="mx-imgBorder"]
    > ![同期ページのイメージ](images/34e6b9a0dae125d085c84593140180ed.png)

7. 同期は数分で完了します。

    ![Android アプリの画像](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. [Android アプリ **] 画面で** [更新] ボタンを選択すると、Microsoft Defender for Endpoint がアプリの一覧に表示されます。

    > [!div class="mx-imgBorder"]
    > ![Android アプリの一覧の画像](images/fa4ac18a6333335db3775630b8e6b353.png)

9. Defender for Endpoint は、Intune 経由で管理対象デバイスのアプリ構成ポリシーをサポートします。 この機能は、該当する Android アクセス許可を自動付与するために利用できます。そのため、エンド ユーザーは、これらのアクセス許可を受け入れる必要がなされません。

    1. [アプリ **] ページで** 、[アプリ構成ポリシー>に移動し、[> **デバイス>追加する] に移動します**。

       ![管理センター android Microsoft エンドポイント マネージャーデバイスのイメージ](images/android-mem.png)

    1. [アプリ構成 **ポリシーの作成] ページ** で、次の詳細を入力します。

        - 名前: エンドポイント用 Microsoft Defender。
        - [**プラットフォームとして Android Enterprise]** を選択します。
        - [プロファイル **の種類] として [作業プロファイル** のみ] を選択します。
        - [アプリ **の選択] を** クリックし **、[Microsoft Defender ATP] を選択** し **、[OK] を選択し、[次** へ] を **選択します**。

        > [!div class="mx-imgBorder"]
        > ![アプリ構成ポリシーの作成ページのイメージ](images/android-create-app.png)

    1. [アクセス **設定]** ページで、[アクセス許可] セクションの [追加] をクリックして、サポートされているアクセス許可の一覧を表示します。 [アクセス許可の追加] セクションで、次のアクセス許可を選択します。

       - 外部ストレージ (読み取り)
       - 外部ストレージ (書き込み)

       次に **[OK]** を選択します。

       > [!div class="mx-imgBorder"]
      > ![Android 作成アプリ構成ポリシーのイメージ](images/android-create-app-config.png)

    1. これで、両方のアクセス許可が一覧表示され、[アクセス許可の状態] ドロップダウンで [自動入力] を選択し、[次へ] を選択して、両方を自動入力 **できます**。

       > [!div class="mx-imgBorder"]
       > ![Android 自動付与アプリ構成ポリシーの作成のイメージ](images/android-auto-grant.png)

    1. [割 **り当て]** ページで、このアプリ構成ポリシーを割り当てるユーザー グループを選択します。 [グループ **の選択] をクリック** して、該当するグループを含め、選択し、[次へ] を **選択します**。  ここで選択したグループは、通常、エンドポイント Android アプリ用 Microsoft Defender を割り当てるのと同じグループです。

       > [!div class="mx-imgBorder"]
       > ![アプリ構成ポリシーの作成のイメージ](images/android-select-group.png)

    1. 次に **表示される [確認と作成** ] ページで、すべての情報を確認し、[作成] を **選択します**。 <br>

        ストレージアクセス許可を自動指定する Defender for Endpoint のアプリ構成ポリシーが、選択したユーザー グループに割り当てられます。

        > [!div class="mx-imgBorder"]
        > ![Android レビュー作成アプリ構成ポリシーのイメージ](images/android-review-create.png)

10. [**プロパティの割り当ての** 編集] の一覧で [Microsoft Defender ATP \>  \> **アプリ] を** \> **選択します**。

    ![アプリの一覧の画像](images/mda-properties.png)

11. アプリを必須アプリとして *ユーザー* グループに割り当てる。 デバイスの次回の同期中に、アプリを使用して作業プロファイルに自動的ポータル サイトされます。 この割り当ては、[必須]セクション [グループの追加] に移動し、ユーザー グループを選択して [選択 \> ] をクリックすることで **実行できます**。

    > [!div class="mx-imgBorder"]
    > ![アプリケーションの編集ページのイメージ](images/ea06643280075f16265a596fb9a96042.png)

12. [アプリケーション **の編集] ページ** で、上記で入力した情報を確認します。 次に、[ **確認] + [保存] の** 順に選択し **、[保存] を** 再度選択して割り当てを開始します。

### <a name="auto-setup-of-always-on-vpn"></a>Always-on VPN の自動セットアップ

Defender for Endpoint は、Intune 経由で管理対象デバイスのデバイス構成ポリシーをサポートします。 この機能は、Android Enterprise 登録済みデバイス上の **Always-on VPN** の自動セットアップに利用できます。そのため、エンド ユーザーはオンボーディング中に VPN サービスをセットアップする必要がなされません。

1. [**デバイス] で**、[**構成プロファイル] [**  >  **プロファイル プラットフォームの**  >    >  **作成] Android Enterprise**

   デバイス **登録の種類に** 基づいて、[次のいずれかのデバイス制限] を選択します。
   - **完全管理、専用、および作業Corporate-Ownedプロファイル**
   - **個人所有の作業プロファイル**

   [**作成**] を選択します。

   > ![デバイス構成プロファイルのイメージ作成](images/1autosetupofvpn.png)

2. **構成設定** 構成プロファイル **を一** 意 **に識別するための名前** と説明を指定します。

   > ![デバイス構成プロファイルのイメージ 名前と説明](images/2autosetupofvpn.png)

3. [接続 **] を選択し** 、VPN を構成します。
   - **Always-on VPN を有効にする**

   作業プロファイルで VPN クライアントをセットアップして、可能な限り VPN に自動的に接続して再接続します。 特定のデバイス上の常時接続 VPN 用に構成できる VPN クライアントは 1 つのみです。そのため、1 つのデバイスに展開する常時接続 VPN ポリシーは 1 つ以下にしてください。

   - [VPN **クライアントの** カスタム] ドロップダウン リストを選択する

   この場合のカスタム VPN は Defender for Endpoint VPN で、Web Protection 機能を提供するために使用されます。

   > [!NOTE]
   > この VPN の自動セットアップを機能するには、Microsoft Defender for Endpoint アプリをユーザーのデバイスにインストールする必要があります。

   - Google Play **ストアで** Microsoft Defender for Endpoint アプリのパッケージ ID を入力します。 Defender アプリの URL <https://play.google.com/store/apps/details?id=com.microsoft.scmx> の場合、パッケージ ID は **com.microsoft.scmx です**。
   - **ロックダウン モード** 構成されていません (既定)

     ![デバイス構成プロファイルのイメージで Always-on VPN を有効にする](images/3autosetupofvpn.png)

4. **割り当て**

   [割 **り当て]** ページで、このアプリ構成ポリシーを割り当てる   ユーザー グループを選択します。 [グループ **の選択]** をクリックして、該当するグループを含め、選択し、[次へ] を **クリックします**。 ここで選択したグループは、通常、エンドポイント Android アプリ用 Microsoft Defender を割り当てるのと同じグループです。

     ![デバイス構成プロファイル割り当てのイメージ](images/4autosetupofvpn.png)

5. 次に **表示される [確認と作成** ] ページで、すべての情報を確認し、[作成] を **選択します**。
これで、デバイス構成プロファイルが選択したユーザー グループに割り当てられます。

    ![デバイス構成プロファイルのイメージ レビューと作成](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a>オンボーディングとチェックの状態を完了する

1. [デバイスのインストール状態] をクリックして、Android 上の Microsoft Defender for Endpoint のインストール状態 **を確認します**。 デバイスがここに表示されるのを確認します。

    > [!div class="mx-imgBorder"]
    > ![デバイスのインストール状態のイメージ](images/900c0197aa59f9b7abd762ab2b32e80c.png)

2. デバイスで、作業プロファイルにアクセスしてオンボーディングの状態を **検証できます**。 Defender for Endpoint が使用可能で、個人用所有のデバイスに仕事用プロファイルが登録 **されているのを確認します**。  企業所有の完全に管理されたユーザー デバイスに登録されている場合は、デバイス上に 1 つのプロファイルが作成され、Defender for Endpoint が使用可能なと確認できます。

    ![モバイル デバイスのアプリのイメージ](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. アプリがインストールされると、アプリを開いてアクセス許可を受け入れ、オンボーディングが成功する必要があります。

    ![Microsoft Defender for Endpoint アプリを使用したモバイル デバイスのイメージ](images/mda-devicesafe.png)

4. この段階では、デバイスは Android 上の Defender for Endpoint に正常にオンボードされます。 [デバイス] ページに移動 [して](https://securitycenter.microsoft.com)、Microsoft Defender セキュリティ センターを **確認できます。**

    ![エンドポイント ポータル用 Microsoft Defender のイメージ](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="related-topics"></a>関連項目

- [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
- [Android 機能用に Microsoft Defender for Endpoint を構成する](android-configure.md)
