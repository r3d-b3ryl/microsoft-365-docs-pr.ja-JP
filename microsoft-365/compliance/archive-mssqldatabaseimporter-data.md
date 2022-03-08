---
title: MS データベースからデータをアーカイブするコネクタをSQLする
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
ms.collection: M365-security-compliance
description: 管理者は、MS データベースからデータをインポートおよびアーカイブするコネクタをSQLできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: f00b76cb2199d1af9daca58e86ad7cd2009c2031
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315695"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>MS データベースからデータをアーカイブするコネクタをSQLする

Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、MS SQL Database から Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas は、XML 構成ファイルを使用してデータベースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された MS SQL データベース インポート コネクタを提供します。 コネクタは、MS SQL データベースから電子メール メッセージ形式にコンテンツを変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

MS SQL データベースのコンテンツをユーザー メールボックスに保存した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Ms SQL データベース コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-the-ms-sql-data"></a>MS データのアーカイブSQL概要

次の概要では、コネクタを使用して Microsoft 365 の MS SQLをアーカイブするプロセスについて説明します。

![MS データのアーカイブ ワークフロー SQLします。](../media/MSSQLDatabaseConnectorWorkflow.png)

1. 組織は MS データベース プロバイダーとSQLして、MS データベース データベース サイトをSQLします。

2. 24 時間に 1 回、MS SQLデータベース アイテムが Veritas Merge1 サイトにコピーされます。 コネクタは、このコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成する MS SQL データベース インポート コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage の場所にメッセージを転送します。

4. コネクタは、ステップ [3](#step-3-map-users-and-complete-the-connector-setup) で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された MS SQL データベース アイテムを特定のユーザーのメールボックスにインポートします。 MS という名前の受信トレイ フォルダー **SQLデータベース** インポートツールがユーザー メールボックスに作成され、そのフォルダーにアイテムがインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 MS データベースのすべてのアイテムSQLこのプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 アカウントを作成するには、 [Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で MS SQL データベース インポート コネクタを作成し、手順 3 で完了するユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「Microsoft 365 コンプライアンス センターのアクセス許可」の「カスタム役割グループの作成」 [セクションを参照してください](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この Veritas データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でパブリック プレビュー中です。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあるサードパーティ 製システムに組織の顧客データを保存、送信、処理する必要がある場合があります。そのため、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象とはなってない場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>手順 1: データベース インSQL MS コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、MS SQLします。

1. [データベース インポート [https://compliance.microsoft.com](https://compliance.microsoft.com) ] に移動し、[ **データ コネクタ** > **MS] SQLクリックします**。

2. [ **MS データベース インポートSQL] ページ** で、[新しいコネクタの追加 **] をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトSQL MS データベース インポート コネクタを構成する

2 番目の手順は、Merge1 サイトSQL MS データ インポート コネクタを構成することです。 データベース インバーの MS SQL構成方法については、「Merge1 サード パーティ コネクタ ユーザー ガイド [」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)。

[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次の手順を実行します。

1. [ **データベース インポートユーザーを Microsoft 365 SQLに** マップする] ページで、自動ユーザー マッピングを有効にします。 [MS SQL] データベース アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>手順 4: データベース インポート コネクタの MS SQL監視する

データベース インポート コネクタの MS SQL作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側のナビゲーション <https://compliance.microsoft.com/> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、**MS SQL データベース**  インポート コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。