---
title: サーバーで Refinitiv Eikon Messenger データをアーカイブするコネクタをMicrosoft 365
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
description: 17a-4 Refinitiv Eikon Messenger DataParser コネクタを設定して使用して、Microsoft 365 で Refinitiv Eikon Messenger データをインポートおよびアーカイブする方法について学習します。
ms.openlocfilehash: ec3a32a1fcf08747e8ad67983ae0c0aff2650673
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59178056"
---
# <a name="set-up-a-connector-to-archive-refinitiv-eikon-messenger-data"></a>Refinitiv Eikon Messenger データをアーカイブするコネクタをセットアップする

17a-4 LLC の[Refinitiv Eikon Messenger DataParser](https://www.17a-4.com/refinitiv-messenger-dataparser/)を使用して、Refinitiv Eikon Messenger から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された Refinitiv Eikon Messenger コネクタが含まれています。 Refinitiv Eikon Messenger DataParser コネクタは、Refinitiv Eikon Messenger データを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Refinitiv Eikon Messenger データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Refinitiv Eikon Messenger コネクタを使用して、Microsoft 365のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-refinitiv-eikon-messenger-data"></a>Refinitiv Eikon Messenger データのアーカイブの概要

次の概要では、データ コネクタを使用して Refinitiv Eikon Messenger データをアーカイブするプロセスについて説明Microsoft 365。

![17a-4 の Refinitiv Eikon Messenger データのアーカイブ ワークフロー。](../media/RefinitivMessengerDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して Refinitiv Eikon Messenger DataParser を設定および構成します。

2. 定期的に、Refinitiv Eikon Messenger アイテムは DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Refinitiv Eikon Messenger DataParser コネクタは、DataParser に接続し、Microsoft クラウド内の安全な Azure Storage 場所にメッセージを転送します。

4. **Refinitiv Eikon Messenger DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、Refinitiv Eikon Messenger アイテムがそのフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべての Refinitiv Eikon Messenger アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で Refinitiv Eikon Messenger DataParser コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-a-refinitiv-eikon-messenger-dataparser-connector"></a>手順 1: Refinitiv Eikon Messenger DataParser コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、Refinitiv Eikon Messenger データ用の 17a-4 コネクタを作成することです。

1. に移動 <https://compliance.microsoft.com> し、[データ コネクタ **の** 絞り込み]をクリックします  >  **。Eikon Messenger DataParser をクリックします**。

2. **[Refinitiv Eikon Messenger DataParser 製品** の説明] ページで、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、Refinitiv Eikon Messenger DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-refinitiv-eikon-messenger-dataparser-connector"></a>手順 2: Refinitiv Eikon Messenger DataParser コネクタを構成する

17a-4 サポートを使用して Refinitiv Eikon Messenger DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

Refinitiv Eikon Messenger DataParser コネクタは、ユーザーにデータをインポートする前に、Microsoft 365 メール アドレスにユーザーを自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-refinitiv-eikon-messenger-dataparser-connector"></a>手順 4: Refinitiv Eikon Messenger DataParser コネクタを監視する

Refinitiv Eikon Messenger DataParser コネクタを作成した後は、コネクタの状態を [Microsoft 365 コンプライアンス センター] に表示できます。

1. 左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、作成した Refinitiv Eikon Messenger DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
