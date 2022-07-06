---
title: Microsoft 365 で Zoom Meetings データをアーカイブするためのコネクタを設定する
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
description: 管理者は、Veritas Zoom Meetings から Microsoft 365 にデータをインポートおよびアーカイブするためのコネクタを設定できます。 これにより、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできるため、訴訟ホールド、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 3a2d63071ba29baa40c8d7a656e7e7437f9348bd
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66631361"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Zoom Meetings データをアーカイブするコネクタを設定する

Microsoft Purview コンプライアンス ポータルの Veritas コネクタを使用して、Zoom Meetings から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。 Veritas には、サード パーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Zoom Meetings](https://globanet.com/zoom/) コネクタが用意されています。 コネクタは、会議のコンテンツ (チャット、記録されたファイル、メタデータを含む) を Zoom Meetings アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

Zoom Meetings データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft Purview 機能を適用できます。 Zoom Meetings コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-zoom-meetings-data"></a>Zoom Meetings データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 で Zoom Meetings データをアーカイブするプロセスについて説明します。

![Zoom Meetings アーカイブ ワークフロー。](../media/ZoomMeetingsConnectorWorkflow.png)

1. 組織は Zoom Meetings と連携して、Zoom Meetings サイトを設定および構成します。

2. 24 時間に 1 回、Zoom Meetings の会議アイテムが Veritas Merge1 サイトにコピーされます。 また、コネクタは会議の内容を電子メール メッセージ形式に変換します。

3. コンプライアンス ポータルで作成する Zoom Meetings コネクタは、毎日 Veritas Merge1 に接続し、会議メッセージを Microsoft クラウド内の安全な Azure Storage の場所に転送します。

4. コネクタは、手順 3. の説明に従って、 *電子メール* プロパティの値と自動ユーザー マッピングを使用して、変換された会議アイテムを特定のユーザーのメールボックスにインポートします。 **Zoom Meetings** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー メールボックスに作成され、会議アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを行います。 すべての会議アイテムにはこのプロパティが含まれています。このプロパティには、会議のすべての参加者のメール アドレスが入力されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタの Veritas Merge1 アカウントを作成します。 このアカウントを作成するには、 [Veritas カスタマー サポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。 手順 1 でコネクタを作成するときに、このアカウントにサインインします。

- 組織の Zoom Business または Zoom Enterprise アカウントのユーザー名とパスワードを取得します。 Zoom Meetings コネクタを構成するときは、手順 2. でこのアカウントにサインインする必要があります。

- [Zoom Marketplace](https://marketplace.zoom.us) で次のアプリケーションを作成します。

  - OAuth アプリケーション

  - JWT アプリケーション

  これらのアプリケーションを作成すると、Zoom プラットフォームはトークンの生成に使用される一意の資格情報のセットを生成します。 これらのトークンは、Zoom アカウントに接続し、項目を Merge1 サイトにコピーするときにコネクタを認証するために使用されます。 これらのトークンは、手順 2 で Zoom コネクタを構成するときに使用します。

  OAuth および JWT アプリケーションを作成する方法の詳細な手順については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)参照してください。

- 手順 1 で Zoom Meetings コネクタを作成し、手順 3 で完了したユーザーには、Data Connector 管理 ロールを割り当てる必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この Veritas データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境でパブリック プレビュー段階にあります。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>手順 1: Zoom Meetings コネクタを設定する

最初の手順では、コンプライアンス ポータルで **データ コネクタ** にアクセスし、Zoom Meetings コネクタを作成します。

1. **[データ コネクタ****] ズーム会議** に [https://compliance.microsoft.com](https://compliance.microsoft.com/)移動し、[データ コネクタ > ] をクリックします。

2. Zoom **Meetings 製品の** 説明ページで、[ **コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインしてコネクタを構成します。

## <a name="step-2-configure-the-zoom-meetings-connector"></a>手順 2: Zoom Meetings コネクタを構成する

2 番目の手順は、Merge1 サイトで Zoom Meetings コネクタを構成することです。 Veritas Merge1 サイトで Zoom Meetings コネクタを構成する方法の詳細については、「 [Merge1 サード パーティ コネクタ ユーザー ガイド」を](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)参照してください。

[ **保存&完了**] をクリックすると、コンプライアンス ポータルのコネクタ ウィザードの **[ユーザー マッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

1. [ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、自動ユーザー マッピングを有効にします。

   Zoom Meetings アイテムには、組織内のユーザーのメール *アドレスを含* む Email というプロパティが含まれます。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合、アイテムはそのユーザーのメールボックスにインポートされます。

2. [ **次へ**] をクリックして設定を確認し、[ **データ コネクタ** ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>手順 4: Zoom Meetings コネクタを監視する

Zoom Meetings コネクタを作成した後、コンプライアンス ポータルでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションにある **[データ コネクタ** ] に移動してクリックします。

2. [ **コネクタ** ] タブをクリックし、[ **会議のズーム** ] コネクタを選択してポップアップ ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. **[コネクタの状態とソース**] で、[**ログのダウンロード**] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。 詳細については、「 [データ コネクタの管理者ログを表示する」を](data-connector-admin-logs.md)参照してください。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。

- Zoom Meetings コネクタを機能させるには、Zoom Meetings を設定するときに録音を有効にする必要があります。