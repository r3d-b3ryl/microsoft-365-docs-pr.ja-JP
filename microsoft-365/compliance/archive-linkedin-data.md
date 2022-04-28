---
title: コネクタをセットアップして LinkedIn データをアーカイブする
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 04/06/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がネイティブ コネクタ&使用して LinkedIn Company Page からMicrosoft 365にデータをインポートする方法について説明します。
ms.openlocfilehash: 352e33ed4c78dd57533312e3f7c37bb3357216f3
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095974"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>コネクタをセットアップして LinkedIn データをアーカイブする

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview コンプライアンス ポータルのコネクタを使用して、LinkedIn Company ページからデータをインポートおよびアーカイブします。 コネクタを設定して構成すると、24 時間に 1 回、特定の LinkedIn Company ページのアカウントに接続されます。 コネクタは、会社のページに投稿されたメッセージを電子メール メッセージに変換し、それらのアイテムをMicrosoft 365のメールボックスにインポートします。

LinkedIn Company ページ のデータがメールボックスに格納されたら、訴訟ホールド、コンテンツ検索、In-Placeアーカイブ、監査、Microsoft 365アイテム保持ポリシーなどの Microsoft Purview 機能を LinkedIn データに適用できます。 たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、Microsoft Purview 電子情報開示 (プレミアム) ケースでストレージ メールボックスを保管担当者に関連付けることができます。 Microsoft 365で LinkedIn データをインポートおよびアーカイブするためのコネクタを作成すると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- LinkedIn Company Page コネクタを作成するユーザーには、データ コネクタ管理者ロールが割り当てられている必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、 [Microsoft Purview コンプライアンス ポータル](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)のアクセス許可の「カスタム ロール グループの作成」セクションを参照してください。

- アーカイブする LinkedIn Company Page の管理者である LinkedIn ユーザー アカウントのサインイン資格情報 (電子メール アドレスまたは電話番号とパスワード) が必要です。 コネクタを設定するときに、これらの資格情報を使用して LinkedIn にサインインします。

- LinkedIn コネクタは、1 日に合計 200,000 個のアイテムをインポートできます。 1 日に 200,000 個を超える LinkedIn アイテムがある場合、これらの項目はMicrosoft 365にインポートされません。

## <a name="create-a-linkedin-connector"></a>LinkedIn コネクタを作成する

1. **Data connectorsLinkedIn** >  **Company ページに**<https://compliance.microsoft.com>移動してクリックします。

2. **LinkedIn 企業ページ** の製品ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] を選択します。

4. [ **LinkedIn でサインイン** ] ページで、[ **LinkedIn でサインイン**] をクリックします。

   LinkedIn サインイン ページが表示されます。

   ![LinkedIn サインイン ページ。](../media/LinkedInSigninPage.png)

5. LinkedIn サインイン ページで、アーカイブする会社のページに関連付けられている LinkedIn アカウントの電子メール アドレス (または電話番号) とパスワードを入力し、[ **サインイン**] をクリックします。

   サインインしたアカウントに関連付けられているすべての LinkedIn Company Pages の一覧がウィザード ページに表示されます。 コネクタは、1 つの会社ページに対してのみ構成できます。 組織に複数の LinkedIn Company Pages がある場合は、それぞれにコネクタを作成する必要があります。

   ![LinkedIn Company Pages の一覧を含むページが表示されます。](../media/LinkedInSelectCompanyPage.png)

6. アイテムをアーカイブする会社のページを選択し、[ **次へ**] をクリックします。

7. [**ストレージの場所の選択**] ページで、ボックスをクリックし、LinkedIn アイテムのインポート先となるMicrosoft 365 メールボックスのメール アドレスを選択し、[**次へ**] をクリックします。 アイテムは、このメールボックスの受信トレイ フォルダーにインポートされます。

8. [ **次へ** ] をクリックしてコネクタの設定を確認し、[ **完了]** をクリックしてコネクタの設定を完了します。

コネクタを作成したら、[ **データ コネクタ** ] ページに戻って、新しいコネクタのインポート プロセスの進行状況を確認できます (必要に応じて **[更新]** を選択してコネクタの一覧を更新します)。 **[状態]** 列の値は[**開始待ち]** です。 最初のインポート プロセスを開始するには、最大で 24 時間かかります。 コネクタを初めて実行して LinkedIn アイテムをインポートすると、コネクタは 24 時間に 1 回実行され、前の 24 時間に LinkedIn Company Page で作成された新しいアイテムがインポートされます。

詳細を表示するには、[ **データ** コネクタ] ページの一覧でコネクタを選択してポップアップ ページを表示します。 **[状態]** に表示される日付範囲は、コネクタの作成時に選択された年齢フィルターを示します。

## <a name="more-information"></a>詳細

LinkedIn アイテムは、Microsoft 365のストレージ メールボックスの受信トレイの LinkedIn サブフォルダーにインポートされます。 これらは電子メール メッセージとして表示されます。