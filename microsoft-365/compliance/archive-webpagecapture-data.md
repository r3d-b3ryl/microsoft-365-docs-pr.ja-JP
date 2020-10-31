---
title: Microsoft 365 の web ページデータをアーカイブするためのコネクタの設定
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
description: 管理者は、Microsoft 365 の Globanet から Web ページのキャプチャデータをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 712e41d84181199ae72de51e0fd834085b2174d0
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816746"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a>Web ページデータをアーカイブするためのコネクタの設定

Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、web ページのデータをインポートし、Microsoft 365 組織のユーザーのメールボックスにアーカイブします。 Globanet には、特定の web サイトまたはドメイン全体の特定の web ページ (およびそれらのページ上のすべてのリンク) をキャプチャする [Web ページキャプチャ](https://globanet.com/webpage-capture) コネクタが用意されています。 コネクタは、web ページのコンテンツを PDF、PNG、またはカスタムのファイル形式に変換し、変換されたファイルを電子メールメッセージに添付した後、それらの電子メールアイテムを Microsoft 365 のユーザーメールボックスにインポートします。

ユーザーのメールボックスに web ページコンテンツが格納されると、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。 Microsoft 365 で Web ページキャプチャコネクタを使用してデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠したままにすることができます。

## <a name="overview-of-archiving-webpage-data"></a>Web ページのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の web ページコンテンツをアーカイブするプロセスについて説明します。

![Web ページデータのアーカイブワークフロー](../media/WebPageCaptureConnectorWorkflow.png)

1. 組織は web ページソースを使用して、Web ページキャプチャサイトをセットアップして構成します。

2. 24時間ごとに、web ページのソースアイテムが Globanet Merge1 サイトにコピーされます。 コネクタは、web ページのコンテンツを変換し、電子メールメッセージに添付します。

3. Microsoft 365 コンプライアンスセンターで作成した Web ページキャプチャコネクタは、毎日 Globanet Merge1 サイトに接続し、その web ページアイテムを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。

4. このコネクタは、 [手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換された web ページアイテムを特定のユーザーのメールボックスにインポートします。 Web ページの **キャプチャ** という名前の受信トレイフォルダー内のサブフォルダーがユーザーのメールボックスに作成され、そのフォルダーに web ページのアイテムがインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを実行します。 すべての web ページアイテムには、このプロパティが含まれており、 [手順 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)で Web ページキャプチャコネクタを構成するときに提供される電子メールアドレスが設定されます。

## <a name="before-you-begin"></a>はじめに

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 このアカウントを作成するには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact/)に問い合わせてください。 このアカウントは、手順1でコネクタを作成するときにサインインします。

- Web ページのアイテムをに変換するためのカスタムファイル形式を設定するには、Globanet サポートと連携する必要があります。 詳細については、「Merge1 サードパーティコネクタのユーザーガイド」を参照してください。 

- 手順1で Web ページキャプチャコネクタを作成したユーザー (および手順3で完了します) は、Exchange Online のメールボックスインポートエクスポート役割に割り当てられている必要があります。 この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online の役割グループに割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-set-up-the-webpage-capture-connector"></a>手順 1: Web ページキャプチャコネクタを設定する

最初の手順として、 **データコネクタ** にアクセスして、Web ページソースデータのコネクタを作成します。

1. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) 、[ **データコネクタ**  >  **web ページキャプチャ** ] をクリックします。

2. [ **Web ページのキャプチャ** 製品の説明] ページで、[ **コネクタの追加** ] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ** ] をクリックします。

5. Merge1 アカウントにサインインして、コネクタを構成します。

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a>手順 2: Globanet Merge1 サイトで Web ページキャプチャコネクタを構成する

2番目の手順は、Globanet Merge1 サイトで Web ページキャプチャコネクタを構成することです。 Web ページキャプチャコネクタを構成する方法については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)」を参照してください。

[ **保存 & 完了** ] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップしてコネクタのセットアップを完了する

ユーザーをマップして、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。

1. [ **Web ページを Microsoft 365 ユーザーにキャプチャする** ] ページで、自動ユーザーマッピングを有効にします。 Web ページのキャプチャアイテムには、 *電子メール* というプロパティが含まれています。このプロパティには、組織内のユーザーの電子メールアドレスが含まれています。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。

2. [ **管理者の同意** ] ページで、[ **同意を提供** する] をクリックします。 Microsoft サイトにリダイレクトされます。 同意を得るには、[ **承諾** ] をクリックします。

   組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

3. [ **次へ** ] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="step-4-monitor-the-webpage-capture-connector"></a>手順 4: Web ページキャプチャコネクタを監視する

Web ページキャプチャコネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[ **データコネクタ** ] をクリックします。

2. [ **コネクタ** ] タブをクリックし、[ **Web ページ] キャプチャ** コネクタを選択して、フライアウトページを表示します。 このページには、コネクタに関するプロパティと情報が含まれています。

3. [ **コネクタの状態 (ソース付き** )] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータが含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きいアイテムのサポートは、後日提供されます。
