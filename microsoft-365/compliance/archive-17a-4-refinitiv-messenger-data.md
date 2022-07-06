---
title: Microsoft 365 で Refinitiv Eikon Messenger データをアーカイブするコネクタを設定する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 17a-4 Refinitiv Eikon Messenger DataParser コネクタを設定して使用して、Microsoft 365 でこのデータをインポートしてアーカイブする方法について説明します。
ms.openlocfilehash: d6a53b5064982446cdcd7ca95f73aa3b6b0bf5cc
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633105"
---
# <a name="set-up-a-connector-to-archive-refinitiv-eikon-messenger-data"></a>Refinitiv Eikon Messenger データをアーカイブするコネクタを設定する

17a-4 LLC の [Refinitiv Eikon Messenger DataParser を](https://www.17a-4.com/refinitiv-messenger-dataparser/) 使用して、Refinitiv Eikon Messenger から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には、サードパーティのデータ ソースからアイテムをキャプチャし、それらの項目を Microsoft 365 にインポートするように構成された Refinitiv Eikon Messenger コネクタが含まれています。 Refinitiv Eikon Messenger DataParser コネクタは、Refinitiv Eikon Messenger データを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Refinitiv Eikon Messenger データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft Purview 機能を適用できます。 Refinitiv Eikon Messenger コネクタを使用して Microsoft 365 でデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-refinitiv-eikon-messenger-data"></a>Refinitiv Eikon Messenger データのアーカイブの概要

次の概要では、データ コネクタを使用して、Microsoft 365 で Refinitiv Eikon Messenger データをアーカイブするプロセスについて説明します。

![17a-4 の Refinitiv Eikon Messenger データのアーカイブ ワークフロー。](../media/RefinitivMessengerDataParserConnectorWorkflow.png)

1. 組織は 17a-4 と連携して、Refinitiv Eikon Messenger DataParser を設定および構成します。

2. 定期的に、Refinitiv Eikon Messenger アイテムは DataParser によって収集されます。 DataParser では、メッセージの内容も電子メール メッセージ形式に変換されます。

3. Microsoft Purview コンプライアンス ポータルで作成した Refinitiv Eikon Messenger DataParser コネクタは、DataParser に接続し、Microsoft クラウドの安全な Azure Storage の場所にメッセージを転送します。

4. **Refinitiv Eikon Messenger DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、Refinitiv Eikon Messenger アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての Refinitiv Eikon Messenger アイテムには、すべての参加者の電子メール アドレスが設定されたこのプロパティが含まれています。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

- Microsoft コネクタの DataParser アカウントを作成します。 アカウントを作成するには、 [17a-4 LLC](https://www.17a-4.com/contact/) にお問い合わせください。 手順 1. でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 1 で Refinitiv Eikon Messenger DataParser コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この 17a-4 データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサード パーティアプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-a-refinitiv-eikon-messenger-dataparser-connector"></a>手順 1: Refinitiv Eikon Messenger DataParser コネクタを設定する

最初の手順は、コンプライアンス ポータルの [データ コネクタ] ページにアクセスし、Refinitiv Eikon Messenger データ用の 17a-4 コネクタを作成することです。

1. **データ コネクタ** > **の Refinitiv Eikon Messenger DataParser** に<https://compliance.microsoft.com>移動してクリックします。

2. **Refinitiv Eikon Messenger DataParser 製品の** 説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. 17a-4 アカウントにサインインし、Refinitiv Eikon Messenger DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-refinitiv-eikon-messenger-dataparser-connector"></a>手順 2: Refinitiv Eikon Messenger DataParser コネクタを構成する

17a-4 サポートと連携して、Refinitiv Eikon Messenger DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

Refinitiv Eikon Messenger DataParser コネクタは、Microsoft 365 にデータをインポートする前に、ユーザーを Microsoft 365 のメール アドレスに自動的にマップします。

## <a name="step-4-monitor-the-refinitiv-eikon-messenger-dataparser-connector"></a>手順 4: Refinitiv Eikon Messenger DataParser コネクタを監視する

Refinitiv Eikon Messenger DataParser コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の <https://compliance.microsoft.com> ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、作成した Refinitiv Eikon Messenger DataParser コネクタを選択して、コネクタに関するプロパティと情報を含むポップアップ ページを表示します。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
