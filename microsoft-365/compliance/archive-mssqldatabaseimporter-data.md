---
title: MS SQL データベースからデータをアーカイブするためのコネクタを設定する
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
description: 管理者は、MS SQL データベースからデータをインポートしてアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 576ba38616b9a6a9c1b0e7c78c5e8d03c5a0e9df
ms.sourcegitcommit: 95b85a1fdf43e3f0839483fa22e279262703f15f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "49407301"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>MS SQL データベースからデータをアーカイブするためのコネクタを設定する

Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、MS SQL データベースから Microsoft 365 組織のユーザーメールボックスにデータをインポートし、アーカイブします。 Globanet は、XML 構成ファイルを使用してデータベースからアイテムを取得するために構成された MS SQL データベースインポーターコネクタを提供し、それらのアイテムを Microsoft 365 にインポートします。 コネクタは、MS SQL データベースのコンテンツを電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーメールボックスにインポートします。

ユーザーのメールボックスに格納されている MS SQL Database からコンテンツを作成すると、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Microsoft 365 でデータをインポートおよびアーカイブするために MS SQL データベースコネクタを使用することにより、組織は政府および規制ポリシーに準拠したままにすることができます。

## <a name="overview-of-archiving-the-ms-sql-data"></a>MS SQL データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 で MS SQL データをアーカイブするプロセスについて説明します。

![MS SQL データのアーカイブワークフロー](../media/MSSQLDatabaseConnectorWorkflow.png)

1. 組織は MS sql データベースプロバイダーと連携して、MS SQL データベースサイトをセットアップし、構成します。

2. 24時間ごとに、MS SQL データベースアイテムは Globanet Merge1 サイトにコピーされます。 コネクタは、このコンテンツを電子メールメッセージの形式に変換します。

3. Microsoft 365 コンプライアンスセンターで作成した MS SQL データベースのインポーターコネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。

4. このコネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換された MS SQL データベースアイテムを特定のユーザーのメールボックスにインポートします。 ユーザーのメールボックスに、 **MS SQL データベースインポーター** という名前の受信トレイフォルダー内のサブフォルダーが作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 MS SQL データベースのすべてのアイテムには、このプロパティが含まれています。このプロパティには、アイテムのすべての参加者の電子メールアドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 アカウントを作成するには、 [Globanet カスタマーサポート](https://globanet.com/contact-us/)に問い合わせてください。 手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順1で MS SQL データベースインポーターコネクタを作成したユーザー (および手順3で完了します) は、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。 この役割は、Microsoft 365 コンプライアンスセンターの [データコネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>手順 1: MS SQL データベースインポーターコネクタを設定する

最初の手順として、Microsoft365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、MS SQL データベース用のコネクタを作成します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) し、[**データコネクタ**  >  **MS SQL データベースインポーター**] をクリックします。

2. [ **MS SQL データベースインポーター** の製品の説明] ページで、[ **新しいコネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインして、コネクタを構成します。

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイト上の MS SQL データベースインポーターコネクタを構成する

2番目の手順は、Merge1 サイトの MS SQL データベースインポーターコネクタを構成することです。 MS SQL データベースインポーターを構成する方法については、「 [Merge1 サードパーティコネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)」を参照してください。

[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップしてコネクタのセットアップを完了する

ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。

1. [ **Microsoft 365 ユーザーにマップする MS SQL データベースインポーターユーザー** ] ページで、[自動ユーザーマッピング] を有効にします。 MS SQL データベースのアイテムには、 *電子メール* というプロパティが含まれています。このプロパティには、組織内のユーザーの電子メールアドレスが含まれています。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。

2. [ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。 Microsoft サイトにリダイレクトされます。 同意を得るには、[ **承諾** ] をクリックします。

   組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

3. [ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>手順 4: MS SQL データベースインポーターコネクタを監視する

MS SQL データベースインポーターコネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。

1. <https://compliance.microsoft.com/>左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。

2. [**コネクタ**] タブをクリックし、[ **MS SQL データベース****インポーター** コネクタ] を選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。

3. [ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きいアイテムのサポートは、後日提供されます。
