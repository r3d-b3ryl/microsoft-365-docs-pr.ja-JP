---
title: ロイター FX データをアーカイブするコネクタを設定Microsoft 365
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
description: 管理者は、Reuters FX データを Veritas からユーザーにインポートおよびアーカイブするコネクタをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: afc8ef93179259597c1113791c318f3b115c3561
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312377"
---
# <a name="set-up-a-connector-to-archive-reuters-fx-data"></a>ロイター FX データをアーカイブするコネクタをセットアップする

Reuters FX プラットフォームからデータをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、組織のユーザー メールボックスMicrosoft 365します。 Veritas は、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたロイター [FX](https://globanet.com/reuters-fx/) コネクタを提供します。 コネクタは、ロイター FX アカウントの通貨と FX レートを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

ロイター FX データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 ロイター FX コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-reuters-fx-data"></a>ロイター FX データのアーカイブの概要

次の概要では、コネクタを使用してロイター FX データをアーカイブするプロセスについて説明Microsoft 365。

![ロイター FX データのアーカイブ ワークフロー。](../media/ReutersFXConnectorWorkflow.png)

1. 組織はロイター FX と一緒にロイター FX サイトを設定および構成します。

2. 24 時間に 1 回、ロイター FX アイテムは Veritas Merge1 サイトにコピーされます。 コネクタは、アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成したロイター FX コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にコンテンツを転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Reuters FX** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用してアイテムをインポートするメールボックスを *決定* します。 すべてのロイター FX アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>始める前に

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 アカウントを作成するには、 [Veritas カスタマー サポートにお問い合わせください](https://globanet.com/contact-us)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 でロイター FX コネクタを作成し (および手順 3 で完了する) ユーザーには、データ コネクタ管理者の役割が割り当てられている必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

- この Veritas データ コネクタは、米国政府機関クラウドGCC環境Microsoft 365プレビュー中です。 サード パーティ製のアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にある、Microsoft 365 コンプライアンスおよびデータ保護のコミットメントの対象となされていないサードパーティ システムに対して、組織の顧客データを保存、送信、および処理する必要があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="step-1-set-up-the-reuters-fx-connector"></a>手順 1: ロイター FX コネクタをセットアップする

最初の手順は、データ ソースの  [データ コネクタ] ページにアクセスしMicrosoft 365ロイター FX データ用のコネクタを作成することです。

1. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/)、[**データ** >  コネクタ **Reuters FX] をクリックします**。

2. [ロイ **ター FX 製品の説明]** ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントに署名します。

## <a name="step-2-configure-the-reuters-fx-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトでロイター FX コネクタを構成する

2 番目の手順は、Veritas Merge1 サイトでロイター FX コネクタを構成することです。 ロイター FX コネクタの構成の詳細については、「Merge1 サード パーティ コネクタ ユーザー ガイド」 [を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf)。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [ロイ **ター FX ユーザーを** ユーザーにマップMicrosoft 365] ページで、自動ユーザー マッピングを有効にします。

   ロイター FX アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-reuters-fx-connector"></a>手順 4: ロイター FX コネクタを監視する

Reuters FX コネクタを作成した後、コネクタの状態を [コネクタ] Microsoft 365 コンプライアンス センター。

1. 左側のナビゲーション <https://compliance.microsoft.com/> で [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、 **ロイター FX** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの** 状態] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。