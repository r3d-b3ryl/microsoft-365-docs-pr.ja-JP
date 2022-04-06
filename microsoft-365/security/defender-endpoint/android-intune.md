---
title: Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開
description: Microsoft Defender for Endpoint を Android に展開する方法について説明します。Microsoft Intune
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mde, android, installation, deploy, uninstallation,
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aab50764a13a671cdeb10902744456dcbc1cb48f
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471409"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

登録されているデバイスで Android に Defender for Endpoint を展開するIntune ポータル サイト説明します。 Intune デバイスの登録の詳細については、「デバイスの登録 [」を参照してください](/mem/intune/user-help/enroll-device-android-company-portal)。

> [!NOTE]
> **Android 上のエンドポイントの Defender が [Google Play で利用できる](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**
>
> Intune から Google Play に接続して、デバイス管理者と Android ユーザー登録モードで Defender for Endpoint アプリEnterprise展開できます。
>
> アプリの更新は、Google Play 経由で自動的に行います。

## <a name="deploy-on-device-administrator-enrolled-devices"></a>デバイス管理者が登録したデバイスに展開する

**デバイス管理者が登録したデバイスで Android Intune ポータル サイト Defender for Endpoint を展開する**

Android 上の Android に Defender for Endpoint を展開するIntune ポータル サイトデバイス管理者が登録したデバイスについて説明します。

### <a name="add-as-android-store-app"></a>Android ストア アプリとして追加する

1. 管理 [Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)アプリ] \> **[Android アプリ] [Android ストア** \> **\>** アプリの追加] に移動し、[選択] を選択 **します**。

   :::image type="content" source="images/mda-addandroidstoreapp.png" alt-text="管理センター ポータルの [Android ストア アプリケーションの追加Microsoft エンドポイント マネージャーウィンドウ"  lightbox="images/mda-addandroidstoreapp.png":::

2. [アプリの **追加] ページで** 、[アプリ情報] *セクションに次の情報* を入力します。

   - **名前**
   - **説明**
   - **Publisher** Microsoft として使用します。
   - **アプリ ストア URL as** https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play ストア URL)

   その他のフィールドはオプションです。 **[次へ]** を選択します。

   :::image type="content" source="images/mda-addappinfo.png" alt-text="[アプリの追加] ページで、アプリケーションの発行元と URL 情報を管理センター ポータルMicrosoft エンドポイント マネージャー表示します。" lightbox="images/mda-addappinfo.png":::

3. [割り *当て] セクション* で、[必須] セクションに移動 **し** 、[グループの追加] **を選択します。** その後、Android アプリで Defender for Endpoint をターゲットとするユーザー グループを選択できます。 [選択 **] と [** 次へ] の順 **に選択します**。

    > [!NOTE]
    > 選択したユーザー グループは、Intune に登録されたユーザーで構成する必要があります。
    >
    > :::image type="content" source="images/363bf30f7d69a94db578e8af0ddd044b.png" alt-text="管理センター ポータルの [アプリの追加] ページの [グループMicrosoft エンドポイント マネージャー追加] ウィンドウ" lightbox="images/363bf30f7d69a94db578e8af0ddd044b.png":::

4. [レビュー **+ 作成] セクション** で、入力した情報が正しいか確認し、[作成] を選択 **します**。

    しばらくすると、Defender for Endpoint アプリが正常に作成され、ページの右上隅に通知が表示されます。

    :::image type="content" source="images/86cbe56f88bb6e93e9c63303397fc24f.png" alt-text="管理センター ポータルのアプリケーションMicrosoft エンドポイント マネージャーウィンドウ" lightbox="images/86cbe56f88bb6e93e9c63303397fc24f.png":::

5. 表示されるアプリ情報ページの [モニター] セクションで、[デバイスのインストール状態] を選択して、デバイスのインストールが正常に完了したと確認します。

    :::image type="content" source="images/513cf5d59eaaef5d2b5bc122715b5844.png" alt-text="Microsoft Defender 365 ポータルの [デバイスのインストール状態] ページ" lightbox="images/513cf5d59eaaef5d2b5bc122715b5844.png":::

### <a name="complete-onboarding-and-check-status"></a>オンボーディングとチェックの状態を完了する

1. Android 上の Defender for Endpoint がデバイスにインストールされた後、アプリ アイコンが表示されます。

   :::image type="content" source="images/7cf9311ad676ec5142002a4d0c2323ca.jpg" alt-text="検索ウィンドウに表示される Microsoft Defender ATP アイコン" lightbox="images/7cf9311ad676ec5142002a4d0c2323ca.jpg":::

2. Microsoft Defender for Endpoint アプリ アイコンをタップし、画面の指示に従ってアプリのオンボーディングを完了します。 詳細には、Android の Defender for Endpoint で必要な Android アクセス許可のエンド ユーザーによる承諾が含まれます。

