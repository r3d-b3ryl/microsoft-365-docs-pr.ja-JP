---
title: Microsoft 365 でデータを扱うロイターをアーカイブするコネクタをセットアップする
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
description: 管理者は、ロイターのデータを Globanet から Microsoft 365 にインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 3977bd01c87bb3a02ec2027c25bbe8dfb1779c67
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925139"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data"></a>ロイターの取引データをアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、ロイター取引プラットフォームから Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。 Globanet は、サードパーティ[](https://globanet.com/reuters-dealing/)のデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたロイターの取引コネクタを提供します。 コネクタは、Reuters Dealing アカウントからの通信を電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

ロイター 取引データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 ロイターの取引コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-reuters-dealing-data"></a>アーカイブの概要 ロイター データの処理

次の概要では、コネクタを使用して Microsoft 365 のロイター取引データをアーカイブするプロセスについて説明します。

![ロイターのデータを扱うアーカイブ ワークフロー](../media/ReuetersDealingConnectorWorkflow.png)

1. 組織はロイターの取引と一緒にロイター取引サイトを設定および構成します。

2. 24 時間に 1 回、ロイター のアイテムは Globanet Merge1 サイトにコピーされます。 コネクタは、アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成したロイターの対応コネクタは、毎日 Globanet Merge1 サイトに接続し、コンテンツを Microsoft クラウド内の安全な Azure Storage の場所に転送します。

4. コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Reuters Dealing** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべてのロイターの [取引] アイテムには、アイテムのすべての参加者の電子メール アドレスが設定されたこのプロパティが含まれる。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us)。 手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。

- 手順 1 でロイター取引コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。 既定では、この役割は Exchange Online の任意の役割グループに割り当てられていない。 Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-reuters-dealing-connector"></a>手順 1: ロイターの対応コネクタをセットアップする

最初の手順は、Microsoft 365 の [データ コネクタ] ページにアクセスし、ロイターのデータを扱うコネクタを作成することです。 

1. [データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ] [**ロイター** 取引]  >  **に移動し、[データ コネクタ] をクリックします**。

2. [ロイター **取引製品の説明] ページ** で、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントに署名します。

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトでロイター取引コネクタを構成する

2 番目の手順は、Merge1 サイトの Globanet でロイター取引コネクタを構成することです。 ロイター対応コネクタの構成の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。

1. [ユーザー **を Microsoft 365** ユーザーに対応するマップ] ページで、自動ユーザー マッピングを有効にする。

   ロイター 取引アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-reuters-dealing-connector"></a>手順 4: ロイターの対応コネクタを監視する

ロイター取引コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し、[ロイターの対応] コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。