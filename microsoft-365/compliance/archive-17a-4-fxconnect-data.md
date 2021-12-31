---
title: 17a-4 DataParser コネクタをセットアップして、17a-4 DataParser ConnectデータをアーカイブMicrosoft 365
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
description: 17a-4 FX Connect DataParser コネクタをセットアップして使用して、データをインポートおよびアーカイブする方法ConnectをMicrosoft 365。
ms.openlocfilehash: bc92ad3dea5c53f208078cc05b0f4cc3661b8ac6
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/30/2021
ms.locfileid: "61646211"
---
# <a name="set-up-a-connector-to-archive-data-from-fx-connect"></a>FX サーバーからデータをアーカイブするコネクタをConnect

17a-4 LLC の FX Connect [DataParser](https://www.17a-4.com/dataparser-roadmap/)を使用して、FX Connect から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には、サードパーティConnectからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された FX Microsoft 365 が含まれています。 FX Connect DataParser コネクタは、FX Connect データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

FX Connectデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 FX Connectコネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-fx-connect-data"></a>データのアーカイブ FX Connect概要

次の概要では、データ コネクタを使用してデータをアーカイブするプロセスについてConnectをMicrosoft 365。

![17a-4 のデータConnect FX のアーカイブ ワークフロー。](../media/FXConnectDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して、DataParser の FX Connect構成します。

2. 定期的に、FX Connectアイテムは DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター でConnectする FX コネクタは DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. FX Connect **DataParser という** 名前の受信トレイ フォルダー内のサブフォルダーがユーザー のメールボックスに作成され、そのフォルダーに FX Connect アイテムがインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべての FX Connectには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で FX Connect DataParser コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

- この 17a-4 データ コネクタは、米国政府機関GCC環境Microsoft 365使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあるサードパーティ システムに組織の顧客データを格納、送信、処理する必要がある場合があります。したがって、Microsoft 365 コンプライアンスとデータ保護のコミットメントの対象とはなってはいけなかっています。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-a-fx-connect-dataparser-connector"></a>手順 1: DATAParser コネクタConnect設定する

最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、FX データ用の 17a-4 コネクタConnectすることです。

1. に移動 <https://compliance.microsoft.com> し **、[Data Connectors** FX Connect  >  **DataParser] をクリックします**。

2. **[FX ファイル] Connect DataParser** 製品の説明ページで、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、FX サーバーの DataParser 接続ウィザードConnect完了します。

## <a name="step-2-configure-the-fx-connect-dataparser-connector"></a>手順 2: DATAParser コネクタConnect FX を構成する

17a-4 サポートを使用して、DATAParser コネクタの FX Connect構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

FX Connect DataParser コネクタは、データをインポートする前に、ユーザー Microsoft 365メール アドレスに自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-fx-connect-dataparser-connector"></a>手順 4: DATAParser コネクタConnect FX を監視する

DataParser コネクタに FX Connectを作成した後、コネクタの状態を表示できます。Microsoft 365 コンプライアンス センター。

1. 左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した FX Connect DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