3. オンボードが成功すると、デバイスはポータルの [デバイス] リストに表示Microsoft 365 Defenderされます。

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Microsoft Defender for Endpoint ポータルのデバイス"  lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>登録済みデバイスEnterprise Android に展開する

Android 上のエンドポイントの Defender は、Android Enterpriseデバイスをサポートします。

Intune でサポートされる登録オプションの詳細については、「登録オプション」 [を参照してください](/mem/intune/enrollment/android-enroll)。

**現在、仕事用プロファイルと企業所有の完全に管理されたユーザー デバイス登録を持つ個人所有のデバイスは、展開のためにサポートされています。**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>Android に Microsoft Defender for Endpoint を Managed Google Play アプリとして追加する

管理された Google Play に Microsoft Defender for Endpoint アプリを追加するには、以下の手順に従います。

1. 管理 [Microsoft エンドポイント マネージャーで、[](https://go.microsoft.com/fwlink/?linkid=2109431)  \> **アプリの Android アプリ**\>の追加] に移動 **し、[****管理された Google Play アプリ] を選択します**。

    :::image type="content" source="images/579ff59f31f599414cedf63051628b2e.png" alt-text="管理センター ポータルのアプリケーションMicrosoft エンドポイント マネージャーウィンドウ" lightbox="images/579ff59f31f599414cedf63051628b2e.png":::

2. その後読み込まれる管理された Google Play ページで、検索ボックスに移動してと入力します `Microsoft Defender`。 検索では、Managed Google Play に Microsoft Defender for Endpoint アプリが表示されます。 アプリの検索結果から Microsoft Defender for Endpoint アプリをクリックします。

    :::image type="content" source="images/0f79cb37900b57c3e2bb0effad1c19cb.png" alt-text="管理センター ポータルの [管理Microsoft エンドポイント マネージャー Google Play] ページ" lightbox="images/0f79cb37900b57c3e2bb0effad1c19cb.png":::

3. 次に表示される [アプリの説明] ページで、Defender for Endpoint でアプリの詳細を確認できる必要があります。 ページの情報を確認し、[承認] を **選択します**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/07e6d4119f265037e3b80a20a73b856f.png" alt-text="管理センター ポータルの [Managed Google Play] Microsoft エンドポイント マネージャーページ" lightbox="images/07e6d4119f265037e3b80a20a73b856f.png":::
      

4. Defender for Endpoint が動作するために取得するアクセス許可が表示されます。 それらを確認し、[承認] を **選択します**。

    :::image type="content" source="images/206b3d954f06cc58b3466fb7a0bd9f74.png" alt-text="Microsoft Defender 365 ポータルの [アクセス許可の承認] ページ" lightbox="images/206b3d954f06cc58b3466fb7a0bd9f74.png":::

5. [承認の設定] ページが表示されます。 このページでは、Android 上の Defender for Endpoint が要求する可能性がある新しいアプリのアクセス許可を処理する設定が確認されます。 選択肢を確認し、希望するオプションを選択します。 [**完了**] を選択します。

    既定では、管理された Google Play は、アプリが新しいアクセス許可を要求するときに [承認された状態に保つ **] を選択します**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ffecfdda1c4df14148f1526c22cc0236.png" alt-text=" Microsoft Defender 365 ポータルの [承認設定の構成完了] ページ" lightbox="images/ffecfdda1c4df14148f1526c22cc0236.png":::

6. アクセス許可処理の選択が行われたら、[同期] を **選択して Microsoft** Defender for Endpoint をアプリの一覧に同期します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/34e6b9a0dae125d085c84593140180ed.png" alt-text="Microsoft Defender 365 ポータルの [同期] ウィンドウ" lightbox="images/34e6b9a0dae125d085c84593140180ed.png":::

7. 同期は数分で完了します。

    :::image type="content" source="images/9fc07ffc150171f169dc6e57fe6f1c74.png" alt-text="Microsoft Defender 365 ポータルの [Android アプリ] ページのアプリケーション同期状態ウィンドウ"  lightbox="images/9fc07ffc150171f169dc6e57fe6f1c74.png":::

8. [Android アプリ **] 画面で** [更新] ボタンを選択すると、Microsoft Defender for Endpoint がアプリの一覧に表示されます。

    :::image type="content" source="images/fa4ac18a6333335db3775630b8e6b353.png" alt-text="同期されたアプリケーションを表示するページ" lightbox="images/fa4ac18a6333335db3775630b8e6b353.png":::

9. Defender for Endpoint は、Intune 経由で管理対象デバイスのアプリ構成ポリシーをサポートします。 この機能は、該当する Android アクセス許可を自動付与するために利用できます。そのため、エンド ユーザーは、これらのアクセス許可を受け入れる必要がなされません。

    1. [アプリ **] ページで** 、[アプリ構成ポリシー>に移動し、[> **デバイス>追加します**。

       :::image type="content" source="images/android-mem.png" alt-text="管理センター ポータルの [アプリ構成ポリシー] Microsoft エンドポイント マネージャーウィンドウ" lightbox="images/android-mem.png":::

    1. [アプリ構成 **ポリシーの作成] ページ** で、次の詳細を入力します。

        - 名前: エンドポイント用 Microsoft Defender。
        - [**プラットフォームとして Android Enterprise**] を選択します。
        - [プロファイル **の種類] として [作業プロファイル** のみ] を選択します。
        - [アプリ **の選択] を** クリックし、[ **Microsoft Defender ATP] を選択** し、[ **OK] を選択し、[次** へ] を **選択します**。

        :::image type="content" source="images/android-create-app.png" alt-text=" [関連付けられたアプリの詳細] ウィンドウ" lightbox="images/android-create-app.png":::

    1. [アクセス **設定**] ページで、[アクセス許可] セクションの [追加] をクリックして、サポートされているアクセス許可の一覧を表示します。 [アクセス許可の追加] セクションで、次のアクセス許可を選択します。

       - 外部ストレージ (読み取り)
       - 外部ストレージ (書き込み)

       次に [**OK**] を選びます。

       :::image type="content" source="images/android-create-app-config.png" alt-text="[アクセス許可の追加] ウィンドウ" lightbox="images/android-create-app-config.png":::

    1. これで、両方のアクセス許可が一覧表示され、[アクセス許可の状態] ドロップダウンで [自動入力] を選択し、[次へ] を選択することで、両方を自動入力 **できます**。

       :::image type="content" source="images/android-auto-grant.png" alt-text="[アクセス許可] 状態ウィンドウ" lightbox="images/android-auto-grant.png":::

    1. [割 **り当て]** ページで、このアプリ構成ポリシーを割り当てるユーザー グループを選択します。 [グループ **の選択] をクリック** して、該当するグループを含め、選択し、[次へ] を選択 **します**。 ここで選択したグループは、通常、エンドポイント Android アプリ用 Microsoft Defender を割り当てるのと同じグループです。

       :::image type="content" source="images/android-select-group.png" alt-text="[選択したグループ] ウィンドウ" lightbox="images/android-select-group.png":::

    1. 次に **表示される [レビューと作成** ] ページで、すべての情報を確認し、[作成] を選択 **します**。

        ストレージアクセス許可を自動指定する Defender for Endpoint のアプリ構成ポリシーが、選択したユーザー グループに割り当てられます。

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="images/android-review-create.png" alt-text="[アプリ構成ポリシーの作成] ページの [レビューと作成] タブ" lightbox="images/android-review-create.png":::

10. [ **プロパティの割り当て** 編集] の一覧で \> **[Microsoft** \> Defender ATP **アプリ] を選択** \> **します**。

   :::image type="content" source="images/mda-properties.png" alt-text="[プロパティ] ページの [編集] オプション" lightbox="images/mda-properties.png":::

11. アプリを必須アプリとして *ユーザー* グループに割り当てる。 デバイスの次回の同期中に、アプリを使用して作業プロファイルに自動的ポータル サイトされます。 この割り当ては、[必須] セクション  [\>グループの追加] に移動し **、ユーザー** グループを選択して [選択] をクリックすることで実行 **できます**。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ea06643280075f16265a596fb9a96042.png" alt-text="[アプリケーションの編集] ページ" lightbox="images/ea06643280075f16265a596fb9a96042.png":::

12. [アプリケーション **の編集] ページ** で、上記で入力した情報を確認します。 次に、[ **確認] + [保存] の** 順に選択し **、[保存] を** 再度選択して割り当てを開始します。

### <a name="auto-setup-of-always-on-vpn"></a>Always-on VPN の自動セットアップ

Defender for Endpoint は、Intune 経由で管理対象デバイスのデバイス構成ポリシーをサポートします。 この機能は、Android Enterprise 登録済みデバイス上の **Always-on VPN** の自動セットアップに利用できます。そのため、エンド ユーザーはオンボーディング中に VPN サービスをセットアップする必要がなされません。

1. [**デバイス] で**、[**構成プロファイル] [** \> **プロファイル プラットフォームの****作成]** \> Android **Enterprise** \>

   デバイス **登録の種類に** 基づいて、[次のいずれかのデバイス制限] を選択します。
   - **完全管理、専用、および作業Corporate-Ownedプロファイル**
   - **個人所有の作業プロファイル**

   **[作成]** を選択します。

   :::image type="content" source="images/1autosetupofvpn.png" alt-text="[ポリシー] ウィンドウの [構成プロファイル] メニュー項目" lightbox="images/1autosetupofvpn.png":::

2. **構成設定** 構成プロファイル **を一** 意に識別するための **名前** と説明を指定します。

   :::image type="content" source="images/2autosetupofvpn.png" alt-text="[基本] ウィンドウのデバイス構成プロファイルの [名前] フィールドと [説明] フィールド" lightbox="images/2autosetupofvpn.png":::

3. [接続 **] を選択し** 、VPN を構成します。

   - **Always-on VPN を有効にする**

     作業プロファイルに VPN クライアントをセットアップして、可能な限り VPN に自動的に接続して再接続します。 特定のデバイス上の常時接続 VPN 用に構成できる VPN クライアントは 1 つのみです。そのため、1 つのデバイスに展開する常時接続 VPN ポリシーは 1 つ以下にしてください。

   - [VPN **クライアントの** カスタム] ドロップダウン リストを選択する

     この場合のカスタム VPN は Defender for Endpoint VPN で、Web Protection 機能を提供するために使用されます。

     > [!NOTE]
     > この VPN の自動セットアップを機能するには、Microsoft Defender for Endpoint アプリをユーザーのデバイスにインストールする必要があります。

   - Google Play **ストアで** Microsoft Defender for Endpoint アプリのパッケージ ID を入力します。 Defender アプリの URL の<https://play.google.com/store/apps/details?id=com.microsoft.scmx>場合、パッケージ ID は **com.microsoft.scmx です**。

   - **ロックダウン モード** 構成されていません (既定)

     :::image type="content" source="images/3autosetupofvpn.png" alt-text="[構成設定] タブの [接続] ウィンドウ" lightbox="images/3autosetupofvpn.png":::

4. **割り当て**

   [割 **り当て]** ページで、このアプリ構成ポリシーを割り当てるユーザー グループを選択します。 [ **グループを選択** して含める] を選択し、該当するグループを選択し、[次へ] を **選択します**。 ここで選択したグループは、通常、エンドポイント Android アプリ用 Microsoft Defender を割り当てるのと同じグループです。

   :::image type="content" source="images/4autosetupofvpn.png" alt-text="[デバイスの制限] の [デバイス構成プロファイルの割り当て] ウィンドウ" lightbox="images/4autosetupofvpn.png":::

5. 次に **表示される [レビューと作成** ] ページで、すべての情報を確認し、[作成] を選択 **します**。
これで、デバイス構成プロファイルが選択したユーザー グループに割り当てられます。

   :::image type="content" source="images/5autosetupofvpn.png" alt-text="デバイス構成プロファイルのレビューと作成の準備" lightbox="images/5autosetupofvpn.png":::

## <a name="check-status-and-complete-onboarding"></a>状態を確認し、オンボーディングを完了する

1. [デバイスのインストール状態] をクリックして、Android 上の Microsoft Defender for Endpoint のインストール状態 **を確認します**。 デバイスがここに表示されるのを確認します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/900c0197aa59f9b7abd762ab2b32e80c.png" alt-text="[デバイスのインストール状態] ウィンドウ" lightbox="images/900c0197aa59f9b7abd762ab2b32e80c.png":::

2. デバイスで、作業プロファイルにアクセスしてオンボーディングの状態を **検証できます**。 Defender for Endpoint が使用可能で、個人用所有のデバイスに仕事用プロファイルが登録 **されているのを確認します**。 企業が所有する完全に管理されたユーザー デバイスに登録している場合は、デバイス上に 1 つのプロファイルが作成され、Defender for Endpoint が使用可能なと確認できます。

    :::image type="content" source="images/c2e647fc8fa31c4f2349c76f2497bc0e.png" alt-text="アプリケーション表示ウィンドウ" lightbox="images/c2e647fc8fa31c4f2349c76f2497bc0e.png":::

3. アプリがインストールされると、アプリを開いてアクセス許可を受け入れ、オンボーディングが成功する必要があります。

    :::image type="content" source="images/MDE_new.png" alt-text="モバイル デバイスでの Microsoft Defender for Endpoint アプリケーションの表示" lightbox="images/MDE_new.png":::

4. この段階では、デバイスは Android 上の Defender for Endpoint に正常にオンボードされます。 デバイス インベントリ ページに移動 [して、Microsoft 365 Defenderポータル](https://security.microsoft.com)でこれを **確認** できます。

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Microsoft Defender for Endpoint ポータル" lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="related-topics"></a>関連項目

- [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
- [Android 機能用に Microsoft Defender for Endpoint を構成する](android-configure.md)
