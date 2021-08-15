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
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、Veritas FX からデータをインポートおよびアーカイブするコネクタを設定して、ConnectをMicrosoft 365。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 61ccbbcea7c9222b68c6fed9fdb954533eab86830c07079dc9c5b5c71cc43d36
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53866674"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a>FX データをアーカイブするコネクタConnectする

サーバー内の Veritas コネクタをMicrosoft 365 コンプライアンス センターして、FX Connect コラボレーション プラットフォームから組織のユーザー メールボックスにデータをインポートMicrosoft 365します。 Veritas には[、FX](https://globanet.com/fx-connect/) Connectアイテムをキャプチャし、それらのアイテムをインポートするように構成された FX ConnectコネクタがMicrosoft 365。 コネクタは、組織の FX Connect アカウントの取引、メッセージ、その他の詳細などのコンテンツを FX Connect から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

FX Connectデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 FX Connectコネクタを使用して、データをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-fx-connect-data"></a>データのアーカイブ FX Connect概要

次の概要では、コネクタを使用して、FX ファイルの情報をアーカイブするプロセスConnect説明Microsoft 365。

![FX データのアーカイブ ワークフロー Connectする](../media/FXConnectConnectorWorkflow.png)

1. 組織は、FX Connectを使用して、FX サイトをConnectします。

2. 24 時間に 1 回、FX アカウントConnectは Veritas Merge1 サイトにコピーされます。 また、コネクタは、FX ファイルConnectメール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した FX Connect コネクタは、毎日 Veritas Merge1 サイトに接続し、FX Connect アイテムを Microsoft クラウド内の安全な Azure Storage 場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。 FX ファイルという名前の受信 **トレイ フォルダー Connect** ユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての FX Connectには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。  アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 手順 1 で FX Connect コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-the-fx-connect-connector"></a>手順 1: FX コネクタをConnectする

最初の手順は、ページの[データ コネクタ] ページにアクセスしMicrosoft 365 コンプライアンス センター FX データのコネクタをConnectすることです。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データ** コネクタ  >  **FX] をクリックConnect。**

2. [FX 製品 **の説明Connect]** ページで、[コネクタの追加]**をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-fx-connect-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで FX Connectコネクタを構成する

2 番目の手順は、Merge1 サイトで FX Connectコネクタを構成することです。 FX コネクタを構成する方法Connect Merge1 サードパーティ コネクタ ユーザー ガイド[を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [ユーザーに **ユーザーをConnectする**] Microsoft 365 FX マップ] ページで、自動ユーザー マッピングを有効にします。 FX のConnectには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-fx-connect-connector"></a>手順 4: FX コネクタをConnectする

FX コネクタコネクタをConnect、コネクタの状態を[コネクタ] Microsoft 365 コンプライアンス センター。

1. 左側の <https://compliance.microsoft.com/> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブを** クリックし **、FX** Connectを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。