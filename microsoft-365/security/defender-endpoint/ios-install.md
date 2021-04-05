---
title: iOS 用 Microsoft Defender ATP のアプリベースの展開
ms.reviewer: ''
description: アプリを使用して iOS 用 Microsoft Defender ATP を展開する方法について説明します。
keywords: microsoft、Defender、atp、ios、アプリ、インストール、展開、アンインストール、Intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c94c6839c17b3bbb432cef12fe58723d0cc2ecff
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587241"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-ios"></a>Microsoft Defender for Endpoint for iOS の展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

このトピックでは、Intune ポータル サイト登録デバイスでの IOS 用 Defender for Endpoint の展開について説明します。 Intune デバイスの登録の詳細については、「Intune に [iOS/iPadOS デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)。

## <a name="before-you-begin"></a>はじめに

- Microsoft Endpoint Manager 管理センター [へのアクセス権を持っている必要があります](https://go.microsoft.com/fwlink/?linkid=2109431)。

- ユーザーに対して iOS 登録が行われたことを確認します。 IOS 用 Defender for Endpoint を使用するには、Defender for Endpoint ライセンスが割り当てられている必要があります。 ライセンスの割 [り当て方法については、「ユーザー](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) にライセンスを割り当てる」を参照してください。

> [!NOTE]
> iOS 用 Microsoft Defender ATP (Microsoft Defender for Endpoint) が Apple App [Store で利用可能になります](https://aka.ms/mdatpiosappstore)。

## <a name="deployment-steps"></a>展開手順

Intune ポータル サイトを介して iOS 用 Defender for Endpoint を展開します。

### <a name="add-ios-store-app"></a>iOS ストア アプリの追加

1. [Microsoft Endpoint manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)  ->  **アプリ] iOS/iPadOS [iOS** ストア アプリの追加] に移動し、[  ->    ->  選択] を **クリックします**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager Admin Center1 のイメージ](images/ios-deploy-1.png)

1. [アプリの追加] ページで、[アプリ ストアの検索] をクリック **し** 、検索バーに **「Microsoft Defender Endpoint」** と入力します。 [検索結果] セクションで *、[Microsoft Defender Endpoint]* をクリックし、[選択] を **クリックします**。

1. [ **最小オペレーティング システム] として [iOS 11.0]** を選択します。 アプリに関する残りの情報を確認し、[次へ] を **クリックします**。

1. [割り *当て] セクションで* 、[必須] **セクションに** 移動し、[グループの追加] **を選択します**。 その後、IOS アプリの Defender for Endpoint をターゲットとするユーザー グループを選択できます。 [選択 **] をクリック** し、[次へ] **をクリックします**。

    > [!NOTE]
    > 選択したユーザー グループは、Intune に登録されたユーザーで構成する必要があります。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager Admin Center2 のイメージ](images/ios-deploy-2.png)

1. [確認 *と作成] セクション* で、入力された情報が正しいか確認し、[作成] を **選択します**。 しばらくすると、Defender for Endpoint アプリが正常に作成され、ページの右上隅に通知が表示されます。

1. 表示されるアプリ情報ページの [モニター]セクションで、[デバイスのインストール状態] を選択して、デバイスのインストールが正常に完了したと確認します。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager Admin Center3 のイメージ](images/ios-deploy-3.png)

## <a name="complete-onboarding-and-check-status"></a>オンボーディングとチェックの状態を完了する

1. デバイスに Defender for Endpoint for iOS がインストールされた後、アプリ アイコンが表示されます。

    ![スマートフォンの説明が自動的に生成されるスクリーン ショット](images/41627a709700c324849bf7e13510c516.png)

2. [Defender for Endpoint] アプリ アイコンをタップし、画面の指示に従ってオンボーディングの手順を完了します。 詳細には、Defender for Endpoint for iOS に必要な iOS アクセス許可のエンド ユーザーによる承諾が含まれます。

