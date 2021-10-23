---
title: Go1 をコンテンツ ソースとして構成Microsoft Viva ラーニング
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/07/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Go1 を学習コンテンツ ソースとして構成する方法についてMicrosoft Viva ラーニング。
ROBOTS: NOINDEX
ms.openlocfilehash: 2751a855f663ca47f0e5896b489f4ee9d3055cf5
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557295"
---
# <a name="configure-go1-as-a-content-source-for-microsoft-viva-learning"></a>Go1 をコンテンツ ソースとして構成Microsoft Viva ラーニング

この記事では、ビバ グループのサードパーティのラーニング コンテンツ ソースとして Go1 を構成するラーニング。

>[!NOTE]
>ビバ サービスからアクセスラーニングは、Microsoft 製品条項以外の条項に従います。 Go1 コンテンツおよび関連するサービスは、Go1 のプライバシーとサービスの条件の対象です。

Go1 は、トップ コンテンツ プロバイダーから何千ものコースにアクセスできます。 [Go1 の詳細を参照してください](https://www.go1.com/go1-microsoft-viva)。 次の手順に従って、Go1 をビバ のラーニング ソースとして追加ラーニング。

## <a name="create-a-developers-app-in-go1"></a>Go1 で開発者のアプリを作成する

まず、Go1 ポータルでアプリを作成するには、次の手順に従う必要があります。 このアプリは API キーを生成します。これにより、Go1 での認証や API への要求を行う場合に使用できます。

1. 管理者として Go1 ポータルにサインインします。

2. メニュー **オプションから [** 統合] を選択します。

3. [開発者 **] を選択します**。

    <!--![Image of the Developers option in the Integrations menu.](../media/learning/go1-1.png)-->

4. [アプリの **作成] ボタンを** 選択します。

    <!--![Image of the Create App button.](../media/learning/go1-2.png)-->

5. アプリの名前を入力します(たとえば、「My-go1-viva-integration」)。

6. 呼び出しの URL を入力します。たとえば、「Mycompany.mygo1.com」。

    <!--![Image of the field where you enter the name and callback URL.](../media/learning/go1-3.png)-->

7. 入力した情報を保存します。

8. シークレットが非表示の情報が表示されます。 省略記号 (**...) を選択し、[** シークレットの表示 **] を選択してシークレット** を表示します。

9. 次の値をコピーします。

    - **クライアントのホスト URL:** これは Go1 ポータルの URL です。 "" のように表示 https://mycompany.mygo1.com されます。
    - **クライアント ID:** Go1 ポータルの [統合/開発者] メニュー オプションの下に **ID があります** 。
    - **シークレット:** シークレットは、Go1 ポータルの [統合/開発者] メニュー **オプションの下に** 表示されます。

## <a name="complete-configuration-in-the-microsoft-365-admin-center"></a>サーバーで構成を完了Microsoft 365 管理センター

Go1 ポータルから取得した値をコピーして、次のページの [Go1 セットアップ] 画面に貼りMicrosoft 365 管理センター。

[Go1 用のプライベート開発者向けアプリを作成する方法について説明します](https://help.go1.com/en/articles/4642648-integrate-with-the-go1-api)。
