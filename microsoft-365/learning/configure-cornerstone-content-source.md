---
title: Cornerstone OnDemand をコンテンツ ソースとして構成Microsoft Viva ラーニング
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
description: Cornerstone OnDemand をユーザーの学習コンテンツ ソースとして構成するMicrosoft Viva ラーニング。
ROBOTS: NOINDEX
ms.openlocfilehash: 0d4f344b2c5ea6854337bb78013994ae5da16f70
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557259"
---
# <a name="configure-cornerstone-ondemand-as-a-content-source-for-microsoft-viva-learning"></a>Cornerstone OnDemand をコンテンツ ソースとして構成Microsoft Viva ラーニング

この記事では、Cornerstone OnDemand をサードパーティのラーニング コンテンツ ソースとしてビバ で構成する方法をラーニング。 まず、ビバ の設定を有効にしラーニング、コーナーストーン ポータルから詳細を取得する必要があります。 次に、サーバーで構成を完了する必要Microsoft 365 管理センター。

>[!NOTE]
>ビバ サービスからアクセスラーニングは、Microsoft 製品条項以外の条項に従います。 Cornerstone OnDemand コンテンツおよび関連するサービスは、Cornerstone OnDemand のプライバシーおよびサービス条件の対象です。

## <a name="configure-in-your-cornerstone-portal"></a>コーナーストーン ポータルで構成する

1. コーナーストーン ポータルに管理者としてログインします。
2. [エッジ **] を選択します**。
3. [Marketplace] **に移動し** 、[ビバ] を検索します。
4. [ビバ] タイルラーニング選択します。
5. [ **インストール**] を選択します。
6. ボックスをオンにして、利用規約に同意し、[インストール] を **選択します**。
7. [今 **すぐ構成する] を選択します**。
8. クライアント ID、シークレット、ポータル名、および基本 URL をコピーします。 その後、戻ってビバを検索します。
9. 切り替えボタンをスライドして、ビバ ラーニング有効にします。

## <a name="configure-in-microsoft-365-admin-center"></a>[構成] Microsoft 365 管理センター

1. 自分のアカウントに[ログインMicrosoft 365 管理センター。](https://admin.microsoft.com)
2. [組織の設定 **設定]** の順 **に移動します**。 [ビバ ラーニング] を選択し、パネルで Cornerstone OnDemand を有効にします。
3. コーナーストーン ポータルから取得した構成の詳細を入力します。

    >[!NOTE]
    >表示名はカルーセルの名前で、Viva ラーニング で組織の Cornerstone ラーニング コンテンツが表示されます。 名前を入力しない場合は、既定の名前 "Cornerstone OnDemand" が表示されます。

4. [保存 **] を選択** して、ビバ のコーナーストーン コンテンツをアクティブラーニング。 コンテンツがビバ アプリに表示されるのに最大 24 時間かかるラーニングがあります。

## <a name="data-residency"></a>データ所在地

テナント のメタデータは、データ ストアに集中して格納され、地域固有のデータ ストアには格納されません。

## <a name="roles-and-permissions"></a>ロールと権限

現在、組織内のすべてのユーザーは、テナント固有のすべてのコースを検出できますが、アクセスできるコースのみを使用できます。 ロールとアクセス許可に基づくユーザー固有のコンテンツ検出は、今後のリリースに向け計画されています。
