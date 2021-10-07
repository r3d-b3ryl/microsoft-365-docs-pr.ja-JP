---
title: InvestEdge データをアーカイブするコネクタをセットアップMicrosoft 365
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
description: 17a-4 InvestEdge DataParser コネクタをセットアップして使用して、InvestEdge データをインポートおよびアーカイブする方法についてMicrosoft 365。
ms.openlocfilehash: cacdb9ed03003eb3aee8b84baf1eac82a2f378b8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200607"
---
# <a name="set-up-a-connector-to-archive-investedge-data"></a>InvestEdge データをアーカイブするコネクタをセットアップする

17a-4 LLC の[InvestEdge DataParser](https://www.17a-4.com/investedge-dataparser/)を使用して、InvestEdge から組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。 DataParser には、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された InvestEdge コネクタがMicrosoft 365。 InvestEdge DataParser コネクタは、InvestEdge データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

InvestEdge データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 InvestEdge コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-investedge-data"></a>InvestEdge データのアーカイブの概要

次の概要では、データ コネクタを使用して InvestEdge データをアーカイブするプロセスについて説明Microsoft 365。

![17a-4 の InvestEdge データのアーカイブ ワークフロー。](../media/InvestEdgeDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して InvestEdge DataParser を設定および構成します。

2. InvestEdge アイテムは、定期的に DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した InvestEdge DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. **InvestEdge DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、InvestEdge アイテムがそのフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべての InvestEdge アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で InvestEdge DataParser コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

- このデータ コネクタは、米国政府機関GCCのMicrosoft 365環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあるサードパーティ システムに組織の顧客データを格納、送信、処理する必要がある場合があります。したがって、Microsoft 365 コンプライアンスとデータ保護のコミットメントの対象とはなってはいけなかっています。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-a-investedge-dataparser-connector"></a>手順 1: InvestEdge DataParser コネクタをセットアップする

最初の手順は、ページの [データ コネクタ] ページにアクセスしMicrosoft 365 コンプライアンス センター InvestEdge データ用の 17a-4 コネクタを作成することです。

1. に移動 <https://compliance.microsoft.com> し、[データ コネクタ **の**  >  **InvestEdge DataParser] をクリックします**。

2. **InvestEdge DataParser 製品** の説明ページで、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、InvestEdge DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-investedge-dataparser-connector"></a>手順 2: InvestEdge DataParser コネクタを構成する

17a-4 サポートを使用して InvestEdge DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

InvestEdge DataParser コネクタは、ユーザーにデータをインポートする前Microsoft 365メール アドレスにユーザーを自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-investedge-dataparser-connector"></a>手順 4: InvestEdge DataParser コネクタを監視する

InvestEdge DataParser コネクタを作成した後は、コネクタの状態を [データ] Microsoft 365 コンプライアンス センター。

1. 左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した InvestEdge DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
