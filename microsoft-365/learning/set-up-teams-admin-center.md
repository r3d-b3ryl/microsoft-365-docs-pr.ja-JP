---
title: 管理センターで Microsoft Viva Learning (プレビュー) をTeamsする
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 管理センターで Microsoft Viva Learning (プレビュー) を構成するTeams説明します。
ms.openlocfilehash: e5af676752064738e26f9b934a60973cb9b0200d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625300"
---
# <a name="set-up-microsoft-viva-learning-preview-in-the-teams-admin-center"></a>管理センターで Microsoft Viva Learning (プレビュー) をTeamsする

> [!NOTE]
> この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。 

管理者Teamsビバ ラーニング (プレビュー) をインストールし、管理者センターからアクセス許可ポリシー Teams適用します。

1. パブリック プレビューの場合は、まず更新ポリシーを設定する必要があります。 詳細については、「パブリック プレビュー」TeamsをMicrosoft Teams[してください](/MicrosoftTeams/public-preview-doc-updates)。

    1. 管理者センターにサインインTeamsします。

    2. [更新  >  **Teams] を選択します**。

    3. **[追加]** を選択します。 

    4. 更新ポリシーに名前を付け、ポリシーを追加し、[プレビュー機能の表示 **] をオンにします**。

2. 管理者は、ポリシー更新プログラムをユーザーに通知して、ビルドをパブリック プレビューに移動Teams。 

    1. ユーザーは、プロファイル イメージ --> -->を選択する必要があります。
   
        ![ユーザーのプロファイルをTeamsアプリケーションの上部ナビゲーション](../media/learning/learning-app-select-profile-teams.png)
    
    2. ユーザーはパブリック プレビューの条項に同意する必要があります。

        ![パブリック プレビュー ビルドに切り替える](../media/learning/learning-app-switch-to-public-preview.png)
 
3. 制限的なポリシーを持ち、Viva Learning を有効にする必要がある組織の場合は、次のセクションの手順に従います。

## <a name="manage-settings-for-viva-learning-preview"></a>ビバラーニングの設定を管理する (プレビュー)

これらのタスクを実行するには、管理センター Teams管理者である必要があります。

組織内のユーザーがビバ ラーニング (プレビュー) を利用するには、次の手順を実行します。

1. 管理センターの左側のナビゲーションTeams、[アプリの管理 **Teams]**  >  **に移動します**。

   ![[アプリとアプリのTeams管理] セクションをTeams管理センターの左側のナビゲーション。](../media/learning/learning-app-teams-manage-apps-nav.png)

2. [アプリの **管理] ページ** の検索ボックスに「 *ビ* バ ラーニング」と入力し、[ビバ ラーニング (プレビュー) ] **を選択します**。

   ![[アプリの管理] ページで、Teamsを表示する管理センターで管理します。](../media/learning/learning-app-teams-manage-apps-page.png)

3. [ビバ **ラーニング (プレビュー)] ページで、次の設定を行** います。

   1. [ **状態] で**、[ **ビバ ラーニング (** プレビュー) を有効にする許可] を選択します。

   2. [アプリの **設定]** タブの **[アプリ** の設定] で、Microsoft 365管理センターに移動して、学習コンテンツ ソース [を構成します](content-sources-365-admin-center.md)。

   ![[状態とアプリの設定] セクションTeams管理センターの [学習] ページ。](../media/learning/learning-app-teams-learning-page.png)

4. [**アプリ設定の管理**]の後、[アクセス許可ポリシーとセットアップ ポリシー] に移動して、組織のプレビューへの参加の一環として、ビバ ラーニング (プレビュー) にアクセスできる必要がある従業員にアクセス許可を付与します。

> [!NOTE]
>  組織が Teams TAP100 プログラムの一部としてリング 4.0 にある場合は、リング 3.0 の承認済みユーザーがビバ ラーニング (プレビュー) にアクセスできる必要がある場合があります。 <br><br>プレビューの一環として、Viva Learning (Preview) はリング 3.0 でリリースされます。 組織がリング 4.0 にある場合は、[アプリの管理] ページに [ビバ ラーニング (プレビュー) **が表示** されます。 アプリをテストするには、カスタム アプリのアクセス許可ポリシーを作成し、[すべてのアプリを許可する] に設定し、それを Ring 3.0 承認済みユーザーに割り当てる必要があります。 <br><br>   ![TAP-AppsPermission-Plcy ページで、[すべてのアプリを選択できます] が表示されます。](../media/learning/learning-app-tap-appspermission-plcy.png)

## <a name="next-step"></a>次の手順

[管理センターで、ビバ ラーニング (プレビュー) の学習コンテンツ ソースMicrosoft 365構成する](content-sources-365-admin-center.md)
