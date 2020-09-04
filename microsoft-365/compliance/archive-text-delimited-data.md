---
title: Microsoft 365 でテキスト区切りのデータをアーカイブするためのコネクタの設定
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
description: 管理者は、Globanet から Microsoft 365 にテキスト区切りのデータをインポートしてアーカイブするためのコネクタを設定できます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 989c0a657d9a30156e5991d5b09e389c0b044332
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361862"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data-preview"></a>テキスト区切りのデータをアーカイブするようにコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、テキスト区切りのデータを Microsoft 365 組織のユーザーのメールボックスにインポートおよびアーカイブします。 [Globanet](https://globanet.com/merge1/) には、サードパーティのデータソースからアイテムを取得するように構成されたテキスト区切りコネクタがあり (定期的に)、それらのアイテムを Microsoft 365 にインポートします。 コネクタは、コンテンツをテキスト区切りデータソースから電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

テキスト区切りのデータがユーザーのメールボックスに格納された後は、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 Microsoft 365 でデータをインポートおよびアーカイブするためにズーム会議コネクタを使用することにより、組織は政府および規制ポリシーに準拠したままにすることができます。

アーカイブ後、テキスト区切りのソース通信は保持され、コンプライアンスを監視し、eDiscovery および内部情報ガバナンスのために取得することができます。

## <a name="overview-of-archiving-the-text-delimited-source"></a>テキスト区切りソースのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 のテキスト区切りのソース情報をアーカイブするプロセスについて説明します。

![テキストで区切られたデータのアーカイブワークフロー](../media/TextDelimitedConnectorWorkflow.png)

1. 組織はテキスト区切りのソースを使用して、テキスト区切りのサイトを設定し、構成します。

2. 24時間ごとに、テキスト区切りソースからのチャットメッセージが Globanet Merge1 サイトにコピーされます。 また、コネクタは、コンテンツを電子メールメッセージの形式に変換します。

3. Microsoft 365 コンプライアンスセンターで作成するテキスト区切りコネクタは、Globanet Merge1 サイトに毎日接続して、Microsoft クラウド内のセキュアな Azure ストレージの場所にメッセージを転送します。

4. このコネクタは、手順3で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換されたメッセージアイテムを特定のユーザーのメールボックスにインポートします。 [ **テキスト区切り** ] という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、ユーザーのメールボックスにメッセージアイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを実行します。 すべてのメッセージにこのプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メールアドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Globanet Merge1 アカウントを作成するには、テキスト区切りコネクタの使用条件に同意します。 これを行うには、 [Globanet カスタマーサポート](https://globanet.com/contact-us)にお問い合わせください。 手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順1でテキスト区切りコネクタを作成し、(手順3で完了する) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てられている必要があります。 この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-set-up-the-text-delimited-connector"></a>手順 1: テキスト区切りコネクタを設定する

最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、テキスト区切りのデータ用のコネクタを作成します。

1. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) て、[**データコネクタ**]  >  **テキストを区切り**ます。

2. [ **テキスト区切り** 製品の説明] ページで、[ **コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインして、コネクタを構成します。

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイト上のテキスト区切りコネクタを構成する

2番目の手順は、Merge1 サイトでテキスト区切りコネクタを構成することです。 Globanet Merge1 サイトでテキスト区切りコネクタを構成する方法については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Text-Delimited%20User%20Guide%20.pdf)」を参照してください。

[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター、コネクタウィザードの [ **ユーザーマッピング** ] ページに戻ります。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップしてコネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンスセンターで設定したコネクタを完成させるには、次の手順を実行します。

1. [ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。 テキスト区切りのソース項目には、 *電子メール*というプロパティが含まれています。これには、組織内のユーザーの電子メールアドレスが含まれます。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。

2. [ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。 Microsoft サイトにリダイレクトされます。 同意を得るには、[ **承諾** ] をクリックします。

   組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

3. [ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="step-4-monitor-the-text-delimited-connector"></a>手順 4: テキスト区切りコネクタを監視する

テキスト区切りコネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。

2. [ **コネクタ** ] タブをクリックし、 **テキスト区切り** コネクタを選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。

3. [ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。
