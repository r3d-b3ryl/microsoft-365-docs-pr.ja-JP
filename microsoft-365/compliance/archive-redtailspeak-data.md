---
title: Microsoft 365 で Redtail Speak データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet から Microsoft 365 に Redtail Speak データをインポートしてアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: ee1e5c63d8990d5847241dc0ab4a88ed19e3215f
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740294"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Redtail Speak データをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Microsoft 365 組織内の Redtail Speak to user メールボックスからデータをインポートおよびアーカイブします。 Globanet は [、Redtail](https://globanet.com/redtail/) からアイテムを受信する組織の SFTP サーバーからアイテムをキャプチャするように構成された Redtail Speak コネクタを提供します。 コネクタは、Redtail Speak から電子メール メッセージ形式にコンテンツを変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Redtail Speak データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Redtail Speak コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Redtail Speak データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の Redtail Speak データをアーカイブするプロセスについて説明します。

![Redtail Speak データのアーカイブ ワークフロー](../media/RedtailSpeakConnectorWorkflow.png)

1. 組織は Redtail Speak と一緒に、メッセージが Redtail Speak から組織の SFTP サーバーに毎日転送される SMTP ゲートウェイを設定および構成します。

2. 24 時間ごとに Redtail Speak アイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、Redtail Speak アイテムを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成する Redtail Speak コネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。

4. コネクタは、ステップ 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Redtail Speak アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。 **Redtail Speak** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。 コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての Redtail Speak アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順 2 では、組織の SFTP サーバーを指定する必要があります。 これは、Globanet Merge1 が SFTP を介して Redtail Speak データを収集するために通信するために必要です。

- 手順 1 で Redtail Speak Importer コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。 この役割は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループには割り当てられていない。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-redtail-speak-connector"></a>手順 1: Redtail Speak コネクタをセットアップする

最初の手順は、Microsoft 365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、Redtail Speak データ用のコネクタを作成することです。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/)  &gt; **Redtail Speak] に移動してクリックします**。

2. Redtail **Speak 製品の説明ページ** で、[新しいコネクタの追加 **] をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで Redtail Speak コネクタを構成する

2 番目の手順は、Merge1 サイトで Redtail Speak コネクタを構成することです。 Redtail Speak コネクタを構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)。

[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。

1. **[Redtail Speak ユーザーを Microsoft 365** ユーザーにマップする] ページで、ユーザーの自動マッピングを有効にします。 Redtail Speak アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-redtail-speak-connector"></a>手順 4: Redtail Speak コネクタを監視する

Redtail Speak コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブをクリック** し **、Redtail Speak** コネクタを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が表示されます。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータが含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
