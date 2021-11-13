---
title: Udemy をコンテンツ ソースとして構成Microsoft Viva ラーニング
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
description: Udemy を学習コンテンツ ソースとして構成する方法についてMicrosoft Viva ラーニング。
ms.openlocfilehash: ea015d6ee0ec1890d56b6f40f928fe96ea44ccbc
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950583"
---
# <a name="configure-udemy-as-a-content-source-for-microsoft-viva-learning"></a>Udemy をコンテンツ ソースとして構成Microsoft Viva ラーニング

この記事では、Udemy をサードパーティのラーニング コンテンツ ソースとして構成する方法についてMicrosoft Viva ラーニング。

>[!NOTE]
>ビバ サービスからアクセスラーニングは、Microsoft 製品条項以外の条項に従います。 Udemy コンテンツおよび関連するサービスは、Udemy のプライバシーとサービスの条件の対象です。

## <a name="configure-in-your-udemy-portal"></a>Udemy ポータルで構成する

>[!NOTE]
>これらの手順を完了するには、Udemy で管理者のアクセス許可が必要です。

次の手順に従って、Udemy Business 環境で API を有効にし、LMS/LXP アプリケーションのクライアント資格情報を生成してアクセスします。

1. [管理]**に移動** し **、[設定** API] に **移動します**。 API の状態を確認します。 無効になっている場合は、サポートに連絡して有効にするか、以下の手順に従って有効にすることができます。

    ![[API 設定] ページのイメージ。](../media/learning/udemy-1.png)

2. API が無効になっている場合は **、LMS/LXP** 統合に移動し、[セットアップの開始] 、次に **[その** 他] に **移動します**。

    [![[LMS/LXP 統合] 設定ページのイメージ。](../media/learning/udemy-2small.png)](../media/learning/udemy-2.png#lightbox)

3. 次の画面で、カスタム LMS/LXP またはサード パーティ製アプリケーションの名前を入力します。 次に、[自動登録] オプションをオンまたはオフにし、[保存] を **選択します**。 自動登録オプションを使用すると、LMS/LXP を使用してコースを起動するユーザーは、自動的に Udemy に登録されます。

    ![自動登録のオン/オフトグルのイメージ。](../media/learning/udemy-3.png)

4. 保存すると、クライアント ID とクライアント シークレットが生成され、画面からコピーできます。 これで、指定されたクライアント資格情報を使用して API にアクセスできます。

    ![生成されたクライアント ID とクライアント シークレットのイメージ。](../media/learning/udemy-4.png)

5. API エンドポイントにアクセスするには、API エンドポイントとエンドポイントの URL ACCOUNT_ID必要があります。 この情報にアクセスし、[管理] 、次に [API]の順に移動して API **を** 試設定試 **します**。 API を有効にすると、API の状態が "有効" と表示されます。 [API ドキュメント] リンクを選択します。

    ![API が有効として表示されている API 設定のイメージ。](../media/learning/udemy-5.png)

6. 概要ページから API エンドポイントの URL ACCOUNT_IDを取得します。 サポートされているメソッドに移動して API 呼び出しを試します。 これで、すべてのユーザーが Udemy Business API を呼び出す設定が可能です。

    ![エンドポイント URL とクライアント ID を表示する概要ページのイメージ。](../media/learning/udemy-6.png)
    ![URL とクライアント ID を入力できる [自分で試す] ページのイメージ。](../media/learning/udemy-7.png)

## <a name="configure-in-your-microsoft-365-admin-center"></a>サーバーで構成Microsoft 365 管理センター

>[!NOTE]
>これらの手順を実行するには、管理者のアクセス許可Microsoft 365必要があります。

前の手順を使用して Udemy ポータルから必要な構成の詳細を受け取った後、テナント管理者は、次の手順を使用して、Microsoft 365 管理センター で Udemy をラーニング ソースとして構成する必要があります。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)に移動します。

2. [組織の設定 **設定]** の順 **に移動します**。 [ビバ] ラーニングを検索し、オプションから Udemy を有効にします。

3. 次の必要な構成の詳細を入力します。

    - **クライアントのホスト URL**: 手順 6 の Udemy ポータルから収集された API エンドポイント URL です。
    - **組織 ID**: 手順 6 で Udemy ポータルACCOUNT_ID収集された組織 ID です。
    - **クライアント ID**: これは、手順 4 の Udemy ポータルから収集されたクライアント ID です。
    - **クライアント シークレット**: これは、手順 4 の Udemy ポータルから収集されたクライアント シークレットです。

4. [**保存] を** 選択して、ユーザー設定で Udemy Microsoft Viva ラーニング。 コンテンツがビバ で利用可能になるには、最大で 24 時間かかる場合ラーニング。
