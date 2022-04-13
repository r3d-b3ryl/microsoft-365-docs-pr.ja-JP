---
title: Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開
description: Microsoft Intuneを使用して Android にMicrosoft Defender for Endpointをデプロイする方法について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, インストール, デプロイ, アンインストール,
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
ms.openlocfilehash: 461664cc72486a49e5b7bd9be44235559409adff
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64825258"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a>Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Intune ポータル サイト登録済みデバイスに Android 上に Defender for Endpoint を展開する方法について説明します。 デバイス登録のIntuneの詳細については、「[デバイスの登録」を参照してください](/mem/intune/user-help/enroll-device-android-company-portal)。

> [!NOTE]
> **Android 上の Defender for Endpoint が [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) で利用できるようになりました**
>
> Intuneから Google Play に接続して、デバイス管理者と Android Enterprise登録モードに Defender for Endpoint アプリを展開できます。
>
> アプリの更新は Google Play によって自動的に行われます。

## <a name="deploy-on-device-administrator-enrolled-devices"></a>デバイス管理者が登録したデバイスに展開する

**Intune ポータル サイト上の Android 上に Defender for Endpoint を展開する - デバイス管理者が登録したデバイス**

Intune ポータル サイト - デバイス管理者が登録したデバイスで Android に Defender for Endpoint を展開する方法について説明します。

### <a name="add-as-android-store-app"></a>Android ストア アプリとして追加する

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、[Apps **Android Apps** **Add Android store app] (Android ストア アプリの追加\>****)** \> に移動し、[選択] を **選択します**。\>

   :::image type="content" source="images/mda-addandroidstoreapp.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの [Android ストア アプリケーションの追加] ウィンドウ"  lightbox="images/mda-addandroidstoreapp.png":::

2. [ **アプリの追加]** ページと [ *アプリ情報* ] セクションで次のように入力します。

   - **[名前]**
   - **説明**
   - **Microsoft としてPublisher**。
   - **アプリ ストア URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)

   その他のフィールドは省略可能です。 **[次へ]** を選択します。

   :::image type="content" source="images/mda-addappinfo.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルでアプリケーションの発行元と URL の情報を表示する [アプリの追加] ページ" lightbox="images/mda-addappinfo.png":::

3. [*割り当て*] セクションの [**必須**] セクションに移動し、[**グループの追加]** を選択します。 その後、Android アプリで Defender for Endpoint をターゲットにするユーザー グループを選択できます。 [ **選択] を選択** し、[ **次へ**] を選択します。

    > [!NOTE]
    > 選択したユーザー グループは、Intune登録されたユーザーで構成する必要があります。
    >
    > :::image type="content" source="images/363bf30f7d69a94db578e8af0ddd044b.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの [アプリの追加] ページの [グループの追加] ウィンドウ" lightbox="images/363bf30f7d69a94db578e8af0ddd044b.png":::

4. [ **確認と作成** ] セクションで、入力されたすべての情報が正しいことを確認し、[ **作成**] を選択します。

    しばらくすると、Defender for Endpoint アプリが正常に作成され、ページの右上隅に通知が表示されます。

    :::image type="content" source="images/86cbe56f88bb6e93e9c63303397fc24f.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルのアプリケーションの状態ウィンドウ" lightbox="images/86cbe56f88bb6e93e9c63303397fc24f.png":::

5. 表示されるアプリ情報ページの [ **モニター** ] セクションで、[ **デバイスのインストール状態** ] を選択して、デバイスのインストールが正常に完了したことを確認します。

    :::image type="content" source="images/513cf5d59eaaef5d2b5bc122715b5844.png" alt-text="Microsoft Defender 365 ポータルの [デバイスのインストール状態] ページ" lightbox="images/513cf5d59eaaef5d2b5bc122715b5844.png":::

### <a name="complete-onboarding-and-check-status"></a>オンボードを完了し、状態を確認する

1. Android 上の Defender for Endpoint がデバイスにインストールされると、アプリ アイコンが表示されます。

   :::image type="content" source="images/7cf9311ad676ec5142002a4d0c2323ca.jpg" alt-text="[検索] ウィンドウに表示される Microsoft Defender ATP アイコン" lightbox="images/7cf9311ad676ec5142002a4d0c2323ca.jpg":::

2. Microsoft Defender for Endpointアプリアイコンをタップし、画面の指示に従ってアプリのオンボードを完了します。 詳細には、Android 上の Defender for Endpoint に必要な Android アクセス許可のエンドユーザー受け入れが含まれます。

