---
title: Microsoft 365 でのアーカイブのためのコネクタの設定 (O2) ネットワークデータ
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
description: 管理者は、TeleMessage コネクタをセットアップして、Microsoft 365 の O2 モバイルネットワークから SMS および MMS データをインポートおよびアーカイブできます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 4911e00cf8bcf641ef7f3386ff3297bf082b7f12
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282662"
---
# <a name="set-up-a-connector-to-archive-o2-network-data-preview"></a>Connector for archive O2 Network data (プレビュー)

Microsoft 365 コンプライアンスセンターの TeleMessage コネクタを使用して、O2 モバイルネットワークからの短いメッセージングサービス (SMS) メッセージと音声通話のインポートとアーカイブを行います。 コネクタをセットアップして構成した後は、組織の O2 ネットワークに毎日接続し、Microsoft 365 のメールボックスに SMS および音声呼び出しをインポートします。

SMS メッセージと音声呼び出しがユーザーのメールボックスに格納された後、訴訟ホールド、コンテンツ検索、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を、O2 ネットワークデータに適用することができます。 たとえば、コンテンツ検索を使用して、O2 ネットワークの SMS メッセージおよび音声呼び出しを検索したり、O2 ネットワークデータを含むメールボックスを高度な電子情報開示ケースの保管担当者に関連付けることができます。 Microsoft 365 のデータをインポートおよびアーカイブするために、O2 ネットワークコネクタを使用することで、組織は政府ポリシーおよび規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-o2-network-data"></a>アーカイブの O2 ネットワークデータの概要

次の概要では、コネクタを使用して Microsoft 365 の O2 ネットワークデータをアーカイブするプロセスについて説明します。

![O2 ネットワークアーカイブワークフロー](../media/O2NetworkConnectorWorkflow.png)

1. 組織は、TeleMessage と O2 を使用して、O2 ネットワークコネクタを設定します。 詳細については、「 [O2 Network Archiver](https://www.telemessage.com/office365-activation-for-o2-network-archiver)」を参照してください。

2. 24時間ごとに、組織の O2 ネットワークからの SMS メッセージと音声通話が TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンスセンターで作成した、O2 ネットワークコネクタは、毎日 TeleMessage サイトに接続し、SMS メッセージと音声呼び出しを過去24時間から Microsoft クラウド内のセキュリティで保護された Azure ストレージの場所に転送します。 また、このコネクタは、SMS メッセージの内容と音声呼び出しを電子メールメッセージの形式に変換します。

4. コネクタは、特定のユーザーのメールボックスにモバイル通信アイテムをインポートします。 **O2 SMS と Voice Network Archiver**という名前の新しいフォルダーが、特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メールアドレス* プロパティの値を使用して、このマッピングを行います。 すべての SMS メッセージと音声呼び出しには、このプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メールアドレスが設定されます。

   *ユーザーの電子メールアドレス*プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを定義することもできます。 このマッピングファイルには、組織内のユーザーの携帯電話番号と、対応する Microsoft 365 メールアドレスが含まれています。 自動ユーザーマッピングとカスタムマッピングの両方を有効にした場合、各 O2 アイテムに対して、コネクタは最初にカスタムマッピングファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタはインポートしようとしているアイテムの [電子メールアドレス] プロパティの値を使用します。 コネクタがカスタムマッピングファイルまたは O2 アイテムの電子メールアドレスプロパティに有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

O2 ネットワークデータをアーカイブするために必要な実装手順の多くは、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に、完了する必要があります。

- [TeleMessage からの O2 ネットワーク Archiver サービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)の注文を行い、組織の有効な管理アカウントを取得します。 コンプライアンスセンターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- TeleMessage のオンボードフォームに記入して、O2 からメッセージアーカイブサービスを注文できるように、O2 ネットワークアカウントと請求連絡先の詳細を取得します。

- TeleMessage アカウントに、O2 SMS および Voice Network アーカイブを必要とするすべてのユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントに使用しているのと同じ電子メールアドレスを使用してください。

- 従業員は、O2 モバイルネットワーク上で企業所有の携帯電話と会社の責任を持つ携帯電話を所有している必要があります。 Microsoft 365 のメッセージのアーカイブは、従業員が所有している場合、または "独自のデバイス (BYOD) デバイスを使用している場合には利用できません。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この同意を得るには、コネクタを作成する必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 O2 ネットワークコネクタを正常に作成するには、この手順を完了する必要があります。

- O2 ネットワークコネクタを作成するユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="create-an-o2-network-connector"></a>O2 ネットワークコネクタを作成する

前のセクションで説明した前提条件を完了したら、Microsoft 365 コンプライアンスセンターで、O2 ネットワークコネクタを作成できます。 コネクタは、提供された情報を使用して、TeleMessage サイトに接続し、SMS メッセージと音声呼び出しを Microsoft 365 の対応するユーザーメールボックスに転送します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **データコネクタ** \> **O2 ネットワーク**] をクリックします。

2. [ **O2 ネットワーク**製品の説明] ページで、[**コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[ **次へ**] をクリックします。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage のパスワードを入力します。

5. コネクタが作成されたら、ポップアップウィンドウを閉じて次のページに進むことができます。

6. [ **ユーザーマッピング** ] ページで、[ユーザーマッピングの自動設定] を有効にして、[ **次へ**] をクリックします。 カスタムマッピングが必要な場合は、CSV ファイルをアップロードし、[ **次へ**] をクリックします。

7. 管理者の同意を得てから、[ **次へ**] をクリックします。

   管理者の同意を得るには、Office 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

8. 設定内容を確認し、[ **完了** ] をクリックしてコネクタを作成します。

9. [ **データコネクタ** ] ページの [コネクタ] タブに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- コネクタは、10 MB を超えるアイテムをインポートしません。
