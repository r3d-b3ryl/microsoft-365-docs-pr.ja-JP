---
title: Microsoft 365 で会議のデータをアーカイブするためのコネクタの設定
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
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Globanet の会議から Microsoft 365 にデータをインポートしてアーカイブするためのコネクタを設定できます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 6b2f5f0b61eb2d569ad49d8f58c7e03d11cdbca0
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405498"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data-preview"></a>アーカイブへのコネクタの設定アーカイブ会議データ (プレビュー)

Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、ズーム会議のデータを Microsoft 365 組織のユーザーのメールボックスにインポートし、アーカイブします。 Globanet では、サードパーティのデータソースからアイテムを取得するように構成された (定期的に)、そのアイテムをズームするための [会議](https://globanet.com/zoom/) コネクタが用意されており、それらのアイテムを Microsoft 365 にインポートします。 コネクタは会議のコンテンツ (チャット、記録されたファイル、およびメタデータを含む) を電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーメールボックスにインポートします。

ズーム会議データがユーザーのメールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Microsoft 365 でデータをインポートおよびアーカイブするためにズーム会議コネクタを使用することにより、組織は政府および規制ポリシーに準拠したままにすることができます。

## <a name="overview-of-archiving-zoom-meetings-data"></a>アーカイブズーム会議データの概要

次の概要では、コネクタを使用して Microsoft 365 の会議データをアーカイブするプロセスについて説明します。

![余裕期間電子情報開示アーカイブワークフロー](../media/ZoomMeetingsConnectorWorkflow.png)

1. 組織は、会議のズームサイトをセットアップして構成するために、ズーム会議を処理します。

2. 24時間ごとに、ズーム会議からの会議アイテムは Globanet Merge1 サイトにコピーされます。 また、コネクタは、会議の内容を電子メールメッセージの形式に変換します。

3. Microsoft 365 コンプライアンスセンターで作成するズーム会議コネクタは、Globanet Merge1 に毎日接続し、Microsoft クラウド内のセキュリティで保護された Azure ストレージの場所に会議メッセージを転送します。

4. このコネクタは、手順3で説明されているように、 *電子メール* プロパティの値と自動ユーザーマッピングを使用して、変換された会議アイテムを特定のユーザーのメールボックスにインポートします。 ユーザーのメールボックスには、" **ズーム会議** " という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、会議アイテムはそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを実行します。 すべての会議アイテムには、会議のすべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 これを行うには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。 手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 組織の拡大または縮小のエンタープライズアカウントのユーザー名とパスワードを取得します。 会議コネクタをズームするには、手順2でこのアカウントにサインインする必要があります。

- [ズーム Marketplace](https://marketplace.zoom.us)で以下のアプリケーションを作成します。

  - OAuth アプリケーション

  - JWT アプリケーション

  これらのアプリケーションを作成した後、Zoom プラットフォームは、トークンの生成に使用される一意の資格情報のセットを生成します。 これらのトークンは、拡大/縮小アカウントに接続してアイテムを Merge1 サイトにコピーするときにコネクタを認証するために使用されます。 これらのトークンは、手順2でズームコネクタを構成するときに使用します。

  OAuth および JWT アプリケーションを作成する手順については、「 [Merge1 サードパーティコネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)」を参照してください。

- 手順1で [ズーム] 会議コネクタを作成する (および手順3で完了する) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てられている必要があります。 この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>手順 1: ズーム会議コネクタを設定する

最初の手順として、Microsoft 365 コンプライアンスセンターの **データコネクタ** にアクセスし、会議コネクタのズームを作成します。

1. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) 、[**データコネクタ**] [  >  **会議のズーム**] をクリックします。

2. [会議製品の説明を **拡大/縮小** する] ページで、[ **コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインして、コネクタを構成します。

## <a name="step-2-configure-the-zoom-meetings-connector"></a>手順 2: ズーム会議コネクタを構成する

2番目の手順では、Merge1 サイト上のズーム会議コネクタを構成します。 Globanet Merge1 サイトにズーム会議コネクタを構成する方法の詳細については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)」を参照してください。

[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター (コネクタウィザードの [ **ユーザーマッピング** ] ページ) に戻ることができます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップしてコネクタのセットアップを完了する

1. [ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。

   会議アイテムをズームするには、組織内のユーザーの電子メールアドレスを含む *電子メール* というプロパティを含みます。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。

2. [ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。 Microsoft サイトにリダイレクトされます。 同意を得るには、[ **承諾** ] をクリックします。
  
   組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

3. [ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>手順 4: ズーム会議コネクタを監視する

ズーム会議コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。

2. [ **コネクタ** ] タブをクリックし、[ **ミーティングのズーム** コネクタ] を選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。

3. [ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。

- 会議のズームコネクタを機能させるには、ズーム会議を設定するときに録画を有効にする必要があります。
