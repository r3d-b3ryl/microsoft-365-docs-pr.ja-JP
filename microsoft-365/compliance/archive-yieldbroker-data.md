---
title: Microsoft 365 で Yieldbroker データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet から Microsoft 365 に Yieldbroker データをインポートしてアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 1591198dae3a7a5082c4f8f7ba925eb9e6dd680b
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722980"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data-preview"></a>Yieldbroker データをアーカイブするコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Yieldbroker から Microsoft 365 組織内のユーザー メールボックスにデータをインポートしてアーカイブします。 Globanet は、サード パーティのデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Yieldbroker](https://globanet.com/yieldbroker/) コネクタを提供します。 コネクタは、コンテンツを Yieldbroker から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Yieldbroker がユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Yieldbroker コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-yieldbroker-data"></a>Yieldbroker データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Yieldbroker データをアーカイブするプロセスについて説明します。

![Yieldbroker データのアーカイブ ワークフロー](../media/YieldbrokerConnectorWorkflow.png)

1. 組織は Yieldbroker と共同で Yieldbroker サイトをセットアップおよび構成します。

2. 24 時間ごとに、Yieldbroker アイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、コンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成する Yieldbroker コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にメッセージを転送します。

4. コネクタは、ステップ 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Yieldbroker アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 ユーザー メールボックスに **Yieldbroker** という名前の受信トレイ フォルダー内のサブフォルダーが作成され、アイテムがフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての Yieldbroker にはこのプロパティが含まれているので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 1 で Yieldbroker コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割に割り当てられている必要があります。 この役割は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループには割り当てられていない。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-yieldbroker-connector"></a>手順 1: Yieldbroker コネクタを設定する

最初の手順は、Microsoft 365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、Yieldbroker のコネクタを作成することです。

1. [データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ &gt; **Yieldbroker] に移動してクリックします**。

2. **Yieldbroker 製品の説明ページ** で、[新しいコネクタの追加 **] をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-yieldbroker-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで Yieldbroker コネクタを構成する

2 番目の手順は、Merge1 サイトで Yieldbroker コネクタを構成することです。 Yieldbroker を構成する方法については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。

1. **[Yieldbroker ユーザーを Microsoft 365 ユーザーに** マップする] ページで、自動ユーザー マッピングを有効にします。 Yieldbroker アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-yieldbroker-connector"></a>手順 4: Yieldbroker コネクタを監視する

Yieldbroker コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブ** をクリックし **、Yieldbroker** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