3. オンボードに成功すると、Microsoft 365 Defender ポータルの [デバイス] 一覧にデバイスが表示されます。

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Microsoft Defender for Endpoint ポータルのデバイス"  lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>Android Enterprise登録済みデバイスにデプロイする

Android 上の Defender for Endpoint では、Android Enterprise登録済みデバイスがサポートされます。

Intuneでサポートされている登録オプションの詳細については、「[登録オプション](/mem/intune/enrollment/android-enroll)」を参照してください。

**現在、仕事用プロファイルを持つ個人所有のデバイスと、企業所有のフル マネージド ユーザー デバイスの登録が展開でサポートされています。**

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a>Android でマネージド Google Play アプリとしてMicrosoft Defender for Endpointを追加する

次の手順に従って、マネージド Google Play にアプリMicrosoft Defender for Endpoint追加します。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、[**Apps** \> **Android Apps** \> **の追加**] に移動し、[**マネージド Google Play アプリ**] を選択します。

    :::image type="content" source="images/579ff59f31f599414cedf63051628b2e.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルのアプリケーション追加ウィンドウ" lightbox="images/579ff59f31f599414cedf63051628b2e.png":::

2. その後読み込まれるマネージド Google Play ページで、検索ボックスに移動し、次のように入力 `Microsoft Defender`します。 検索では、Managed Google Play にMicrosoft Defender for Endpointアプリが表示されます。 アプリの検索結果からMicrosoft Defender for Endpointアプリをクリックします。

    :::image type="content" source="images/0f79cb37900b57c3e2bb0effad1c19cb.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの [マネージド Google Play] ページ" lightbox="images/0f79cb37900b57c3e2bb0effad1c19cb.png":::

3. 次に表示される [アプリの説明] ページでは、Defender for Endpoint でアプリの詳細を確認できます。 ページの情報を確認し、[ **承認**] を選択します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/07e6d4119f265037e3b80a20a73b856f.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの Managed Google Play のページ" lightbox="images/07e6d4119f265037e3b80a20a73b856f.png":::
      

4. Defender for Endpoint が動作するために取得するアクセス許可が表示されます。 それらを確認し、[ **承認**] を選択します。

    :::image type="content" source="images/206b3d954f06cc58b3466fb7a0bd9f74.png" alt-text="Microsoft Defender 365 ポータルのアクセス許可の承認ページ" lightbox="images/206b3d954f06cc58b3466fb7a0bd9f74.png":::

5. [承認設定] ページが表示されます。 このページでは、Android 上の Defender for Endpoint が求める可能性がある新しいアプリのアクセス許可を処理するためのユーザー設定が確認されます。 選択肢を確認し、好みのオプションを選択します。 [**完了**] を選択します。

    既定では、アプリが **新しいアクセス許可を要求したときに**、マネージド Google Play によって [承認を保持] が選択されます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ffecfdda1c4df14148f1526c22cc0236.png" alt-text=" Microsoft Defender 365 ポータルの [承認設定の構成完了] ページ" lightbox="images/ffecfdda1c4df14148f1526c22cc0236.png":::

6. 選択を処理するアクセス許可が作成されたら、[**同期**] を選択してアプリの一覧Microsoft Defender for Endpoint同期します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/34e6b9a0dae125d085c84593140180ed.png" alt-text="Microsoft Defender 365 ポータルの [同期] ウィンドウ" lightbox="images/34e6b9a0dae125d085c84593140180ed.png":::

7. 同期は数分で完了します。

    :::image type="content" source="images/9fc07ffc150171f169dc6e57fe6f1c74.png" alt-text="Microsoft Defender 365 ポータルの Android アプリ ページのアプリケーション同期状態ウィンドウ"  lightbox="images/9fc07ffc150171f169dc6e57fe6f1c74.png":::

8. Android アプリ画面で **[更新**] ボタンを選択すると、アプリの一覧にMicrosoft Defender for Endpointが表示されます。

    :::image type="content" source="images/fa4ac18a6333335db3775630b8e6b353.png" alt-text="同期されたアプリケーションを表示するページ" lightbox="images/fa4ac18a6333335db3775630b8e6b353.png":::

