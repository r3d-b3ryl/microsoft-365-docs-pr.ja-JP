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
description: 17a-4 FX Connect DataParser コネクタをセットアップして使用して、データをインポートおよびアーカイブする方法についてConnectをMicrosoft 365。
ms.openlocfilehash: 129d5f6836d8cf447b77bf068a4c6b5f33b33703
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63311803"
---
# <a name="set-up-a-connector-to-archive-data-from-fx-connect"></a>FX サーバーからデータをアーカイブするコネクタをConnect

17a-4 LLC [Connect DataParser](https://www.17a-4.com/dataparser-roadmap/) を使用して、FX Connect Microsoft 365 から組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 DataParser には、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された FX Connect コネクタが含Microsoft 365。 FX Connect DataParser コネクタは、FX Connect データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。

FX Connectデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 FX Connectコネクタを使用してデータをインポートおよびアーカイブすると、Microsoft 365規制ポリシーに準拠し、組織のコンプライアンスを維持できます。

## <a name="overview-of-archiving-fx-connect-data"></a>データのアーカイブ FX Connect概要

次の概要では、データ コネクタを使用して、FX データをアーカイブするプロセスConnect説明Microsoft 365。

![FX のアーカイブ ワークフロー Connect 17a-4 のデータを収集します。](../media/FXConnectDataParserConnectorWorkflow.png)

1. 組織は 17a-4 を使用して、DataParser の FX Connect構成します。

2. 定期的に、FX Connectアイテムは DataParser によって収集されます。 DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した FX Connect DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。

4. **FX Connect DataParser という名前** の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーに fx Connect アイテムがインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべての FX Connectには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

- Microsoft コネクタ用の DataParser アカウントを作成します。 これを行うには、 [17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 で FX Connect DataParser コネクタを作成し、手順 3 で完了するユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この 17a-4 データ コネクタは、米国政府機関GCC環境Microsoft 365利用できます。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-a-fx-connect-dataparser-connector"></a>手順 1: DATAParser コネクタConnect設定する

最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、FX データ用の 17a-4 Connectすることです。

1. [Data ConnectorsFX<https://compliance.microsoft.com>] に移動 **し、[DataParser** > **] Connectクリックします**。

2. **[FX ファイル] Connect DataParser** 製品の説明ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. 17a-4 アカウントにサインインし、FX サーバーの DataParser 接続ウィザードConnect完了します。

## <a name="step-2-configure-the-fx-connect-dataparser-connector"></a>手順 2: DATAParser コネクタConnect FX を構成する

17a-4 サポートを使用して、DATAParser コネクタの FX Connect構成します。

## <a name="step-3-map-users"></a>手順 3: ユーザーをマップする

FX Connect DataParser コネクタは、データをインポートする前に、ユーザーを自分の電子メール Microsoft 365に自動的にマップMicrosoft 365。

## <a name="step-4-monitor-the-fx-connect-dataparser-connector"></a>手順 4: DATAParser コネクタConnect FX を監視する

DataParser コネクタに FX Connectを作成した後、コネクタの状態を表示できます。Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション <https://compliance.microsoft.com> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし、作成した FX Connect DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
