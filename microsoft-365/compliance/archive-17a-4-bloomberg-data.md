---
title: ブルームバーグ のデータをアーカイブするコネクタをセットアップMicrosoft 365
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
description: 17a-4 Bloomberg DataParser コネクタをセットアップして使用して、ブルームバーグ データをインポートおよびアーカイブする方法についてMicrosoft 365。
ms.openlocfilehash: 2d4005468d7df7987d1794e8d61262c8fde70b5f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454543"
---
# <a name="set-up-a-connector-to-archive-bloomberg-data"></a>ブルームバーグ データをアーカイブするコネクタをセットアップする

17a-4 LLC の[Bloomberg DataParser](https://www.17a-4.com/Bloomberg-dataparser/)を使用して、ブルームバーグから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。 DataParser には、サード パーティ製のデータ ソースからアイテムをキャプチャし、それらのアイテムを他のデータ ソースにインポートするように構成されたブルームバーグ コネクタMicrosoft 365。 Bloomberg DataParser コネクタは、ブルームバーグ データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

Bloomberg データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 ブルームバーグ コネクタを使用して、Microsoft 365のデータをインポートおよびアーカイブすると、組織が政府と規制のポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-bloomberg-data"></a>ブルームバーグ データのアーカイブの概要

次の概要では、データ コネクタを使用してブルームバーグ データをアーカイブするプロセスについて説明Microsoft 365。

![17a-4 からのブルームバーグ データのアーカイブ ワークフロー](../media/BloombergDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用してブルームバーグ DataParser を設定および構成します。

2. 定期的に、Bloomberg アイテムは DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Bloomberg DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. **Bloomberg DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー のメールボックスに作成され、そのフォルダーにブルームバーグ アイテムがインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべての Bloomberg アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 でブルームバーグ DataParser コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-a-bloomberg-dataparser-connector"></a>手順 1: Bloomberg DataParser コネクタをセットアップする

最初の手順は、ブルームバーグ データ用の 17a-4 コネクタを作成Microsoft 365 コンプライアンス センターデータ コネクタ ページにアクセスすることです。

1. [データ <https://compliance.microsoft.com> コネクタ]**ブルームバーグ**  >  **DataParser に移動し、[データ コネクタ] をクリックします**。

2. Bloomberg **DataParser 製品の説明ページで、[** コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、Bloomberg DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-bloomberg-dataparser-connector"></a>手順 2: Bloomberg DataParser コネクタを構成する

17a-4 サポートを使用してブルームバーグ DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

Bloomberg DataParser コネクタは、ユーザーにデータをインポートする前に、ユーザー Microsoft 365メール アドレスに自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-bloomberg-dataparser-connector"></a>手順 4: Bloomberg DataParser コネクタを監視する

Bloomberg DataParser コネクタを作成した後、コネクタの状態を[データ]ページでMicrosoft 365 コンプライアンス センター。

1. 左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、作成した Bloomberg DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