9. Defender for Endpoint では、Intune経由でマネージド デバイスのアプリ構成ポリシーがサポートされます。 この機能を利用して、Defender のさまざまな構成を選択できます。

    1. [ **アプリ]** ページで、[ **ポリシー>アプリ構成ポリシー] > [管理対象デバイス>追加] に移動します**。

       :::image type="content" source="images/android-mem.png" alt-text="Microsoft エンドポイント マネージャー管理センター ポータルの [アプリ構成ポリシー] ウィンドウ" lightbox="images/android-mem.png":::

    1. [ **アプリ構成ポリシーの作成** ] ページで、次の詳細を入力します。

        - 名前: Microsoft Defender for Endpoint。
        - プラットフォームとして **Android Enterprise** を選択します。
        - [プロファイルの種類 **] として [仕事用プロファイルのみ** ] を選択します。
        - [**アプリの選択]** をクリックし、**Microsoft Defender ATP** を選択 **して[OK]、[****次へ**] の順に選択します。

        :::image type="content" source="images/android-create-app.png" alt-text=" [関連付けられているアプリの詳細] ウィンドウ" lightbox="images/android-create-app.png":::

    1. **[設定**] ページの [**構成設定]** セクションに移動し、[構成設定] 形式で **[構成デザイナーの使用**] を選択します。 

       :::image type="content" alt-text="Android のアプリ構成ポリシーを作成するイメージ。" source="images/configurationformat.png" lightbox="images/configurationformat.png":::

    1. [ **追加]** をクリックして、サポートされている構成の一覧を表示します。 必要な構成を選択し、[ **OK**] をクリックします。

       :::image type="content" alt-text="Android の構成ポリシーを選択するイメージ。" source="images/selectconfigurations.png" lightbox="images/selectconfigurations.png":::


    1. 選択したすべての構成が一覧表示されます。 必要に応じて構成値を変更し、[ **次へ**] を選択できます。
        
        :::image type="content" alt-text="選択した構成ポリシーのイメージ。" source="images/listedconfigurations.png" lightbox="images/listedconfigurations.png":::
       

    1. [ **割り当て** ] ページで、このアプリ構成ポリシーを割り当てるユーザー グループを選択します。 [ **含めるグループの選択]** をクリックし、該当するグループを選択し、[ **次へ**] を選択します。 ここで選択したグループは、通常、Android アプリMicrosoft Defender for Endpoint割り当てるのと同じグループです。

       :::image type="content" source="images/android-select-group.png" alt-text="[選択したグループ] ウィンドウ" lightbox="images/android-select-group.png":::

    1. 次に表示される **[確認と作成]** ページで、すべての情報を確認し、[ **作成**] を選択します。

        ストレージアクセス許可を自動で作成する Defender for Endpoint のアプリ構成ポリシーが、選択したユーザー グループに割り当てられます。

        > [!div class="mx-imgBorder"]
        > :::image type="content" source="images/android-review-create.png" alt-text="[アプリ構成ポリシーの作成] ページの [確認と作成] タブ" lightbox="images/android-review-create.png":::

10. **プロパティ** \> **の割り当ての** 編集の一覧\>で **Microsoft Defender ATP** アプリを\>選択 **します**。

   :::image type="content" source="images/mda-properties.png" alt-text="[プロパティ] ページの [編集] オプション" lightbox="images/mda-properties.png":::

11. アプリを *必須* アプリとしてユーザー グループに割り当てます。 これは、ポータル サイト アプリを介してデバイスを次回同期するときに *、仕事用プロファイル* に自動的にインストールされます。 この割り当ては、[ *必須* ] セクション \> [ **グループの追加]** に移動し、ユーザー グループを選択して **[選択**] をクリックすることで実行できます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ea06643280075f16265a596fb9a96042.png" alt-text="[アプリケーションの編集] ページ" lightbox="images/ea06643280075f16265a596fb9a96042.png":::

12. [ **アプリケーションの編集]** ページで、上記で入力したすべての情報を確認します。 次に、[ **校閲と保存]** を選択し、もう一度 **[保存] を** 選択して割り当てを開始します。

### <a name="auto-setup-of-always-on-vpn"></a>Always-on VPN の自動セットアップ

Defender for Endpoint では、Intune経由でマネージド デバイスのデバイス構成ポリシーがサポートされます。 この機能は、Android Enterprise登録済みデバイスでの **Always-on VPN の自動セットアップ** に利用できるため、エンド ユーザーはオンボード中に VPN サービスを設定する必要はありません。

1. **[デバイス**] で、[**構成プロファイル**\>] [プロファイル **プラットフォーム** \> **Android Enterprise****の**\>作成] を選択します。

   デバイス登録の種類に基づいて、次のいずれかの下にある [デバイス **の制限** ] を選択します。
   - **フル マネージド、専用、Corporate-Owned作業プロファイル**
   - **個人所有の仕事用プロファイル**

   **[作成]** を選択します。

   :::image type="content" source="images/1autosetupofvpn.png" alt-text="[ポリシー] ウィンドウの [構成プロファイル] メニュー項目" lightbox="images/1autosetupofvpn.png":::

