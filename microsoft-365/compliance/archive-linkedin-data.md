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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がネイティブ コネクタを&して LinkedIn Company Page からデータをインポートする方法について説明Microsoft 365。
ms.openlocfilehash: 944a8bcbd06a07653ccf5e98e28807d279b66023
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322199"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>コネクタをセットアップして LinkedIn データをアーカイブする

LinkedIn Company ページからデータをインポートMicrosoft 365 コンプライアンス センターアーカイブするには、このページのコネクタを使用します。 コネクタを設定して構成した後、24 時間に 1 回、特定の LinkedIn Company ページのアカウントに接続します。 コネクタは、[会社] ページに投稿されたメッセージを電子メール メッセージに変換し、それらのアイテムをメールボックスにインポートMicrosoft 365。

LinkedIn Company ページ データをメールボックスに格納した後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を LinkedIn データに適用できます。 たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、ストレージ メールボックスを保管担当者に関連付Advanced eDiscoveryできます。 LinkedIn データをインポートおよびアーカイブするコネクタを作成するとMicrosoft 365政府および規制ポリシーに準拠し、組織を支援できます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- LinkedIn Company Page コネクタを作成するユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- アーカイブする LinkedIn Company Page の管理者である LinkedIn ユーザー アカウントのサインイン資格情報 (電子メール アドレスまたは電話番号とパスワード) が必要です。 コネクタをセットアップするときに、これらの資格情報を使用して LinkedIn にサインインします。

- LinkedIn コネクタは、1 日に合計 200,000 アイテムをインポートできます。 1 日に 200,000 件を超える LinkedIn アイテムがある場合、それらのアイテムはいずれも 1 日にインポートMicrosoft 365。

## <a name="create-a-linkedin-connector"></a>LinkedIn コネクタの作成

1. [データ コネクタ<https://compliance.microsoft.com>**LinkedIn Company] ページに移動し、[データ コネクタ] をクリックします** > 。

2. **LinkedIn 会社ページの製品ページ** で、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **選択します**。

4. [ **LinkedIn でサインイン] ページで、[LinkedIn** で **サインイン] をクリックします**。

   LinkedIn サインイン ページが表示されます。

   ![LinkedIn サインイン ページ。](../media/LinkedInSigninPage.png)

5. [LinkedIn サインイン] ページで、アーカイブする会社ページに関連付けられた LinkedIn アカウントの電子メール アドレス (または電話番号) とパスワードを入力し、[サインイン] **をクリックします**。

   サインインしたアカウントに関連付けられているすべての LinkedIn Company Pages の一覧がウィザード ページに表示されます。 コネクタを構成できるのは、1 つの会社ページのみです。 組織に複数の LinkedIn Company Pages がある場合は、それぞれのコネクタを作成する必要があります。

   ![LinkedIn Company Pages のリストを含むページが表示されます。](../media/LinkedInSelectCompanyPage.png)

6. アイテムをアーカイブする会社ページを選択し、[次へ] をクリック **します**。

7. [保存 **場所の選択**] ページで、ボックス内をクリックし、LinkedIn アイテムをインポートする Microsoft 365 メールボックスの電子メール アドレスを選択し、[次へ] をクリック **します**。 アイテムは、このメールボックスの受信トレイ フォルダーにインポートされます。

8. [ **次へ]** をクリックしてコネクタの設定を確認し、[完了] を **クリックして** コネクタのセットアップを完了します。

コネクタを作成した後、[データ コネクタ] ページに戻って、新しいコネクタのインポート プロセスの進行状況を確認できます (コネクタの一覧を更新するには、必要に応じて [更新] を選択します)。 [状態] 列の **値が** [開始 **待ち] です**。 最初のインポート プロセスを開始するには、最大 24 時間かかります。 コネクタが初めて実行され、LinkedIn アイテムがインポートされると、コネクタは 24 時間に 1 回実行され、過去 24 時間に LinkedIn Company Page で作成された新しいアイテムがインポートされます。

詳細を表示するには、[データ コネクタ] ページの一覧でコネクタを **選択して、** フライアウト ページを表示します。 [ **状態]** で、表示される日付範囲は、コネクタの作成時に選択された年齢フィルターを示します。

## <a name="more-information"></a>詳細

LinkedIn アイテムは、ストレージ メールボックスの受信トレイにある LinkedIn サブフォルダーにインポートMicrosoft 365。 電子メール メッセージとして表示されます。