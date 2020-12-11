---
title: Microsoft 365 の MS クライアント データで Cisco Jabber をアーカイブSQLコネクタを設定する
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
ms.collection: M365-security-compliance
description: 管理者は、Microsoft 365 の Globanet から Cisco Jabber データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 2790a29cdfa090372976d78de2e5cc5e5c5ce12e
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620043"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>Cisco Jabber データをアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Cisco Jabber プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Globanet は、1 対 1 のチャット メッセージやグループ チャットなど、Jabber の MS SQL データベースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Cisco Jabber](https://globanet.com/jabber/) コネクタを提供します。 コネクタは、Cisco Jabber の MS SQL データベースからデータを取得して処理し、コンテンツをユーザーの Cisco Jabber アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Cisco Jabber データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Cisco Jabber コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-cisco-jabber-data"></a>Cisco Jabber データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Cisco Jabber データをアーカイブするプロセスについて説明します。

![Cisco Jabber データのアーカイブ ワークフロー](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. 組織は Cisco と一緒に MS SQL Database で Cisco Jabber をセットアップおよび構成します。

2. 24 時間ごとに、Cisco Jabber アイテムが MS SQL Database から Globanet Merge1 サイトにコピーされます。 コネクタは、チャット メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成する Cisco Jabber コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にアイテムを転送します。

4. コネクタとしての自動ユーザー マッピングは、手順 3 で説明した *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。 MS SQL 上の **Cisco Jabber** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、メッセージ アイテムがフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての Cisco Jabber アイテムには、このプロパティが含まれているので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact/)。 このアカウントは、手順 1 でコネクタを作成するときにサインインします。

- 手順 1 でコネクタSQLする前に、Jabber アイテムを取得するために MS データベース データベースをセットアップします。 手順 2 で Cisco Jabber コネクタを構成するときに、MS SQL Database の接続設定を指定します。 詳細については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。

- 手順 1 で Cisco Jabber コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てられている必要があります。 この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていない。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>手順 1: Cisco Jabber コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの **Data Connectors** にアクセスし、MS SQL データに Cisco Jabber のコネクタを作成することです。

1. MS アプリケーション [https://compliance.microsoft.com](https://compliance.microsoft.com/) の [**データ** コネクタ Cisco  >  **Jabber] に移動してSQL。**

2. MS アプリケーション **の製品の説明ページで、Cisco Jabber SQL** コネクタの追加を **クリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで Cisco Jabber コネクタを構成する

2 番目の手順は、Globanet Merge1 サイトの MS SQLコネクタで Cisco Jabber を構成することです。 MS SQL コネクタで Cisco Jabber を構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。

[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. MS サーバー **の Map Cisco Jabber でSQL Microsoft 365** ユーザーへのマッピング] ページで、自動ユーザー マッピングを有効にしてください。 MS の Cisco Jabber SQLアイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>手順 4: Cisco Jabber コネクタを監視する

MS SQL コネクタで Cisco Jabber を作成すると、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブを** クリックし、MS SQL Cisco **Jabber** を選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
