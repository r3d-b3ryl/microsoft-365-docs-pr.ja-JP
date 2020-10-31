---
title: Microsoft 365 で Symphony データをアーカイブするためのコネクタをセットアップする
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
description: 管理者は、Globanet Symphony から Microsoft 365 にデータをインポートしてアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: c90329f2e3a21db4073245c93e01b6593773d59f
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816530"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a>Symphony データをアーカイブするためのコネクタの設定

Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、Symphony データを Microsoft 365 組織のユーザーのメールボックスにインポートおよびアーカイブします。 Symphony は、金融サービス業界で使用されるメッセージングおよびコラボレーションのプラットフォームです。 Globanet は、Microsoft 365 コンプライアンスセンターで、サードパーティのデータソースからアイテムを取得するように構成できる [Symphony](https://globanet.com/symphony) データコネクタを (定期的に) 提供し、それらのアイテムをユーザーのメールボックスにインポートします。 コネクタは、アイテムのコンテンツを Symphony アカウントから電子メールメッセージ形式に変換し、そのアイテムを Microsoft 365 のメールボックスにインポートします。

Symphony 通信がユーザーのメールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Symphony コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることで、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-symphony-data"></a>Symphony データのアーカイブの概要

次の概要では、データコネクタを使用して Microsoft 365 の Symphony 通信をアーカイブするプロセスについて説明します。

![Symphony アーカイブワークフロー](../media/SymphonyConnectorWorkflow.png)

1. 組織は Symphony を使用して、Symphony サイトをセットアップおよび構成します。

2. 24時間ごとに、Symphony からのチャットメッセージが Globanet Merge1 サイトにコピーされます。 また、コネクタは、チャットメッセージの内容を電子メールメッセージの形式に変換します。

3. Microsoft 365 コンプライアンスセンターで作成した Symphony コネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。

4. このコネクタは、手順3で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換されたメッセージアイテムを特定のユーザーのメールボックスにインポートします。 ユーザーメールボックスに **Symphony** という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、そのフォルダーにメッセージアイテムがインポートされます。 コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。 すべてのチャットメッセージには、すべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 アカウントを作成するには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact)に問い合わせてください。 このアカウントは、手順1でコネクタを作成するときにサインインします。

- 手順1で Symphony コネクタを作成したユーザー (手順3で完了します) は、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。 この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-set-up-the-symphony-connector"></a>手順 1: Symphony コネクタを設定する

最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、Symphony データ用のコネクタを作成します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **データコネクタ** の Symphony] をクリックし  >  **Symphony** ます。

2. **Symphony** 製品の説明ページで、[ **コネクタの追加** ] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ** ] をクリックします。

5. Merge1 アカウントにサインインして、コネクタを構成します。

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a>Globanet Merge1 サイトで Symphony コネクタを構成する

2番目の手順は、Merge1 サイト上の Symphony コネクタを構成することです。 Globanet Merge1 サイト上の Symphony コネクタの構成の詳細については、「 [Merge1 サードパーティ製コネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)」を参照してください。

[ **保存 & 完了** ] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップしてコネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。

1. [ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。 Symphony のアイテムには、組織内のユーザーの電子メールアドレスを含む *email* というプロパティが含まれています。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。

2. [ **管理者の同意** ] ページで、[ **同意を提供** する] をクリックします。 Microsoft サイトにリダイレクトされます。 同意を得るには、[ **承諾** ] をクリックします。

   組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

3. [ **次へ** ] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="step-4-monitor-the-symphony-connector"></a>手順 4: Symphony コネクタを監視する

Symphony コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[ **データコネクタ** ] をクリックします。

2. [ **コネクタ** ] タブをクリックし、[ **Symphony** コネクタ] を選択して、フライアウトページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. [ **コネクタの状態 (ソース付き** )] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きいアイテムのサポートは、後日提供されます。
