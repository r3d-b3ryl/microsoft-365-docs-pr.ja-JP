---
title: Microsoft 365 で Webex Teams データへのコネクタを設定する
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
description: 管理者は、Microsoft 365 の Veritas の Webex Teams コネクタからデータをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできるため、訴訟ホールド、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 1a1823c4928ac310aa3bbfe7b5c6e0a26408f964
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66621273"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Webex Teams データをアーカイブするコネクタを設定する

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Webex Teams から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas には [、Webex Teams の](https://globanet.com/webex-teams/) 通信項目をキャプチャして Microsoft 365 にインポートするように構成された Webex Teams コネクタが用意されています。 コネクタは、Webex Teams のコンテンツ (1 対 1 チャット、グループ会話、チャネル会話、組織の Webex Teams アカウントからの添付ファイルなど) をメール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

Webex Teams データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft Purview 機能を適用できます。 Webex Teams コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-webex-teams-data"></a>Webex Teams データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 で Webex Teams データをアーカイブするプロセスについて説明します。

![Webex Teams データのアーカイブ ワークフロー。](../media/WebexTeamsConnectorWorkflow.png)

1. 組織は Webex Teams と連携して、Webex Teams サイトを設定および構成します。

2. 24 時間に 1 回、Webex Teams アイテムは Veritas Merge1 サイトにコピーされます。 また、コネクタは Webex Teams アイテムを電子メール メッセージ形式に変換します。

3. コンプライアンス ポータルで作成した Webex Teams コネクタは、毎日 Veritas Merge1 に接続し、Webex Teams アイテムを Microsoft クラウドの安全な Azure Storage の場所に転送します。

4. コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup). の説明に従って、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテムをインポートします。 **Webex Teams** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを行います。 すべての Webex Teams アイテムにはこのプロパティが含まれています。このプロパティには、アイテムのすべての参加者の電子メール アドレスが入力されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Veritas Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- Webex Teams アカウントからデータをフェッチするアプリケーション [https://developer.webex.com/](https://developer.webex.com) を作成します。 アプリケーションの作成に関する詳細な手順については、「[Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)参照してください。

   このアプリケーションを作成すると、Webex プラットフォームによって一意の資格情報のセットが生成されます。 これらの資格情報は、グローバル マージ 1 サイトで Webex Teams コネクタを構成するときに、手順 2 で使用されます。

- 手順 1 で Webex Teams コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-webex-teams-connector"></a>手順 1: Webex Teams コネクタを設定する

最初の手順では、 **データ コネクタ** にアクセスし、 [Webex Teams](https://globanet.com/webex-teams/) コネクタを設定します。

1. **データ コネクタ** > **Webex Teams** に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動してクリックします。

2. **Webex Teams 製品** の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>手順 2: Veritas Merge1 サイトで Webex Teams コネクタを構成する

2 番目の手順では、Merge1 サイトで Webex Teams コネクタを構成します。 Webex Teams コネクタを構成する方法については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

ユーザーをマップし、コンプライアンス ポータルでコネクタのセットアップを完了するには、次の手順に従います。

1. **[Webex Teams ユーザーを Microsoft 365 ユーザーにマップする**] ページで、自動ユーザー マッピングを有効にします。 Webex Teams アイテム *には、組織内* のユーザーの電子メール アドレスを含む Email というプロパティが含まれています。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-webex-teams-connector"></a>手順 4: Webex Teams コネクタを監視する

Webex Teams コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、 **Webex Teams** コネクタを選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。