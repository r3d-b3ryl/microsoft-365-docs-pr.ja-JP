---
title: Microsoft 365 で FX 接続データをアーカイブするためのコネクタの設定
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
description: 管理者は、Microsoft 365 で Globanet FX Connect からデータをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 9c769088148f747e4918f2f91a244ad321d61888
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399440"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data-preview"></a>コネクタを設定して、FX 接続データをアーカイブする (プレビュー)

Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、FX Connect コラボレーションプラットフォームから Microsoft 365 組織のユーザーメールボックスへのデータのインポートとアーカイブを行います。 Globanet には、FX 接続項目をキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Fx 接続](https://globanet.com/fx-connect/) コネクタが用意されています。 コネクタは、組織の FX Connect アカウントからの、取引、メッセージ、その他の詳細などの FX Connect からのコンテンツを電子メールメッセージの形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。

FX Connect データがユーザーのメールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信のコンプライアンスなど、Microsoft 365 のコンプライアンス機能を適用できます。 Microsoft 365 でのデータのインポートおよびアーカイブに FX Connect コネクタを使用することで、組織は政府および規制ポリシーに準拠したままにすることができます。

## <a name="overview-of-archiving-fx-connect-data"></a>FX 接続データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の FX 接続情報をアーカイブするプロセスについて説明します。

![FX 接続データのアーカイブワークフロー](../media/FXConnectConnectorWorkflow.png)

1. 組織は FX Connect を使用して、FX 接続サイトを設定および構成します。

2. 24時間ごとに、FX Connect アカウントからのアイテムが Globanet Merge1 サイトにコピーされます。 また、コネクタは、FX Connect アイテムを電子メールメッセージの形式に変換します。

3. Microsoft 365 コンプライアンスセンターで作成する FX 接続コネクタは、Globanet Merge1 サイトに毎日接続し、Microsoft クラウド内のセキュアな Azure ストレージの場所に FX Connect アイテムを転送します。

4. コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの*Email*プロパティの値を使用して、特定のユーザーのメールボックスにアイテムをインポートします。 ユーザーメールボックスに [ **FX Connect** ] という名前の受信トレイフォルダー内のサブフォルダーが作成され、アイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを実行します。 すべての FX Connect アイテムには、アイテムのすべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。

## <a name="before-you-begin"></a>開始する前に

- Globanet Merge1 アカウントを作成するには、FX Connect コネクタの使用条件に同意します。 これを行うには、 [Globanet カスタマーサポート](https://globanet.com/contact-us)にお問い合わせください。 手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 手順1で FX の接続コネクタを作成したユーザー (および手順3で完了したもの) は、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。 この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-set-up-the-fx-connect-connector"></a>手順 1: FX 接続コネクタを設定する

最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、FX Connect データ用のコネクタを作成します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) して、[**データコネクタ**  >  **FX Connect**] をクリックします。

2. [ **FX Connect** 製品の説明] ページで、[ **コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインして、コネクタを構成します。

## <a name="step-2-configure-the-fx-connect-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで FX 接続コネクタを構成する

2番目の手順は、Merge1 サイトで FX Connect コネクタを構成することです。 FX 接続コネクタを構成する方法については、「 [Merge1 サードパーティコネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)」を参照してください。

[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター (コネクタウィザードの [ **ユーザーマッピング** ] ページ) に戻ることができます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップしてコネクタのセットアップを完了する

ユーザーをマップし、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。

1. [FX へのユーザーの **Microsoft 365 ユーザーへの接続** ] ページで、[自動ユーザーマッピング] を有効にします。 FX Connect 項目には、 *電子メール*というプロパティがあります。このプロパティには、組織内のユーザーの電子メールアドレスが含まれています。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。

2. [ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。 Microsoft サイトにリダイレクトされます。 同意を得るには、[ **承諾** ] をクリックします。

   組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

3. [ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="step-4-monitor-the-fx-connect-connector"></a>手順 4: FX Connect connector を監視する

FX 接続コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。

1. <https://compliance.microsoft.com/>左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。

2. [ **コネクタ** ] タブをクリックし、[ **FX Connect** コネクタ] を選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。

3. [ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。
