---
title: Android モバイルデータをアーカイブするためのコネクタの設定
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
description: 管理者は、Android 携帯電話から SMS、MMS、音声通話をインポートしてアーカイブするための TeleMessage コネクタを設定できます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 2284e09b3f04bf135435407a842f3e2c3f0648fa
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47362100"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data-preview"></a>Android mobile データをアーカイブするためのコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンスセンターの TeleMessage コネクタを使用して、SMS、MMS、音声通話、および通話ログを Android 携帯電話からインポートおよびアーカイブします。 コネクタをセットアップして構成した後は、組織の TeleMessage アカウントに毎日接続し、TeleMessage Android Archiver を使用して従業員のモバイルコミュニケーションを Microsoft 365 のメールボックスにインポートします。

Android 携帯電話からのデータがユーザーのメールボックスに保存された後、訴訟ホールド、コンテンツ検索、Microsoft 365 のアイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を Android Archiver データに適用することができます。 たとえば、コンテンツ検索を使用して Android Archiver mobile コミュニケーションを検索したり、Android Archiver コネクタのデータを含むメールボックスを保管担当者に関連付けて高度な電子情報開示ケースで検索したりできます。 Android Archiver connector を使用して Microsoft 365 のデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠したままにすることができます。

## <a name="overview-of-archiving-android-mobile-data"></a>Android モバイルデータのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 で Android モバイルデータをアーカイブするプロセスについて説明します。

![Android Archiver connector ワークフロー](../media/AndroidArchiverConnectorWorkflow.png)

1. 組織は TeleMessage を使用して Android アーカイバコネクタを設定します。 詳細については、「 [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/)」を参照してください。

2. 24時間ごとに、SMS、MMS、音声呼び出し、組織の Android 携帯電話からの通話ログが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンスセンターで作成した Android Archiver connector は、TeleMessage サイトに毎日接続して、過去24時間の Android データを Microsoft クラウド内のセキュリティで保護された Azure ストレージの場所に転送します。 また、このコネクタは、Android データを電子メールメッセージ形式に変換します。

4. コネクタは、特定のユーザーのメールボックスにモバイル通信アイテムをインポートします。 Android Archiver という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メールアドレス* プロパティの値を使用してマッピングを行います。 すべての電子メールメッセージにはこのプロパティが含まれており、電子メールメッセージのすべての参加者の電子メールアドレスが設定されます。 *ユーザーの電子メールアドレス*プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを定義することもできます。 このマッピングファイルには、ユーザーの携帯電話番号と、各ユーザーの対応する Microsoft 365 メールボックスアドレスが含まれている必要があります。 自動ユーザーマッピングを有効にしてカスタムマッピングを指定すると、コネクタはまずカスタムマッピングファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタは電子メールアイテムのユーザーの電子メールアドレスプロパティを使用します。 コネクタが、カスタムマッピングファイル、または電子メールアイテムの *ユーザーの電子メールアドレス* プロパティに有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

Android の通信データをアーカイブするために必要ないくつかの実装手順は、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から Android Archiver service](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文して、組織の有効な管理アカウントを取得します。 コネクタを作成するときに、このアカウントにサインインする必要があります。

- Android Archiver service を必要とするすべてのユーザーを TeleMessage アカウントに登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントに使用しているのと同じ電子メールアドレスを使用してください。

- 従業員の携帯電話に TeleMessage Android Archiver アプリをインストールしてアクティブ化します。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この同意を得るには、コネクタを作成する必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Microsoft 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 AT&T ネットワークコネクタを正常に作成するには、この手順を完了する必要があります。

- Android アーカイバコネクタを作成するユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="create-an-android-archiver-connector"></a>Android アーカイバコネクタを作成する

最後の手順では、Microsoft 365 コンプライアンスセンターで Android アーカイバコネクタを作成します。 コネクタは、提供された情報を使用して、TeleMessage サイトに接続し、Android の通信を Microsoft 365 の対応するユーザーメールボックスに転送します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) して、[**データコネクタ**  >  **Android Archiver**] をクリックします。

2. [ **Android Archiver** 製品の説明] ページで、[ **コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[ **次へ**] をクリックします。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage のパスワードを入力します。

5. コネクタが作成されたら、ポップアップウィンドウを閉じ、[ **次へ**] をクリックします。

6. [ **ユーザーマッピング** ] ページで、[ユーザーマッピングの自動設定] を有効にして、[ **次へ**] をクリックします。 カスタムマッピングが必要な場合は、CSV ファイルをアップロードし、[ **次へ**] をクリックします。

7. 管理者の同意を得てから、[ **次へ**] をクリックします。

   管理者の同意を得るには、Office 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

8. 設定内容を確認し、[ **完了** ] をクリックしてコネクタを作成します。

9. [ **データコネクタ** ] ページの [コネクタ] タブに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。
