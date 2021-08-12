---
title: ロイターをアーカイブするコネクタをセットアップする データを処理するMicrosoft 365
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
description: 管理者は、Reuters のデータを Veritas から他のユーザーにインポートしてアーカイブするコネクタをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 247ad42731df49887255c2e3b094fd2f6ec4b643542b097f09b6b68bfae300c0
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53796651"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data"></a>ロイターの取引データをアーカイブするコネクタをセットアップする

Reuters Dealing プラットフォームからデータをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、組織のユーザー メールボックスMicrosoft 365します。 Veritas は、サードパーティ[](https://globanet.com/reuters-dealing/)のデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたロイターの取引コネクタを提供します。 コネクタは、電子メール メッセージ形式にロイターの取引アカウントからの通信を変換し、それらのアイテムをユーザーのメールボックスにインポートMicrosoft 365。

ロイター 取引データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 ロイターの取引コネクタを使用して、Microsoft 365データをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-reuters-dealing-data"></a>アーカイブの概要 ロイター データの処理

次の概要では、コネクタを使用してロイターの取引データをアーカイブするプロセスについて説明Microsoft 365。

![ロイターのデータを扱うアーカイブ ワークフロー](../media/ReuetersDealingConnectorWorkflow.png)

1. 組織はロイターの取引と一緒にロイター取引サイトを設定および構成します。

2. 24 時間に 1 回、ロイター のアイテムは Veritas Merge1 サイトにコピーされます。 コネクタは、アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成したロイターの対応コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にコンテンツを転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Reuters Dealing** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべてのロイターの [取引] アイテムには、アイテムのすべての参加者の電子メール アドレスが設定されたこのプロパティが含まれる。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/contact-us)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 でロイター取引コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割は、グループ内の任意の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-the-reuters-dealing-connector"></a>手順 1: ロイターの対応コネクタをセットアップする

最初の手順は、データ の[データ コネクタ] ページにアクセスし、Microsoft 365データを扱うコネクタを作成することです。

1. [データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ] [**ロイター** 取引]  >  **に移動し、[データ コネクタ] をクリックします**。

2. [ロイター **取引製品の説明] ページ** で、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントに署名します。

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトでロイター取引コネクタを構成する

2 番目の手順は、Merge1 サイトの Veritas でロイター取引コネクタを構成することです。 ロイター対応コネクタの構成の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。

1. [ユーザー **をユーザーに割り当てMicrosoft 365する]** ページで、自動ユーザー マッピングを有効にします。

   ロイター 取引アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-reuters-dealing-connector"></a>手順 4: ロイターの対応コネクタを監視する

ロイターの取引コネクタを作成した後、コネクタの状態を [コネクタ] Microsoft 365 コンプライアンス センター。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、[ロイターの対応] コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。