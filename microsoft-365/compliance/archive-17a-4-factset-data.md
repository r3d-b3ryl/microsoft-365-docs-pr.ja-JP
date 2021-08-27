---
title: データ内の FactSet データをアーカイブするコネクタをMicrosoft 365
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
description: 17a-4 FactSet DataParser コネクタをセットアップして使用して、ファクトセット データをインポートおよびアーカイブする方法についてMicrosoft 365。
ms.openlocfilehash: cbc56b5ce3c2305238daabd78fed2f9794f96242
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58563274"
---
# <a name="set-up-a-connector-to-archive-factset-data"></a>FactSet データをアーカイブするコネクタをセットアップする

FactSet プラットフォームから組織内のユーザー メールボックスにデータをインポートおよびアーカイブするには、17a-4 LLC の[FactSet DataParser](https://www.17a-4.com/factset-dataparser/)をMicrosoft 365します。 DataParser には、サード パーティ製のデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された FactSet コネクタMicrosoft 365。 FactSet DataParser コネクタは、FactSet データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

FactSet データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 FactSet コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-factset-data"></a>FactSet データのアーカイブの概要

次の概要では、データ コネクタを使用してファクトセット データをアーカイブするプロセスについて説明Microsoft 365。

![17a-4 の FactSet データのアーカイブ ワークフロー。](../media/FactSetDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して FactSet DataParser を設定および構成します。

2. 定期的に、FactSet アイテムは DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した FactSet DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage場所にメッセージを転送します。

4. **FactSet DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、FactSet アイテムはそのフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべての FactSet アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で FactSet DataParser コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-a-factset-dataparser-connector"></a>手順 1: FactSet DataParser コネクタをセットアップする

最初の手順は、データ の [データ コネクタ] ページにアクセスしMicrosoft 365 コンプライアンス センターファクトセット データ用の 17a-4 コネクタを作成することです。

1. [データ コネクタ <https://compliance.microsoft.com> ]   >  **FactSet DataParser に移動し、[データ コネクタ] をクリックします**。

2. **FactSet DataParser 製品の説明ページで、[** コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、FactSet DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-factset-dataparser-connector"></a>手順 2: FactSet DataParser コネクタを構成する

17a-4 サポートを使用して FactSet DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

FactSet DataParser コネクタは、ユーザーにデータをインポートする前に、ユーザー Microsoft 365メール アドレスに自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-factset-dataparser-connector"></a>手順 4: FactSet DataParser コネクタを監視する

FactSet DataParser コネクタを作成した後、コネクタの状態を[データ セット] Microsoft 365 コンプライアンス センター。

1. 左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した FactSet DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
