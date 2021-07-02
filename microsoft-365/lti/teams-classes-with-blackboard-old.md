---
title: Blackboard でMicrosoft Teamsクラスを使用する
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 管理Microsoft Teamsシステムにラーニングクラスを統合する
ms.openlocfilehash: 3c574184c48ae064d425ed98dbc391b8f5bcf7e0
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256997"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a>Blackboard でMicrosoft Teamsクラスを使用する

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft Teamsクラスは、ラーニング ツール相互運用性 (LTI) アプリで、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。 ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a>テナントでアプリをMicrosoft Azureする

次のタスクは、管理者と Blackboard Learn Ultra Microsoft Office 365によって完了します。

Blackboard Learn Ultra 内の統合を管理する前に、Microsoft Office 365 管理者は、教育機関の Microsoft Azure テナントの Blackboard **MSFT Teams** for Learn Ultra Azure アプリを承認する必要があります。

1. Microsoft テナント ID を見つける。 テナント [を検索する方法を参照してください](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)。

2. 次の例に従って、Microsoft Identity Platform Admin Consent Endpoint をリダイレクトします。

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > {tenant} を組織の Microsoft テナント ID に置き換える。

## <a name="register-the-integration-apps"></a>統合アプリの登録

Blackboard Learn Ultra 管理者として、テスト環境内に 2 つの LTI 1.3 統合アプリを登録する必要があります。

- 名簿の同期をTeamsする Blackboard Learn クラスの統合

- クラス Microsoft Teams LTI アプリ

1. 両方のアプリに対して次の LTI クライアント ID をメモします。

    - Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41

    - Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89

2. 管理パネルにアクセスし、[統合] **で** LTI ツール プロバイダーを探します。

   ![これは、[LTI ツール プロバイダー] ダイアログボックスにプロバイダーの一覧が表示されます。](../media/lti-media/lti-tool-providers.png)

3. **[LTI1.3/Advantage Tool の登録] を選択します**。

4. 指定されたクライアント ID (Blackboard または Microsoft) の最初の ID を入力し、[送信] を **選択します**。

5. 事前に設定された設定を確認し、ツールの状態が承認済みとしてマークされている必要があります。

6. 下までスクロールし、[送信] を **選択します**。

7. 前の手順を繰り返して、環境内で 2 番目の LTI アプリを登録します。

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a>REST アプリケーションとクロスオリジン リソース共有のセットアップ

Blackboard Learn Ultra 管理者は、REST アプリケーションとクロス オリジン リソース共有構成を構成する必要があります。

REST アプリケーションをセットアップするには、次の手順を実行します。

1. [管理ツールの学習] にアクセスし、[統合] セクションから **[REST API の** 統合 **] を選択** します。

2. [**統合の作成] を** 選択し、統合 LTI ツールに対して入力したのと同じアプリケーション/クライアント ID Teams入力します。

3. [ユーザーの学習] を入力します (これは、管理者のユーザー名を学習する場合があります)、または [参照] を選択 **して** 検索します。

4. [エンド **ユーザー アクセス] で** **[はい] を選択します**。

5. [ユーザー **として機能****する承認] で [はい] を選択します。**

6. [完了 **したら送信]** を選択します。

## <a name="set-up-cross-origin-resource-sharing"></a>クロスオリジン リソース共有のセットアップ

1. [管理ツールの学習] にアクセスし、[統合] セクションから [クロスオリジン **リソース共有****] を選択** します。

2. [構成 **の作成] を選択します**。

3. 原点 `https://bb-ms-teams-ultra-ext.api.blackboard.com` に入力します。

4. [許可するヘッダー **] に [承認****] という単語を追加します**。

5. [使用可能 **] を [はい** ] **に設定します**。

6. [完了 **したら送信]** を選択します。

## <a name="enable-class-teams-in-blackboard-learn"></a>Blackboard Learn でTeamsを有効にする

LTI ツールを有効にしたら、次の手順では、独自のテナントから Microsoft Class Teams統合をMicrosoft Office 365します。 これを行うには、Blackboard Learn Ultra 管理者として次の手順を実行します。

1. [**管理ツールと**  >  **ユーティリティの詳細] で**、[統合管理者] **Microsoft Teamsを選択します**。

   ![使用可能なツールの一覧を含むツールとユーティリティ ダイアログ](../media/lti-media/tools-utilities.png)

2. [有効にする] チェック **ボックスをオンMicrosoft Teams。**

3. [Microsoft O365 Admin] のセクションで参照されているテナント ID を入力します。

 > [!NOTE]
 > アプリが O365 管理者によって承認されるまで、設定を保存できない。「[アプリを承認する」を参照Microsoft Azureします](#approve-the-app-in-the-microsoft-azure-tenant)。

4. グローバル O365 管理者が Microsoft テナントの Blackboard Teamsを承認した場合は、[送信] を **選択します**。
