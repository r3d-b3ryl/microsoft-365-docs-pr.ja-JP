---
title: Microsoft 365 で Salesforce Chatter データをアーカイブするためのコネクタを設定する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 管理者は、Veritas から Microsoft 365 に Salesforce Chatter データをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、訴訟ホールド、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 8b33e0d9d0e181035c1466cc8d7669ead4e734df
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636581"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a>Salesforce Chatter データをアーカイブするコネクタを設定する

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Salesforce Chatter プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas は、サード パーティのデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートする [Salesforce Chatter](http://globanet.com/chatter/) コネクタを提供します。 コネクタは、チャット、添付ファイル、投稿などのコンテンツを Salesforce Chatter から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Salesforce Chatter データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft Purview 機能を適用できます。 Salesforce Chatter コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-salesforce-chatter-data"></a>Salesforce Chatter データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 で Salesforce Chatter データをアーカイブするプロセスについて説明します。

![Salesforce Chatter データのアーカイブ ワークフロー。](../media/SalesforceChatterConnectorWorkflow.png)

1. 組織は Salesforce Chatter と連携して、Salesforce Chatter サイトを設定および構成します。

2. 24 時間に 1 回、Salesforce Chatter アイテムが Veritas Merge1 サイトにコピーされます。 コネクタでは、Salesforce Chatter アイテムも電子メール メッセージ形式に変換されます。

3. コンプライアンス ポータルで作成する Salesforce Chatter コネクタは、毎日 Veritas Merge1 サイトに接続し、Chatter コンテンツを Microsoft クラウドの安全な Azure Storage の場所に転送します。

4. コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup). で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックスにインポートします。 **Salesforce Chatter** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべての Chatter アイテムにはこのプロパティが含まれています。このプロパティには、アイテムのすべての参加者のメール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Merge1 アカウントを作成します。 アカウントを作成するには、 [Veritas カスタマー サポート](https://www.veritas.com/content/support/)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。

- Salesforce アプリケーションを作成し、次の時点で [https://salesforce.com](https://salesforce.com)トークンを取得します。 管理者として Salesforce アカウントにログインし、ユーザー個人トークンを取得してデータをインポートする必要があります。 また、更新、削除、および編集をキャプチャするには、トリガーを Chatter サイトに発行する必要があります。 これらのトリガーはチャネルに投稿を作成し、Merge1 はチャネルからの情報をキャプチャします。 アプリケーションを作成してトークンを取得する方法の詳細な手順については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)参照してください。

- 手順 1 で Salesforce Chatter コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>手順 1: Salesforce Chatter コネクタを設定する

最初の手順では、コンプライアンス ポータルの **[データ コネクタ** ] ページにアクセスし、Chatter データ用のコネクタを作成します。

1. **データ コネクタ** > **の Salesforce Chatter** に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動してクリックします。

2. **Salesforce Chatter** 製品の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-salesforce-chatter-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Salesforce Chatter を構成する

2 番目の手順は、Veritas Merge1 サイトで Salesforce Chatter コネクタを構成することです。 Salesforce Chatter コネクタを構成する方法については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf)参照してください。

[ **保存&完了** ] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. **[Salesforce Chatter ユーザーを Microsoft 365 ユーザーにマップする**] ページで、自動ユーザー マッピングを有効にします。 Salesforce Chatter アイテム *には、組織内* のユーザーのメール アドレスを含む Email というプロパティが含まれています。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックし、設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>手順 4: Salesforce Chatter コネクタを監視する

Salesforce Chatter コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、 **Salesforce Chatter** コネクタをクリックして、コネクタに関するプロパティと情報を含むポップアップ ページを表示します。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
