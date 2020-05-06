---
title: コネクタをセットアップして LinkedIn データをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: LinkedIn データを Microsoft 365 にインポートするためのコネクタを設定して、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンスツールを使用できるようにします。
ms.openlocfilehash: 7d88d366ea19be7d158a04edc7d7fb11dca7bab9
ms.sourcegitcommit: e55e4747d3b838baacab8985aefc24aac245c431
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44043348"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>コネクタをセットアップして LinkedIn データをアーカイブする

Microsoft 365 コンプライアンスセンターのコネクタを使用して、LinkedIn の会社のページからデータをインポートおよびアーカイブします。 コネクタを設定して構成すると、24時間ごとに、特定の LinkedIn 会社のページのアカウントに接続されます。 コネクタは、会社のページに投稿されたメッセージを電子メールメッセージに変換し、そのアイテムを Microsoft 365 のメールボックスにインポートします。

LinkedIn 会社のページデータをメールボックスに格納した後、Microsoft 365 のコンプライアンス機能 (訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、Microsoft 365 アイテム保持ポリシーなど) を LinkedIn データに適用することができます。 たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、高度な電子情報開示ケースの保管担当者にストレージメールボックスを関連付けたりすることができます。 Microsoft 365 で LinkedIn データをインポートおよびアーカイブするためのコネクタを作成することで、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="before-you--begin"></a>はじめに

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Microsoft 365 グローバル管理者の資格情報でサインインし、要求を承諾します。

- LinkedIn Company Page コネクタを作成したユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンスセンターの [**データコネクタ**] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。

- アーカイブする LinkedIn の会社のページの管理者である LinkedIn ユーザーアカウントのサインイン資格情報 (電子メールアドレスまたは電話番号とパスワード) を持っている必要があります。 これらの資格情報を使用して、コネクタを設定するときに LinkedIn にサインインします。

## <a name="create-a-linkedin-connector"></a>LinkedIn コネクタを作成する

1. に移動<https://compliance.microsoft.com>して、[**データコネクタ** > **LinkedIn の会社のページ**] をクリックします。

2. [ **LinkedIn company pages** product] ページで、[**コネクタの追加**] をクリックします。

3. [**サービス利用規約**] ページで、[**同意**する] を選択します。

4. [ **Linkedin を使用**してサインインする] ページで、[ **linkedin でサインイン**] をクリックします。

   LinkedIn サインインページが表示されます。

   ![LinkedIn サインインページ](../media/LinkedInSigninPage.png)

5. LinkedIn の [サインイン] ページで、アーカイブする会社のページに関連付けられている LinkedIn アカウントの電子メールアドレス (または電話番号) とパスワードを入力し、[**サインイン**] をクリックします。

   ウィザードページが、サインインしたアカウントに関連付けられているすべての LinkedIn 会社のページの一覧と共に表示されます。 コネクタは、1つの会社のページに対してのみ構成できます。 組織に複数の LinkedIn Company ページがある場合は、それぞれに対してコネクタを作成する必要があります。

   ![LinkedIn 会社のページの一覧を含むページが表示されます。](../media/LinkedInSelectCompanyPage.png)

6. アイテムをアーカイブする会社のページを選択し、[**次へ**] をクリックします。

7. [**記憶域の場所の選択**] ページで、ボックス内のをクリックし、LinkedIn アイテムをインポートする Microsoft 365 メールボックスの電子メールアドレスを選択して、[**次へ**] をクリックします。 アイテムは、このメールボックスの受信トレイフォルダーにインポートされます。

8. [**管理者に同意**する] で、[**同意を提供**する] をクリックし、手順に従います。 組織内のデータにアクセスするために Office 365 Import service への同意を提供するには、グローバル管理者である必要があります。

9. [**次**へ] をクリックしてコネクタの設定を確認し、[**完了**] をクリックしてコネクタのセットアップを完了します。

コネクタを作成したら、[**データコネクタ**] ページに戻り、新しいコネクタのインポート処理の進行状況を確認できます (コネクタの一覧を更新する必要がある場合は、[**更新**] を選択します)。 [**状態**] 列の値は、**開始を待機**しています。 最初のインポート処理が開始されるまでに最大で24時間かかります。 コネクタが初めて実行され、LinkedIn アイテムがインポートされると、コネクタは24時間ごとに1回実行され、過去24時間に LinkedIn Company ページに作成された新しいアイテムをインポートします。

詳細を表示するには、[**データコネクタ**] ページの一覧でコネクタを選択して、フライアウトページを表示します。 [**状態**] の下に表示される日付の範囲は、コネクタの作成時に選択された年齢フィルターを示します。

## <a name="more-information"></a>詳細情報

LinkedIn アイテムは、Microsoft 365 のストレージメールボックスの受信トレイの LinkedIn サブフォルダーにインポートされます。 電子メールメッセージとして表示されます。
