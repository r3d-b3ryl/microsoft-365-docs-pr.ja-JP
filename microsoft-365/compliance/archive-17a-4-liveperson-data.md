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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 17a-4 LivePerson Conversational Cloud DataParser コネクタをセットアップして使用して、LivePerson Conversational Cloud データをインポートおよびアーカイブする方法についてMicrosoft 365。
ms.openlocfilehash: 3eedfafe03378237238f354af8e40eba5464e514
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315709"
---
# <a name="set-up-a-connector-to-archive-liveperson-conversational-cloud-data"></a>LivePerson Conversational Cloud データをアーカイブするコネクタをセットアップする

17a-4 LLC の [LivePerson Conversational Cloud DataParser](https://www.17a-4.com/liveperson-dataparser/) を使用して、LivePerson Conversational Cloud から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には LivePerson Conversational Cloud コネクタが含まれており、サード パーティ製のデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されています。 LivePerson Conversational Cloud DataParser コネクタは、データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

ユーザー メールボックスにデータを格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスMicrosoft 365コンプライアンス機能を適用できます。 LivePerson Conversational Cloud コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠し続けるのに役立ちます。

## <a name="overview-of-archiving-liveperson-conversational-cloud-data"></a>LivePerson Conversational Cloud データのアーカイブの概要

次の概要では、データ コネクタを使用して LivePerson Conversational Cloud データをアーカイブするプロセスについて説明Microsoft 365。

![17a-4 の LivePerson Conversational Cloud データのアーカイブ ワークフロー。](../media/LiveEngageDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して LivePerson Conversational Cloud DataParser をセットアップおよび構成します。

2. LivePerson Conversational Cloud アイテムは、定期的に DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した LivePerson Conversational Cloud DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. **LivePerson Conversational Cloud DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにアイテムがインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべてのアイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには、 [17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で LivePerson Conversational Cloud DataParser コネクタを作成するユーザー (および手順 3 で完了) には、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この 17a-4 データ コネクタは、米国政府機関GCC環境Microsoft 365利用できます。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-a-liveperson-conversational-cloud-dataparser-connector"></a>手順 1: LivePerson Conversational Cloud DataParser コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、LivePerson Conversational Cloud データ用の 17a-4 コネクタを作成することです。

1. に移動し <https://compliance.microsoft.com> 、[ **データ コネクタ** > **LivePerson Conversational Cloud DataParser] をクリックします**。

2. **LivePerson Conversational Cloud DataParser** 製品の説明ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、LivePerson Conversational Cloud DataParser 接続ウィザードの手順を完了します。

## <a name="step-2-configure-the-liveperson-conversational-cloud-dataparser-connector"></a>手順 2: LivePerson Conversational Cloud DataParser コネクタを構成する

17a-4 サポートを使用して LivePerson Conversational Cloud DataParser コネクタを構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

LivePerson Conversational Cloud DataParser コネクタは、ユーザーにデータをインポートする前に、Microsoft 365 メール アドレスにユーザーを自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-liveperson-conversational-cloud-dataparser-connector"></a>手順 4: LivePerson Conversational Cloud DataParser コネクタを監視する

LivePerson Conversational Cloud DataParser コネクタを作成した後、コネクタの状態を [スレッド] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション <https://compliance.microsoft.com> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した LivePerson Conversational Cloud DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
