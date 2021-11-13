---
title: Go1 をコンテンツ ソースとして構成Microsoft Viva ラーニング
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Go1 を学習コンテンツ ソースとして構成する方法についてMicrosoft Viva ラーニング。
ms.openlocfilehash: 1adef6275be2a8656eaad9a7f47805d13299e3c7
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950535"
---
# <a name="configure-go1-as-a-content-source-for-microsoft-viva-learning"></a>Go1 をコンテンツ ソースとして構成Microsoft Viva ラーニング

この記事では、ビバ グループのサードパーティのラーニング コンテンツ ソースとして Go1 を構成するラーニング。

>[!NOTE]
>ビバ サービスからアクセスラーニングは、Microsoft 製品条項以外の条項に従います。 Go1 コンテンツおよび関連するサービスは、Go1 のプライバシーとサービスの条件の対象です。

Go1 は、トップ コンテンツ プロバイダーから何千ものコースにアクセスできます。 [Go1 の詳細を参照してください](https://www.go1.com/go1-microsoft-viva)。 次の手順に従って、Go1 をビバ のラーニング ソースとして追加ラーニング。

## <a name="configure-in-your-go1-portal"></a>Go1 ポータルで構成する

>[!NOTE]
>これらの手順を完了するには、Go1 で管理者権限が必要です。

まず、Go1 ポータルでアプリを作成するには、次の手順に従う必要があります。 このアプリは API キーを生成します。これにより、Go1 での認証や API への要求を行う場合に使用できます。

1. 管理者として Go1 ポータルにサインインします。

2. メニュー **オプションから [** 統合] を選択します。

3. [開発者 **] を選択します**。
4. [アプリの **作成] ボタンを** 選択します。
5. アプリの名前を入力します(たとえば、「My-go1-viva-integration」)。
6. 呼び出しの URL を入力します。たとえば、「Mycompany.mygo1.com」。
7. 入力した情報を保存します。
8. シークレットが非表示の情報が表示されます。 省略記号 (**...) を選択し、[** シークレットの表示 **] を選択してシークレット** を表示します。
9. 次の値をコピーします。

    - **クライアントのホスト URL:** これは Go1 ポータルの URL です。 "" のように表示 https://mycompany.mygo1.com されます。
    - **クライアント ID:** Go1 ポータルの [統合/開発者] メニュー オプションの下に **ID があります** 。
    - **シークレット:** シークレットは、Go1 ポータルの [統合/開発者] メニュー **オプションの下に** 表示されます。

[Go1 用のプライベート開発者向けアプリを作成する方法について説明します](https://help.go1.com/en/articles/4642648-integrate-with-the-go1-api)。

## <a name="configure-in-your-microsoft-365-admin-center"></a>サーバーで構成Microsoft 365 管理センター

>[!NOTE]
>これらの手順を実行するには、管理者のアクセス許可Microsoft 365必要があります。

1. 自分のアカウントに[ログインMicrosoft 365 管理センター。](https://admin.microsoft.com)
2. [組織の設定 **設定]** の順 **に移動します**。 [ビバ ラーニング] を選択し、パネルで [Go1] を有効にします。
3. Go1 ポータルから取得した構成の詳細を入力します。
4. [保存 **] を選択** して、ビバ の Go1 コンテンツをアクティブラーニング。 コンテンツがビバ アプリに表示されるのに最大 24 時間かかるラーニングがあります。
