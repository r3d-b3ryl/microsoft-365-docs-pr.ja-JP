---
title: Slack 電子情報開示データをアーカイブするコネクタを設定Microsoft 365
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
description: 管理者は、Veritas Slack 電子情報開示からデータをインポートおよびアーカイブするコネクタを設定して、Microsoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 3cbc19ab41b7916de76924cd69598335e8834322
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58572217"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>Slack 電子情報開示データをアーカイブするコネクタをセットアップする

Microsoft 365 コンプライアンス センター の Veritas コネクタを使用して、ソーシャル メディア、インスタント メッセージング、ドキュメント コラボレーション プラットフォームから、Microsoft 365 組織内のメールボックスにサードパーティデータをインポートおよびアーカイブします。 Veritas には[、サードパーティ](https://globanet.com/slack/)のデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された Slack コネクタが提供されています。 Slack は Slack API からメッセージとファイルをプルし、メール メッセージ形式に変換してから、アイテムをユーザー メールボックスにインポートします。

Slack 電子情報開示データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Slack コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Slack 電子情報開示データのアーカイブの概要

次の概要では、コネクタを使用して Slack 情報をアーカイブするプロセスについて説明Microsoft 365。

![Slack アーカイブ ワークフロー。](../media/SlackConnectorWorkflow.png)

1. 組織は Slack を使用して Slack サイトを設定および構成します。

2. 24 時間に 1 回、Slack 電子情報開示からのチャット メッセージが Veritas Merge1 サイトにコピーされます。 また、コネクタはチャット メッセージのコンテンツを電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センター で作成した Slack 電子情報開示コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage 場所にチャット メッセージを転送します。

4. コネクタは、手順 3 で説明したように *、Email* プロパティと自動ユーザー マッピングの値を使用して、変換されたチャット メッセージ アイテムを特定のユーザーのメールボックスにインポートします。 **Slack eDiscovery** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにチャット メッセージ アイテムがインポートされます。 コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。 すべてのチャット メッセージには、このプロパティが含まれるので、チャット メッセージのすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。 アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 組織の Slack エンタープライズ アカウントのユーザー名とパスワードを取得します。 Slack を構成する場合は、手順 2 でこのアカウントにサインインする必要があります。

- 手順 1 で Slack 電子情報開示コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。 この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割はグループ内の役割グループExchange Online。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>手順 1: Slack 電子情報開示コネクタをセットアップする

最初の手順は、Slack データのコネクタを作成し、Microsoft 365 コンプライアンス センターデータ コネクタページにアクセスすることです。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) の Slack 電子 **情報開示**]  >  **に移動し、[データ コネクタ] をクリックします**。

2. Slack 電子 **情報開示製品の説明** ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-slack-ediscovery"></a>手順 2: Slack 電子情報開示を構成する

2 番目の手順は、Merge1 サイトで Slack 電子情報開示コネクタを構成することです。 Veritas Merge1 サイトで Slack 電子情報開示コネクタを構成する方法の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。

[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

1. [外部ユーザー **をユーザーにマップMicrosoft 365] ページで**、自動ユーザー マッピングを有効にします。

   Slack 電子情報開示アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。 コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>手順 4: Slack 電子情報開示コネクタを監視する

Slack 電子情報開示コネクタを作成した後は、コネクタの状態を [電子情報開示] Microsoft 365 コンプライアンス センター。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。

2. [コネクタ **] タブをクリック** し **、Slack 電子情報開示** コネクタを選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。  このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。