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
description: 管理者がネイティブ コネクタを&して LinkedIn Company Page からデータをインポートする方法について説明Microsoft 365。
ms.openlocfilehash: 2d34a424b11c9489d54a87bfb9f81de9a74ed5e6
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58571497"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>コネクタをセットアップして LinkedIn データをアーカイブする

LinkedIn Company ページからデータをインポートMicrosoft 365 コンプライアンス センターアーカイブするには、このページのコネクタを使用します。 コネクタを設定して構成した後、24 時間に 1 回、特定の LinkedIn Company ページのアカウントに接続します。 コネクタは、[会社] ページに投稿されたメッセージを電子メール メッセージに変換し、それらのアイテムをメールボックスにインポートMicrosoft 365。

LinkedIn Company ページ データをメールボックスに格納した後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を LinkedIn データに適用できます。 たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、ストレージ メールボックスを保管担当者に関連付Advanced eDiscoveryできます。 LinkedIn データをインポートおよびアーカイブするコネクタを作成すると、Microsoft 365規制ポリシーに準拠し、組織を支援できます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- LinkedIn Company Page コネクタを作成するユーザーには、ユーザーにメールボックスインポートエクスポートの役割が割りExchange Online。 これは、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

- アーカイブする LinkedIn Company Page の管理者である LinkedIn ユーザー アカウントのサインイン資格情報 (電子メール アドレスまたは電話番号とパスワード) が必要です。 コネクタをセットアップするときに、これらの資格情報を使用して LinkedIn にサインインします。

- LinkedIn コネクタは、1 日に合計 200,000 アイテムをインポートできます。 1 日に 200,000 件を超える LinkedIn アイテムがある場合、それらのアイテムはいずれもそのアイテムにインポートMicrosoft 365。

## <a name="create-a-linkedin-connector"></a>LinkedIn コネクタの作成

1. [データ コネクタ <https://compliance.microsoft.com> ] **[LinkedIn Company]** ページ  >  **に移動し、[データ コネクタ] をクリックします**。

2. **LinkedIn 会社ページの製品ページ** で、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **選択します**。

4. **[LinkedIn でサインイン] ページで、[LinkedIn** で **サインイン] をクリックします**。

   LinkedIn サインイン ページが表示されます。

   ![LinkedIn サインイン ページ。](../media/LinkedInSigninPage.png)

5. [LinkedIn サインイン] ページで、アーカイブする会社ページに関連付けられている LinkedIn アカウントの電子メール アドレス (または電話番号) とパスワードを入力し、[サインイン] をクリック **します**。

   サインインしたアカウントに関連付けられているすべての LinkedIn Company Pages の一覧がウィザード ページに表示されます。 コネクタを構成できるのは、1 つの会社ページのみです。 組織に複数の LinkedIn Company Pages がある場合は、それぞれのコネクタを作成する必要があります。

   ![LinkedIn Company Pages のリストを含むページが表示されます。](../media/LinkedInSelectCompanyPage.png)

6. アイテムをアーカイブする会社ページを選択し、[次へ] を **クリックします**。

7. [保存 **場所の選択**] ページで、ボックス内をクリックし、LinkedIn アイテムをインポートする Microsoft 365 メールボックスの電子メール アドレスを選択し、[次へ] をクリック **します**。 アイテムは、このメールボックスの受信トレイ フォルダーにインポートされます。

8. [ **次へ]** をクリックしてコネクタの設定を確認し、[完了] を **クリックして** コネクタのセットアップを完了します。

コネクタを作成した後、[データ コネクタ] ページに戻って、新しいコネクタのインポート プロセスの進行状況を確認できます (コネクタの一覧を更新するには、必要に応じて [更新] を選択します)。 [状態] 列の **値は** 、[開始 **を待機中] です**。 最初のインポート プロセスを開始するには、最大 24 時間かかります。 コネクタが初めて実行され、LinkedIn アイテムがインポートされると、コネクタは 24 時間に 1 回実行され、過去 24 時間に LinkedIn Company Page で作成された新しいアイテムがインポートされます。

詳細を表示するには、[データ コネクタ] ページの一覧でコネクタを **選択して、** フライアウト ページを表示します。 [ **状態]** で、表示される日付範囲は、コネクタの作成時に選択された年齢フィルターを示します。

## <a name="more-information"></a>詳細情報

LinkedIn アイテムは、ストレージ メールボックスの受信トレイにある LinkedIn サブフォルダーにインポートMicrosoft 365。 電子メール メッセージとして表示されます。