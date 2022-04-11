---
title: Microsoft 365でSQL データをアーカイブするコネクタを設定する
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
description: 17a-4 SQL DataParser コネクタを設定して使用して、Microsoft 365でSQLデータをインポートおよびアーカイブする方法について説明します。
ms.openlocfilehash: 1932e7830c1e23a07dbd9d6cbb968c3f12193d54
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761541"
---
# <a name="set-up-a-connector-to-archive-sql-data"></a>SQL データをアーカイブするコネクタを設定する

17a-4 LLC の [SQL DataParser](https://www.17a-4.com/sql-dataparser/) を使用して、SQL データベースからMicrosoft 365組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には、サード パーティのデータ ソースからアイテムをキャプチャし、それらの項目をMicrosoft 365にインポートするように構成されたSQL コネクタが含まれています。 SQL DataParser コネクタは、SQLデータを電子メール メッセージ形式に変換し、それらのアイテムをMicrosoft 365のユーザー メールボックスにインポートします。

SQLデータがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどのMicrosoft 365コンプライアンス機能を適用できます。 SQL コネクタを使用してMicrosoft 365のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-sql-data"></a>SQL データのアーカイブの概要

次の概要では、データ コネクタを使用してMicrosoft 365でSQLデータをアーカイブするプロセスについて説明します。

![17a から 4 のSQL データのアーカイブ ワークフロー。](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. 組織は 17a-4 と連携して、SQL DataParser を設定および構成します。

2. 定期的に、SQL項目は DataParser によって収集されます。 DataParser では、メッセージの内容も電子メール メッセージ形式に変換されます。

3. Microsoft 365 コンプライアンス センターで作成するSQL DataParser コネクタは DataParser に接続し、メッセージを Microsoft クラウド内の安全なAzure Storageの場所に転送します。

4. **SQL DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、SQLアイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべてのSQL項目には、すべての参加者の電子メール アドレスが設定されたこのプロパティが含まれています。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- Microsoft コネクタの DataParser アカウントを作成します。 これを行うには、 [17a-4 LLC](https://www.17a-4.com/contact/) にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 1 で SQL DataParser コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理者ロールを割り当てる必要があります。 このロールは、Microsoft 365 コンプライアンス センターの **[データ コネクタ**] ページにコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者は、カスタム役割グループを作成し、Data Connector 管理者ロールを割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft 365 コンプライアンス センターのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この 17a-4 データ コネクタは、Microsoft 365米国政府機関クラウドのGCC環境で使用できます。 サード パーティのアプリケーションとサービスには、組織の顧客データを、Microsoft 365 インフラストラクチャの外部にあるサード パーティ システムに格納、送信、処理する必要があるため、Microsoft 365コンプライアンスとデータ保護のコミットメントの対象とされません。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-a-sql-dataparser-connector"></a>手順 1: SQL DataParser コネクタを設定する

最初の手順では、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、SQL データ用の 17a-4 コネクタを作成します。

1. **DataParser** >  に<https://compliance.microsoft.com>移動して[データ コネクタ]**SQL** クリックします。

2. **SQL DataParser 製品の** 説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. 17a-4 アカウントにサインインし、SQL DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-sql-dataparser-connector"></a>手順 2: SQL DataParser コネクタを構成する

17a-4 サポートと連携して、SQL DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

SQL DataParser コネクタは、Microsoft 365にデータをインポートする前に、ユーザーをMicrosoft 365電子メール アドレスに自動的にマップします。

## <a name="step-4-monitor-the-sql-dataparser-connector"></a>手順 4: SQL DataParser コネクタを監視する

SQL DataParser コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の <https://compliance.microsoft.com> ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [**コネクタ**] タブをクリックし、作成した SQL DataParser コネクタを選択して、コネクタに関するプロパティと情報を含むポップアップ ページを表示します。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
