---
title: TeleMessage エンタープライズ番号 Archiver からデータをアーカイブするためのコネクタの設定
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
description: 管理者は、TeleMessage Enterprise 番号 Archiver から SMS および MMS データをインポートしてアーカイブするためのコネクタを設定できます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 1152c5e1d658e33e3056873d2230f6f94e58adc1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200164"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>エンタープライズ数値データをアーカイブするためのコネクタの設定

Microsoft 365 コンプライアンスセンターの TeleMessage コネクタを使用して、短いメッセージングサービス (SMS) およびマルチメディアメッセージングサービス (MMS) メッセージ、チャットメッセージ、音声通話、音声通話の記録をエンタープライズ番号の Archiver からインポートおよびアーカイブします。 コネクタをセットアップして構成した後は、組織の TeleMessage アカウントに毎日接続し、TeleMessage エンタープライズ番号 Archiver を使用して従業員のモバイル通信データを Microsoft 365 のメールボックスにインポートします。

TeleMessage Enterprise Number Archiver connector データがユーザーのメールボックスに格納された後は、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、通信コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能をエンタープライズ番号の Archiver データに適用することができます。 たとえば、コンテンツ検索を使用して TeleMessage エンタープライズ番号のアーカイバ、MMS、および音声通話を検索したり、高度な電子情報開示ケースの保管担当者にエンタープライズ番号の Archiver コネクタデータを含むメールボックスを関連付けたりすることができます。 Microsoft 365 でデータをインポートおよびアーカイブするためにエンタープライズ電話番号 Archiver connector を使用することにより、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-enterprise-number-data"></a>エンタープライズ番号データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 のエンタープライズネットワークデータをアーカイブするプロセスについて説明します。

![エンタープライズ番号のアーカイブワークフロー](../media/EnterpriseNumberConnectorWorkflow.png)

1. 組織は TeleMessage を使用して、エンタープライズ番号アーカイバコネクタを設定します。 詳細について [は、ここ](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)を参照してください。

2. Microsoft 365 コンプライアンスセンターで作成したエンタープライズ番号アーカイバコネクタは、TeleMessage サイトに毎日接続し、電子メールメッセージを、過去24時間から Microsoft クラウド内のセキュアな Azure ストレージ領域に転送します。

3. コネクタは、特定のユーザーのメールボックスにモバイル通信アイテムをインポートします。 エンタープライズ番号 Archiver という新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メールアドレス* プロパティの値を使用してマッピングを行います。 すべての電子メールメッセージにはこのプロパティが含まれており、電子メールメッセージのすべての参加者の電子メールアドレスが設定されます。 *ユーザーの電子メールアドレス*プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを定義することもできます。 このマッピングファイルには、ユーザーの携帯電話番号と、各ユーザーの対応する Microsoft 365 メールボックスアドレスが含まれている必要があります。 自動ユーザーマッピングを有効にしてカスタムマッピングを指定すると、コネクタはまずカスタムマッピングファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタは電子メールアイテムのユーザーの電子メールアドレスプロパティを使用します。 コネクタが、カスタムマッピングファイル、または電子メールアイテムの *ユーザーの電子メールアドレス* プロパティに有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

エンタープライズ番号の Archiver データをアーカイブするために必要ないくつかの実装手順は、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に完了する必要があります。

- [TeleMessage からエンタープライズ電話番号 Archiver サービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文して、組織の有効な管理アカウントを取得します。 コンプライアンスセンターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- エンタープライズ番号を必要とするすべてのユーザーを TeleMessage アカウントに登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントに使用しているのと同じ電子メールアドレスを使用してください。

- 従業員の携帯電話に TeleMessage Enterprise 番号 Archiver アプリをインストールしてアクティブ化します。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この同意を得るには、コネクタを作成する必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Microsoft 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 Bell ネットワークコネクタを正常に作成するには、この手順を完了する必要があります。

- エンタープライズ番号アーカイバコネクタを作成するユーザーには、Exchange Online の Mailbox Import Export 役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="create-an-enterprise-number-archiver-connector"></a>エンタープライズ番号アーカイバコネクタを作成する

前のセクションで説明した前提条件を完了した後、Microsoft 365 コンプライアンスセンターでエンタープライズ電話番号アーカイバコネクタを作成できます。 コネクタは、提供された情報を使用して、TeleMessage サイトに接続し、SMS、MMS、および音声通話メッセージを Microsoft 365 の対応するユーザーメールボックスに転送します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **データコネクタ** \> **エンタープライズ番号 Archiver**] をクリックします。

2. [**エンタープライズ番号 Archiver**製品の説明] ページで、[**コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[ **次へ**] をクリックします。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage のパスワードを入力します。

5. コネクタが作成されたら、ポップアップウィンドウを閉じて次のページに進むことができます。

6. [ **ユーザーマッピング** ] ページで、[自動ユーザーマッピング] を有効にします。 カスタムマッピングを有効にするには、ユーザーマッピング情報を含む CSV ファイルをアップロードし、[ **次へ**] をクリックします。

7. 管理者の同意を得てから、[ **次へ**] をクリックします。

   管理者の同意を得るには、Office 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

8. 設定内容を確認し、[ **完了** ] をクリックしてコネクタを作成します。

9. [ **データコネクタ** ] ページの [コネクタ] タブに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きいアイテムのサポートは、後日提供されます。
