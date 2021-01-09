---
title: コネクタをセットアップして LinkedIn データをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がネイティブ コネクタを使用&して LinkedIn Company Page から Microsoft 365 にデータをインポートする方法について説明します。
ms.openlocfilehash: 9f6cb2c6d5c47559f1fda13b6d03bfed3afe6fa2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790181"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>コネクタをセットアップして LinkedIn データをアーカイブする

Microsoft 365 コンプライアンス センターのコネクタを使用して、LinkedIn Company ページからデータをインポートおよびアーカイブします。 コネクタを設定して構成すると、24 時間ごとに 1 回、特定の LinkedIn Company ページのアカウントに接続されます。 コネクタは、会社のページに投稿されたメッセージを電子メール メッセージに変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

LinkedIn Company ページのデータがメールボックスに保存された後、Microsoft 365 コンプライアンス機能 (訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 アイテム保持ポリシーなど) を LinkedIn データに適用できます。 たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、Advanced eDiscovery ケースの保管担当者にストレージ メールボックスを関連付けできます。 Microsoft 365 で LinkedIn データをインポートおよびアーカイブするためのコネクタを作成すると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- LinkedIn Company Page コネクタを作成するユーザーには、Exchange Online の "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割が割り当てられている必要があります。 これは、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

- アーカイブする LinkedIn 会社ページの管理者である LinkedIn ユーザー アカウントのサインイン資格情報 (電子メール アドレスまたは電話番号とパスワード) が必要です。 これらの資格情報を使用して、コネクタを設定するときに LinkedIn にサインインします。

- LinkedIn コネクタは、1 日に合計 200,000 アイテムをインポートできます。 1 日に 200,000 を超える LinkedIn アイテムがある場合、それらのアイテムは Microsoft 365 にインポートされません。

## <a name="create-a-linkedin-connector"></a>LinkedIn コネクタを作成する

1. <https://compliance.microsoft.com>[LinkedIn Company] ページに移動し、[**データ コネクタ**  >  **] をクリックします**。

2. **LinkedIn 会社ページの製品ページで、[** コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **選択します**。

4. **[LinkedIn でサインイン] ページで、[LinkedIn** でサインイン]**をクリックします**。

   LinkedIn サインイン ページが表示されます。

   ![LinkedIn サインイン ページ](../media/LinkedInSigninPage.png)

5. LinkedIn サインイン ページで、アーカイブする会社のページに関連付けられている LinkedIn アカウントの電子メール アドレス (または電話番号) とパスワードを入力し、[サインイン] をクリック **します**。

   ウィザード ページが表示され、サインインしたアカウントに関連付けられているすべての LinkedIn 会社ページの一覧が表示されます。 コネクタは、1 つの会社ページにのみ構成できます。 組織に複数の LinkedIn 会社ページがある場合は、それぞれにコネクタを作成する必要があります。

   ![LinkedIn Company Pages のリストを含むページが表示される](../media/LinkedInSelectCompanyPage.png)

6. アイテムをアーカイブする会社のページを選択し、[次へ] をクリック **します**。

7. [ストレージ **の場所** の選択] ページで、ボックスをクリックし、LinkedIn アイテムのインポート先の Microsoft 365 メールボックスの電子メール アドレスを選択し、[次へ] をクリック **します。** アイテムは、このメールボックスの受信トレイ フォルダーにインポートされます。

8. [ **次へ]** をクリックしてコネクタの設定を確認し、[完了] **をクリックして** コネクタのセットアップを完了します。

コネクタを作成した後、[データ コネクタ] ページに戻り、新しいコネクタのインポート プロセスの進行状況を確認できます (必要に応じて [最新の情報に更新] を選択してコネクタの一覧を更新します)。 The value in the **Status** column is **Waiting to start**. 最初のインポート プロセスが開始するには、最大 24 時間かかります。 初めてコネクタを実行して LinkedIn アイテムをインポートした後、コネクタは 24 時間ごとに 1 回実行され、過去 24 時間以内に LinkedIn Company Page で作成された新しいアイテムがインポートされます。

詳細を表示するには、[データ コネクタ] ページの一覧でコネクタを **選択して、** フライアウト ページを表示します。 [ **状態]** の下に表示される日付範囲は、コネクタの作成時に選択された年齢フィルターを示します。

## <a name="more-information"></a>詳細

LinkedIn アイテムは、Microsoft 365 のストレージ メールボックスの受信トレイにある LinkedIn サブフォルダーにインポートされます。 電子メール メッセージとして表示されます。