2. **構成設定** 構成プロファイルを一意に識別するための **名前** と **説明** を指定します。

   :::image type="content" source="images/2autosetupofvpn.png" alt-text="[基本] ウィンドウの [デバイス構成プロファイル名] フィールドと [説明] フィールド" lightbox="images/2autosetupofvpn.png":::

3. [ **接続** ] を選択し、VPN を構成します。

   - **Always-on VPN を** 有効にする

     仕事用プロファイルで VPN クライアントを設定し、可能な限り VPN に自動的に接続して再接続します。 特定のデバイスで常時オン VPN 用に構成できる VPN クライアントは 1 つだけです。そのため、1 つのデバイスに 1 つの常時オン VPN ポリシーを 1 つ以上デプロイしないようにしてください。

   - [VPN クライアントの **カスタム** ] ドロップダウン リストを選択する

     この場合のカスタム VPN は、Web 保護機能を提供するために使用される Defender for Endpoint VPN です。

     > [!NOTE]
     > この VPN の自動セットアップを機能させるには、Microsoft Defender for Endpoint アプリをユーザーのデバイスにインストールする必要があります。

   - Google Play ストアでMicrosoft Defender for Endpoint アプリの **パッケージ ID を** 入力します。 Defender アプリ URL <https://play.google.com/store/apps/details?id=com.microsoft.scmx>の場合、パッケージ ID は **com.microsoft.scmx です**

   - **ロックダウン モード** 未構成 (既定)

     :::image type="content" source="images/3autosetupofvpn.png" alt-text="[構成設定] タブの [接続] ウィンドウ" lightbox="images/3autosetupofvpn.png":::

4. **割り当て**

   [ **割り当て** ] ページで、このアプリ構成ポリシーを割り当てるユーザー グループを選択します。 [含める **グループの選択]** を選択し、該当するグループを選択して、[ **次へ**] を選択します。 ここで選択したグループは、通常、Android アプリMicrosoft Defender for Endpoint割り当てるのと同じグループです。

   :::image type="content" source="images/4autosetupofvpn.png" alt-text="[デバイスの制限] の [デバイス構成プロファイルの割り当て] ウィンドウ" lightbox="images/4autosetupofvpn.png":::

5. 次に表示される **[確認と作成]** ページで、すべての情報を確認し、[ **作成**] を選択します。
これで、デバイス構成プロファイルが選択したユーザー グループに割り当てられます。

   :::image type="content" source="images/5autosetupofvpn.png" alt-text="デバイス構成プロファイル 's provision for Review + create" lightbox="images/5autosetupofvpn.png":::

## <a name="check-status-and-complete-onboarding"></a>状態を確認し、オンボードを完了する

1. [デバイスのインストール状態] をクリックして、Android でのMicrosoft Defender for Endpointの **インストール状態** を確認します。 デバイスがここに表示されていることを確認します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/900c0197aa59f9b7abd762ab2b32e80c.png" alt-text="デバイスのインストール状態ウィンドウ" lightbox="images/900c0197aa59f9b7abd762ab2b32e80c.png":::

2. デバイスでは、 **作業プロファイル** に移動してオンボード状態を検証できます。 Defender for Endpoint が使用可能であり、 **仕事用プロファイルを持つ個人用デバイスに** 登録されていることを確認します。 **企業所有のフル マネージド ユーザー デバイス** に登録されている場合は、デバイスに 1 つのプロファイルがあり、Defender for Endpoint が使用可能であることを確認できます。

    :::image type="content" source="images/c2e647fc8fa31c4f2349c76f2497bc0e.png" alt-text="アプリケーション表示ウィンドウ" lightbox="images/c2e647fc8fa31c4f2349c76f2497bc0e.png":::

3. アプリがインストールされたら、アプリを開き、アクセス許可を受け入れてから、オンボードに成功します。

    :::image type="content" source="images/MDE_new.png" alt-text="モバイル デバイス上のMicrosoft Defender for Endpoint アプリケーションの表示" lightbox="images/MDE_new.png":::

4. この段階で、デバイスは Android 上の Defender for Endpoint に正常にオンボードされます。 これを確認するには、[Microsoft 365 Defender ポータル](https://security.microsoft.com)で **[デバイス インベントリ]** ページに移動します。

    :::image type="content" source="images/9fe378a1dce0f143005c3aa53d8c4f51.png" alt-text="Microsoft Defender for Endpoint ポータル" lightbox="images/9fe378a1dce0f143005c3aa53d8c4f51.png":::

## <a name="related-topics"></a>関連項目

- [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
- [Android 機能用に Microsoft Defender for Endpoint を構成する](android-configure.md)
