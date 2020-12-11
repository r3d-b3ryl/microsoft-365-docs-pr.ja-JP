---
title: Microsoft 365 でズーム会議データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet Zoom Meetings から Microsoft 365 にデータをインポートおよびアーカイブするコネクタを設定できます。 これにより、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: c61c9a40d85b3bea266df9b1f2dba32301e54e08
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620203"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>ズーム会議データをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Zoom Meetings から Microsoft 365 組織のユーザー メールボックスにデータをインポートしてアーカイブします。 Globanet は、サード パーティのデータ ソースから (定期的に) アイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された Zoom [Meetings](https://globanet.com/zoom/) コネクタを提供します。 コネクタは、会議のコンテンツ (チャット、記録されたファイル、メタデータを含む) を Zoom Meetings アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。

ズーム会議のデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Zoom Meetings コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-zoom-meetings-data"></a>ズーム会議データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 のズーム会議データをアーカイブするプロセスについて説明します。

![会議のアーカイブ ワークフローのズーム](../media/ZoomMeetingsConnectorWorkflow.png)

1. 組織はズーム会議と共同で、ズーム会議サイトをセットアップおよび構成します。

2. 24 時間ごとに、Zoom Meetings の会議アイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、会議の内容を電子メール メッセージ形式に変換します。

3. Microsoft 365 コンプライアンス センターで作成した Zoom Meetings コネクタは、毎日 Globanet Merge1 に接続し、会議メッセージを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。

4. コネクタは、手順 3 で説明するように *、Email* プロパティの値と自動ユーザー マッピングを使用して、変換された会議アイテムを特定のユーザーのメールボックスにインポートします。 Zoom **Meetings** という名前の受信トレイ フォルダーに新しいサブフォルダーがユーザー メールボックスに作成され、会議アイテムがフォルダーにインポートされます。 コネクタは、Email プロパティの値を使用して *これを行* います。 すべての会議アイテムには、このプロパティが含まれるので、会議のすべての参加者の電子メール アドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。 このアカウントは、手順 1 でコネクタを作成するときにサインインします。

- 組織の Zoom Business アカウントまたは Zoom Enterprise アカウントのユーザー名とパスワードを取得します。 Zoom Meetings コネクタを構成する場合は、手順 2 でこのアカウントにサインインする必要があります。

- Zoom Marketplace で次のアプリケーション [を作成します](https://marketplace.zoom.us)。

  - OAuth アプリケーション

  - JWT アプリケーション

  これらのアプリケーションを作成すると、Zoom プラットフォームはトークンの生成に使用される一意の資格情報のセットを生成します。 これらのトークンは、Zoom アカウントに接続してアイテムを Merge1 サイトにコピーするときにコネクタを認証するために使用されます。 これらのトークンは、手順 2 でズーム コネクタを構成するときに使用します。

  OAuth アプリケーションと JWT アプリケーションを作成する方法の詳細な手順については [、「Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)」を参照してください。

- 手順 1 で Zoom Meetings コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。 この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていない。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>手順 1: 会議のズーム コネクタを設定する

最初の手順は、Microsoft 365 コンプライアンス センターの **Data Connector に** アクセスし、Zoom Meetings コネクタを作成することです。

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **Zoom Meetings**.

2. [ **会議のズーム] 製品の** 説明ページで、[コネクタの追加] **をクリックします**。

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。

5. コネクタを構成するには、Merge1 アカウントにサインインします。

## <a name="step-2-configure-the-zoom-meetings-connector"></a>手順 2: 会議のズーム コネクタを構成する

2 番目の手順は、Merge1 サイトで会議のズーム コネクタを構成することです。 Globanet Merge1 サイトで Zoom Meetings コネクタを構成する方法の詳細については [、「Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)」を参照してください。

[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップし、コネクタのセットアップを完了する

1. [外部ユーザー **を Microsoft 365 ユーザーに** マップする] ページで、自動ユーザー マッピングを有効にします。

   会議アイテムのズームには、組織内のユーザーの電子メール アドレスを含む [電子メール] というプロパティが含まれます。 コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。

2. [**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>手順 4: 会議のズーム コネクタを監視する

Zoom Meetings コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [ **コネクタ] タブをクリック** し、[ **会議コネクタのズーム]** を選択して、フライアウト ページを表示します。 このページには、コネクタに関するプロパティと情報が含まれる。

3. [**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。

- Zoom Meetings コネクタが機能するには、Zoom Meetings を設定するときにレコーディングを有効にする必要があります。
