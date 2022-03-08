---
title: FX データをアーカイブするコネクタConnectを設定Microsoft 365
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
description: 管理者は、Veritas FX からデータをインポートおよびアーカイブするコネクタをセットアップして、ConnectをMicrosoft 365。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: a625cc6d7367521ab30f4018b04f1ad8449efa55
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328303"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a>FX データをアーカイブするコネクタConnectする

サーバーの Veritas コネクタをMicrosoft 365 コンプライアンス センターして、FX Connect コラボレーション プラットフォームから組織のユーザー メールボックスにデータをインポートMicrosoft 365します。 Veritas には[、FX](https://globanet.com/fx-connect/) Connectアイテムをキャプチャし、それらのアイテムをインポートするように構成された FX ConnectコネクタがMicrosoft 365。 コネクタは、組織の FX Connect アカウントの取引、メッセージ、その他の詳細などのコンテンツを FX Connect から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

FX Connectデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 FX Connectコネクタを使用して、データをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-fx-connect-data"></a>データのアーカイブ FX Connect概要

次の概要では、コネクタを使用して、FX ファイルの情報をアーカイブするプロセスConnect説明Microsoft 365。

![FX データのアーカイブ ワークフロー Connectします。](../media/FXConnectConnectorWorkflow.png)

1. 組織は、FX Connectと一緒に FX サイトをConnectします。

2. 24 時間に 1 回、FX アカウントConnectが Veritas Merge1 サイトにコピーされます。 また、コネクタは、FX ファイルConnectメール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した FX Connect コネクタは、毎日 Veritas Merge1 サイトに接続し、FX Connect アイテムを Microsoft クラウド内の安全な Azure Storage 場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。 FX ファイルという名前の受信 **トレイ フォルダー Connect** ユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての FX Connectには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。  アカウントを作成するには、 [Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1 で FX Connectコネクタを作成し (および手順 3 で完了する) ユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-fx-connect-connector"></a>手順 1: FX コネクタをConnectする

最初の手順は、ページの [データ コネクタ] ページにアクセスしMicrosoft 365 コンプライアンス センター FX データのコネクタをConnectします。

1. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/)、[**データ コネクタ** > **FX] をクリックConnect**。

2. [**FX 製品の説明Connect**] ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-fx-connect-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで FX Connectコネクタを構成する

2 番目の手順は、Merge1 サイトConnect FX コネクタを構成することです。 FX コネクタコネクタを構成するConnect詳細については、「Merge1 サード パーティ コネクタ ユーザー ガイド」[を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [ユーザー **をユーザーにConnectする**] Microsoft 365 FX マップ] ページで、ユーザーの自動マッピングを有効にしてください。 FX のConnectには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-fx-connect-connector"></a>手順 4: FX コネクタをConnectする

FX サーバー コネクタを作成Connect、コネクタの状態を [コネクタ] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション <https://compliance.microsoft.com/> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、**FX** Connectを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。