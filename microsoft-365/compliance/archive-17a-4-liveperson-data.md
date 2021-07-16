---
title: LivePerson Conversational Cloud データをアーカイブするコネクタを設定Microsoft 365
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
description: 17a-4 LivePerson Conversational Cloud DataParser コネクタをセットアップして使用して、LivePerson Conversational Cloud データをインポートおよびアーカイブする方法についてMicrosoft 365。
ms.openlocfilehash: 70b8e8bd1c8c411894a90e0f919581b3faf58cae
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454459"
---
# <a name="set-up-a-connector-to-archive-liveperson-conversational-cloud-data"></a>LivePerson Conversational Cloud データをアーカイブするコネクタをセットアップする

17a-4 LLC の[LivePerson Conversational Cloud DataParser](https://www.17a-4.com/liveperson-dataparser/)を使用して、LivePerson Conversational Cloud から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には LivePerson Conversational Cloud コネクタが含まれており、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されています。 LivePerson Conversational Cloud DataParser コネクタは、データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

ユーザー メールボックスにデータを格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどのコンプライアンス機能Microsoft 365コンプライアンス機能を適用できます。 LivePerson Conversational Cloud コネクタを使用して、Microsoft 365データをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠し続けるのに役立ちます。

## <a name="overview-of-archiving-liveperson-conversational-cloud-data"></a>LivePerson Conversational Cloud データのアーカイブの概要

次の概要では、データ コネクタを使用して LivePerson Conversational Cloud データをアーカイブするプロセスを、Microsoft 365。

![17a-4 の LivePerson Conversational Cloud データのアーカイブ ワークフロー](../media/LiveEngageDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して LivePerson Conversational Cloud DataParser をセットアップおよび構成します。

2. LivePerson Conversational Cloud アイテムは、定期的に DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した LivePerson Conversational Cloud DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. **LivePerson Conversational Cloud DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにアイテムがインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべてのアイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で LivePerson Conversational Cloud DataParser コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-a-liveperson-conversational-cloud-dataparser-connector"></a>手順 1: LivePerson Conversational Cloud DataParser コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、LivePerson Conversational Cloud データ用の 17a-4 コネクタを作成することです。

1. に移動 <https://compliance.microsoft.com> し、[**データ** コネクタ  >  **LivePerson Conversational Cloud DataParser] をクリックします**。

2. **LivePerson Conversational Cloud DataParser** 製品の説明ページで、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、LivePerson Conversational Cloud DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-liveperson-conversational-cloud-dataparser-connector"></a>手順 2: LivePerson Conversational Cloud DataParser コネクタを構成する

17a-4 サポートを使用して LivePerson Conversational Cloud DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

LivePerson Conversational Cloud DataParser コネクタは、ユーザーにデータをインポートする前に、Microsoft 365 メール アドレスにユーザーを自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-liveperson-conversational-cloud-dataparser-connector"></a>手順 4: LivePerson Conversational Cloud DataParser コネクタを監視する

LivePerson Conversational Cloud DataParser コネクタを作成した後は、コネクタの状態を [スレッド] Microsoft 365 コンプライアンス センター。

1. 左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した LivePerson Conversational Cloud DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