3. オンボードが成功すると、デバイスは Microsoft Defender セキュリティ センターの [デバイス] リストに表示されます。

    > [!div class="mx-imgBorder"]
    > ![自動的に生成された携帯電話の説明のスクリーンショット](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>監視モード用に Microsoft Defender for Endpoint を構成する

Microsoft Defender for Endpoint for iOS アプリは、これらの種類のデバイスでプラットフォームによって提供される管理機能の強化を考えると、監視対象の iOS/iPadOS デバイスに特化した機能を備えます。 これらの機能を利用するには、Defender for Endpoint アプリがデバイスが監視モードにあるかどうかが知る必要があります。

### <a name="configure-supervised-mode-via-intune"></a>Intune 経由で監視モードを構成する

Intune を使用すると、アプリ構成ポリシーを使用して Defender for iOS アプリを構成できます。

   > [!NOTE]
   > 監視対象デバイスのこのアプリ構成ポリシーは、管理対象デバイスにのみ適用され、ベスト プラクティスとしてすべての管理対象 iOS デバイスを対象とする必要があります。

1. Microsoft Endpoint [Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理センターにサインインし、[アプリ アプリ構成ポリシーの追加]  >  **に**  >  **移動します**。 [管理対象デバイス **] をクリックします**。

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager Admin Center4 のイメージ](images/ios-deploy-4.png)

1. [アプリ構成 *ポリシーの作成] ページ* で、次の情報を入力します。
    - ポリシー名
    - プラットフォーム: iOS/iPadOS を選択する
    - 対象アプリ: リスト **から Microsoft Defender ATP** を選択する

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager Admin Center5 のイメージ](images/ios-deploy-5.png)

1. 次の画面で、[構成デザイナー **を形式として使用** する] を選択します。 次のプロパティを指定します。
    - 構成キー: issupervised
    - 値の型:String
    - 構成値: {{issupervised}}
    
    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager Admin Center6 のイメージ](images/ios-deploy-6.png)

1. [次 **へ] を** クリックして [スコープ タグ **] ページを** 開きます。 スコープ タグはオプションです。 続行するには、**[次へ]** をクリックします。

1. [割り **当て] ページ** で、このプロファイルを受け取るグループを選択します。 このシナリオでは、すべてのデバイスをターゲットに設定するベスト **プラクティスです**。 プロファイルの割り当ての詳細については、「Assign [user and device profiles」を参照してください](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。

   ユーザー グループに展開する場合、ユーザーはポリシーが適用される前にデバイスにサインインする必要があります。

   [ **次へ**] をクリックします。

1. [レビュー **と作成] ページ** で、完了したら、[作成] を **選択します**。 新しいプロファイルが構成プロファイルの一覧に表示されます。

1. 次に、フィッシング対策機能を強化するには、監視対象の iOS デバイスにカスタム プロファイルを展開できます。 以下の手順に従います。
    - 構成プロファイルのダウンロード [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)
    - [デバイス  ->  **] iOS/iPadOS**  ->  **構成プロファイルの [プロファイルの**  ->  **作成] に移動します。**

    > [!div class="mx-imgBorder"]
    > ![Microsoft Endpoint Manager Admin Center7 のイメージ](images/ios-deploy-7.png)

    - プロファイルの名前を指定します。 構成プロファイル ファイルのインポートを求めるメッセージが表示されたら、上記でダウンロードしたファイルを選択します。
    - [割 **り当て** ] セクションで、このプロファイルを適用するデバイス グループを選択します。 ベスト プラクティスとして、これはすべての管理対象 iOS デバイスに適用する必要があります。 [ **次へ**] をクリックします。
    - [レビュー **と作成] ページ** で、完了したら、[作成] を **選択します**。 新しいプロファイルが構成プロファイルの一覧に表示されます。

## <a name="next-steps"></a>次の手順

[iOS 機能用に Defender for Endpoint を構成する](ios-configure-features.md)
