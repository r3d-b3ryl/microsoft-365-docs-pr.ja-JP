---
title: MS SQL Database からデータをアーカイブするコネクタを設定する
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
description: 管理者は、MS SQL Database からデータをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 686575877f788a2c2662024d5fac3e425d08c500
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620384"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>MS SQL Database からデータをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、MS SQL Database から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Globanet は、XML 構成ファイルを使用してデータベースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された MS SQL Database Importer コネクタを提供します。 コネクタは、MS SQL Database のコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

ユーザー メールボックスに保存されている MS SQL Database のコンテンツの後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 MS SQL データベース コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-the-ms-sql-data"></a>MS サービス データのアーカイブSQL概要

次の概要では、コネクタを使用して MICROSOFT 365 の MS SQLアーカイブするプロセスについて説明します。

![MS データのアーカイブ SQLワークフロー](../media/MSSQLDatabaseConnectorWorkflow.png)

1. 組織は MS SQL データベース プロバイダーと共同で MS データベース サイトをセットアップSQL構成します。

2. 24 時間ごとに MS SQLデータベース アイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、このコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成する MS SQL Database Importer コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にメッセージを転送します。

4. コネクタは、ステップ 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された MS SQL Database アイテムを特定のユーザーのメールボックス [にインポート](#step-3-map-users-and-complete-the-connector-setup)します。 MS SQL **Database Importer** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 MS SQL Database のすべてのアイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 1 で MS SQL Database Importer コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。 この役割は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループには割り当てられていない。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>手順 1: MS データベース インSQLコネクタをセットアップする

最初の手順では、Microsoft365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、MS SQL Database のコネクタを作成します。

1. [データ [https://compliance.microsoft.com](https://compliance.microsoft.com) コネクタMS SQL  >  **Database Importer] に移動してクリックします**。

2. **[MS SQL Database Importer** 製品の説明] ページで、[新しいコネクタの追加 **] をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで MS SQL Database Importer コネクタを構成する

2 番目の手順は、Merge1 サイトで MS SQL Database Importer コネクタを構成することです。 データベース インデクサーで MS SQL構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)。

[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。

1. [Map **MS SQL Database Importer users to Microsoft 365 users]** ページで、自動ユーザー マッピングを有効にしてください。 MS SQL データベース アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>手順 4: MS データベース インSQLコネクタを監視する

MS SQL Database Importer コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の <https://compliance.microsoft.com/> ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ]** タブをクリックし **、MS SQL Database** **Importer** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
