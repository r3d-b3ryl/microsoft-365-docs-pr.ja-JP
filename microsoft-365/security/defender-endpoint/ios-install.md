---
title: iOSでのMicrosoft Defender for Endpointのアプリ ベースのデプロイ
ms.reviewer: ''
description: アプリを使用してiOSにMicrosoft Defender for Endpointをデプロイする方法について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, アプリ, インストール, デプロイ, アンインストール, intune
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a81f125f9f32a5b4bdafd6d4656699fa17caa82
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65669972"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a>iOSにMicrosoft Defender for Endpointをデプロイする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

このトピックでは、Intune ポータル サイト登録済みデバイス上のiOSに Defender for Endpoint を展開する方法について説明します。 デバイスの登録Intune詳細については、「[IntuneにiOS/iPadOS デバイスを登録する](/mem/intune/enrollment/ios-enroll)」を参照してください。

## <a name="before-you-begin"></a>はじめに

- [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にアクセスできることを確認します。

- iOS登録がユーザーに対して行われることを確認します。 IOSで Defender for Endpoint を使用するには、Defender for Endpoint ライセンスを割り当てる必要があります。 ライセンスを [割り当てる方法については、「ユーザーにライセンスを](/azure/active-directory/users-groups-roles/licensing-groups-assign) 割り当てる」を参照してください。

> [!NOTE]
> iOSのMicrosoft Defender for Endpointは[、Apple App Store](https://aka.ms/mdatpiosappstore)で入手できます。

## <a name="deployment-steps"></a>展開手順

Intune ポータル サイト経由でiOSに Defender for Endpoint をデプロイします。

### <a name="add-ios-store-app"></a>ストア アプリiOS追加する

1. [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、[**アプリ** -> **iOS/iPadOS** -> **の追加** -> ] に移動 **iOSアプリを保存** し、[**選択**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-1.png" alt-text="Microsoft エンドポイント マネージャー 管理 センターの [アプリケーションの追加] タブ" lightbox="images/ios-deploy-1.png":::

1. [**アプリの追加]** ページで、**App Storeの検索を** クリックし、検索バー **に「Microsoft Defender for Endpoint**」と入力します。 検索結果セクションで、*Microsoft Defender for Endpoint* をクリックし、[**選択**] をクリックします。

1. 最小オペレーティング システムとして **iOS 11.0** を選択します。 アプリに関する残りの情報を確認し、[ **次へ**] をクリックします。

1. [ **割り当て** ] セクションの [ **必須** ] セクションに移動し、[ **グループの追加]** を選択します。 その後、IOS アプリで Defender for Endpoint をターゲットにするユーザー グループを選択できます。 **[選択]** をクリックし、[**次へ**] をクリックします。

    > [!NOTE]
    > 選択したユーザー グループは、Intune登録されたユーザーで構成する必要があります。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-2.png" alt-text="Microsoft エンドポイント マネージャー 管理 センターの [グループの追加] タブ" lightbox="images/ios-deploy-2.png":::

1. [ *確認と作成* ] セクションで、入力したすべての情報が正しいことを確認し、[ **作成**] を選択します。 しばらくすると、Defender for Endpoint アプリが正常に作成され、ページの右上隅に通知が表示されます。

1. 表示されるアプリ情報ページの [ **モニター** ] セクションで、[ **デバイスのインストール状態** ] を選択して、デバイスのインストールが正常に完了したことを確認します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-3.png" alt-text="[デバイスのインストールの状態] ページ" lightbox="images/ios-deploy-3.png":::

## <a name="complete-deployment-for-supervised-devices"></a>監視対象デバイスの完全な展開

iOS アプリのMicrosoft Defender for Endpointには、このような種類のデバイス上のプラットフォームによって提供される管理機能の向上に応じて、監視付きiOS/iPadOS デバイスに特化した機能があります。 **また、デバイスにローカル VPN を設定せずに** Web Protection を提供することもできます。 これにより、エンド ユーザーはシームレスなエクスペリエンスを得られますが、フィッシングやその他の Web ベースの攻撃から保護されます。

### <a name="configure-supervised-mode-via-intune"></a>Intuneを使用して監視モードを構成する

次に、App Configuration ポリシーを使用して Defender for Endpoint アプリの監視モードを構成します。

   > [!NOTE]
   > 監視対象デバイスのこのアプリ構成ポリシーは、管理対象デバイスにのみ適用され、ベスト プラクティスとしてすべてのマネージド iOS デバイスを対象にする必要があります。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインし、[**アプリ** \> **の構成ポリシー** \> **の追加**] に移動します。 **[管理対象デバイス**] を選択します。

    > [!div class="mx-imgBorder"]
    > ![Microsoft エンドポイント マネージャー 管理 Center4 の画像。](images/ios-deploy-4.png)

1. [ *アプリ構成ポリシーの作成* ] ページで、次の情報を入力します。
    - ポリシー名
    - プラットフォーム: iOS/iPadOS を選択する
    - 対象アプリ: 一覧から **Microsoft Defender for Endpoint** を選択する

    > [!div class="mx-imgBorder"]
    > ![Microsoft エンドポイント マネージャー 管理 Center5 の画像。](images/ios-deploy-5.png)

1. 次の画面で、 **構成デザイナーを** 形式として使用を選択します。 次のプロパティを指定します。
    - 構成キー: issupervised
    - 値の型:String
    - 構成値: {{issupervised}}

    > [!div class="mx-imgBorder"]
    > ![Microsoft エンドポイント マネージャー 管理 Center6 の画像。](images/ios-deploy-6.png)

1. **[次へ]** を選択して、**[スコープ タグ]** ページを開きます。 スコープ タグは省略可能です。 [**次へ**] を選んで続行します。

1. **[割り当て]** ページで、このプロファイルを受け取るグループを選択します。 このシナリオでは、 **すべてのデバイス** をターゲットにすることをお勧めします。 プロファイルの割り当ての詳細については、[ユーザーおよびデバイス プロファイルの割り当て](/mem/intune/configuration/device-profile-assign)に関するページを参照してください。

   ユーザー グループに展開する場合、ユーザーはポリシーを適用する前にデバイスにサインインする必要があります。

   [**次へ**] をクリックします。

1. **[確認および作成]** ページで、完了したら、**[作成]** を選択します。 構成プロファイルの一覧に新しいプロファイルが表示されます。

1. 次に、監視対象のiOS デバイスにカスタム プロファイルを展開する必要があります。 これは、強化されたフィッシング対策機能用です。 次の手順に従います。

    - 構成プロファイルをダウンロードする [https://aka.ms/mdeiosprofilesupervised](https://aka.ms/mdeiosprofilesupervised)
    - **デバイス** -> **iOS/iPadOS** -> **構成プロファイルに** 移動 **する プロファイル** の -> 作成

    > [!div class="mx-imgBorder"]
    > ![Microsoft エンドポイント マネージャー 管理 Center7 の画像。](images/ios-deploy-7.png)
    
    - プロファイルの名前を指定します。 構成プロファイル ファイルのインポートを求めるメッセージが表示されたら、前の手順からダウンロードしたファイルを選択します。
    - [ **割り当て]** セクションで、このプロファイルを適用するデバイス グループを選択します。 ベスト プラクティスとして、これはすべてのマネージド iOS デバイスに適用する必要があります。 **[次へ]** を選択します。
    - **[確認および作成]** ページで、完了したら、**[作成]** を選択します。 構成プロファイルの一覧に新しいプロファイルが表示されます。


## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a>VPN プロファイルの自動オンボード (簡易オンボード)

教師なしデバイスの場合、Web 保護機能を提供するために VPN が使用されます。 これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカル/セルフループ VPN です。

>[!NOTE]
>監視対象デバイスの場合、Web Protection 機能には VPN は必要ありません。管理者は監視対象デバイスに構成プロファイルを設定する必要があります。 監視対象デバイスを構成するには、「監視対象デバイスの [展開の完了」](#complete-deployment-for-supervised-devices) セクションの手順に従います。

管理者は、VPN プロファイルの自動セットアップを構成できます。 これにより、オンボード中にユーザーが実行しなくても、Defender for Endpoint VPN プロファイルが自動的に設定されます。 

この手順では、VPN プロファイルを設定することで、オンボード プロセスを簡略化します。 ゼロタッチまたはサイレント オンボードエクスペリエンスについては、次のセクション「 [ゼロタッチオンボード」を](#zero-touch-onboarding-of-microsoft-defender-for-endpoint)参照してください。

1. [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、[**デバイス** -> **構成プロファイル** の **作成プロファイル** -> ] に移動します。
1. **iOS/iPadOS** として **プラットフォーム** を選択し、**VPN** として **プロファイルの種類を選択します**。 **[作成]** をクリックします。
1. プロファイルの名前を入力し、[ **次へ**] をクリックします。
1. [接続の種類] の **[カスタム VPN** ] を選択し、[ **基本 VPN** ] セクションで次のように入力します。
    - 接続名 = Microsoft Defender for Endpoint
    - VPN サーバー アドレス = 127.0.0.1
    - Auth メソッド = "Username and password"
    - 分割トンネリング = 無効
    - VPN 識別子 = com.microsoft.scmx
    - キーと値のペアで、キー **AutoOnboard** を入力し、値を True に設定 **します**。
    - 自動 VPN の種類 = オンデマンド VPN
    - [**オンデマンド ルール** の **追加]** を選択し、**次の操作を行う = [VPN のConnect**] を選択します。**制限する場合は [ = すべてのドメイン**] を選択します。

    :::image type="content" source="images/ios-deploy-8.png" alt-text="[VPN プロファイルの構成設定] タブ" lightbox="images/ios-deploy-8.png":::

1. [次へ] をクリックし、対象ユーザーにプロファイルを割り当てます。
1. [ *確認と作成* ] セクションで、入力したすべての情報が正しいことを確認し、[ **作成**] を選択します。

## <a name="zero-touch-onboarding-of-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointのゼロタッチ オンボード



> [!NOTE]
> ゼロタッチは、ユーザー アフィニティ (ユーザーレス デバイスまたは共有デバイス) なしで登録されているiOS デバイスでは構成できません。

管理者は、サイレント モードでデプロイおよびアクティブ化するようにMicrosoft Defender for Endpointを構成できます。 このフローでは、管理者がデプロイ プロファイルを作成し、ユーザーにインストールの通知を受け取ります。 Defender for Endpoint は、ユーザーがアプリを開く必要なく自動的にインストールされます。 次の手順に従って、登録済みのiOS デバイスで Defender for Endpoint のゼロタッチまたはサイレント 展開を設定します。

1. [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、[**デバイス** > **構成プロファイル** の **作成プロファイル** > ] に移動します。
1. **iOS/iPadOS** として **プラットフォーム** を選択し、**VPN** として **プロファイルの種類を選択します**。 **[作成]** を選択します。
1. プロファイルの名前を入力し、[ **次へ**] を選択します。
1. [接続の種類] の **[カスタム VPN** ] を選択し、[ **基本 VPN** ] セクションで次のように入力します。
    - 接続名 = Microsoft Defender for Endpoint
    - VPN サーバー アドレス = 127.0.0.1
    - Auth メソッド = "Username and password"
    - 分割トンネリング = 無効
    - VPN 識別子 = com.microsoft.scmx
    - キーと値のペアで、キー **SilentOnboard** を入力し、値を True に設定 **します**。
    - 自動 VPN の種類 = オンデマンド VPN
    - [**オンデマンド ルール** の **追加]** を選択し、**次の操作を行う = [VPN のConnect**] を選択します。**制限する場合は [ = すべてのドメイン**] を選択します。

    :::image type="content" source="images/ios-deploy-9.png" alt-text="[VPN プロファイルの構成] ページ" lightbox="images/ios-deploy-9.png":::

1. **[次へ**] を選択し、対象ユーザーにプロファイルを割り当てます。
1. [ *確認と作成* ] セクションで、入力したすべての情報が正しいことを確認し、[ **作成**] を選択します。

上記の構成が完了し、デバイスと同期されると、対象となるiOS デバイスで次のアクションが実行されます。
    - Microsoft Defender for Endpointは展開され、サイレント オンボードされ、デバイスは Defender for Endpoint ポータルに表示されます。
    - 暫定的な通知がユーザー デバイスに送信されます。
    - Web Protection およびその他の機能がアクティブ化されます。

   > [!NOTE]
   > 監視対象デバイスの場合、VPN プロファイルは必要ありませんが、管理者は、Intune経由で Defender for Endpoint VPN プロファイルを構成することでゼロタッチ オンボードを設定できます。 VPN プロファイルはデバイスに展開されますが、デバイスにはパススルー プロファイルとしてのみ存在し、初期オンボード後に削除できます。

## <a name="complete-onboarding-and-check-status"></a>オンボードを完了し、状態を確認する

1. iOS上の Defender for Endpoint がデバイスにインストールされると、アプリ アイコンが表示されます。

    :::image type="content" source="images/41627a709700c324849bf7e13510c516.png" alt-text="スマート フォンの説明が自動的に生成される" lightbox="images/41627a709700c324849bf7e13510c516.png":::

2. Defender for Endpoint アプリ アイコン (MSDefender) をタップし、画面の指示に従ってオンボード手順を完了します。 詳細には、iOS上の Defender for Endpoint で必要なiOSアクセス許可のエンドユーザー受け入れが含まれます。

3. オンボードに成功すると、Microsoft 365 Defender ポータルの [デバイス] 一覧にデバイスが表示されます。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/device-inventory-screen.png" alt-text="[デバイス インベントリ] ページ" lightbox="images/device-inventory-screen.png":::

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>監視モードのMicrosoft Defender for Endpointを構成する

iOS アプリのMicrosoft Defender for Endpointには、このような種類のデバイス上のプラットフォームによって提供される管理機能の向上に応じて、監視付きiOS/iPadOS デバイスに特化した機能があります。 これらの機能を利用するには、Defender for Endpoint アプリでデバイスが監視モードであるかどうかを把握する必要があります。

### <a name="configure-supervised-mode-via-intune"></a>Intuneを使用して監視モードを構成する

Intuneでは、App Configuration ポリシーを使用して、iOS アプリ用の Defender を構成できます。

   > [!NOTE]
   > 監視対象デバイスのこのアプリ構成ポリシーは、管理対象デバイスにのみ適用され、ベスト プラクティスとしてすべてのマネージド iOS デバイスを対象にする必要があります。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインし、[**アプリ** \> **の構成ポリシー** \> **の追加**] に移動します。 **[管理対象デバイス**] をクリックします。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-4.png" alt-text="[管理対象デバイス] オプション" lightbox="images/ios-deploy-4.png":::

1. [ *アプリ構成ポリシーの作成* ] ページで、次の情報を入力します。
    - ポリシー名
    - プラットフォーム: iOS/iPadOS を選択する
    - 対象アプリ: 一覧から **Microsoft Defender for Endpoint** を選択する

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-5.png" alt-text="アプリケーションの構成ポリシーの基本フィールド" lightbox="images/ios-deploy-5.png":::

1. 次の画面で、 **構成デザイナーを** 形式として使用を選択します。 次のプロパティを指定します。
    - 構成キー: issupervised
    - 値の型:String
    - 構成値: {{issupervised}}

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/ios-deploy-6.png" alt-text="ポリシー構成の設定の形式を選択するページ" lightbox="images/ios-deploy-6.png":::

1. [ **次へ** ] をクリックして、[ **スコープ タグ]** ページを開きます。 スコープ タグは省略可能です。 続行するには、**[次へ]** をクリックします。

1. **[割り当て]** ページで、このプロファイルを受け取るグループを選択します。 このシナリオでは、 **すべてのデバイス** をターゲットにすることをお勧めします。 プロファイルの割り当ての詳細については、[ユーザーおよびデバイス プロファイルの割り当て](/mem/intune/configuration/device-profile-assign)に関するページを参照してください。

   ユーザー グループに展開する場合、ユーザーはポリシーを適用する前にデバイスにサインインする必要があります。

   [**次へ**] をクリックします。

1. **[確認および作成]** ページで、完了したら、**[作成]** を選択します。 構成プロファイルの一覧に新しいプロファイルが表示されます。

## <a name="next-steps"></a>次の手順

- [Defender for Endpoint リスクシグナル (MAM) を含めるアプリ保護ポリシーを構成する](ios-install-unmanaged.md)
- [iOS機能で Defender for Endpoint を構成する](ios-configure-features.md)
