---
title: SMS/MMS ネットワークデータ&のアーカイブへのコネクタの設定
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
description: 管理者は、TeleMessage コネクタをセットアップして、AT&のモバイルネットワークから SMS および MMS データをインポートおよびアーカイブすることができます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 87974fd18f0e0a7c824e81231418ccf1c838b636
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200252"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data"></a>SMS/MMS データ&のアーカイブへのコネクタの設定

Microsoft 365 コンプライアンスセンターの TeleMessage コネクタを使用して、SMS および MMS データを&のモバイルネットワークからインポートおよびアーカイブします。 コネクタをセットアップして構成した後は、組織の&のネットワークに毎日接続し、SMS および MMS データを Microsoft 365 のメールボックスにインポートします。

SMS および MMS のメッセージをユーザーのメールボックスに格納した後、訴訟ホールド、コンテンツ検索、Microsoft 365 のアイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を&T ネットワークデータに適用できます。 たとえば、コンテンツ検索を使用してネットワークデータ&を検索したり、保管担当者のネットワークコネクタデータを&含むメールボックスを高度な電子情報開示ケースのに関連付けることができます。 Microsoft 365 でデータをインポートおよびアーカイブするために AT&T ネットワークコネクタを使用することにより、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-att-network-data"></a>&T ネットワークデータでのアーカイブの概要

次の概要は、コネクタを使用して Microsoft 365 の&T ネットワークデータにアーカイブする方法について説明しています。

![AT&T Network のアーカイブワークフロー](../media/ATTNetworkConnectorWorkflow.png)

1. 組織は TeleMessage を使用して、AT&T ネットワークコネクタを設定します。 詳細については、「 [AT&T Network Archiver](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/)」を参照してください。

2. 24時間ごとに、組織の&T ネットワークの SMS および MMS メッセージは TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンスセンターで作成した AT&T ネットワークコネクタが、毎日 TeleMessage サイトに接続し、SMS および MMS メッセージを、過去24時間から Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。 また、このコネクタは、SMS メッセージと MMS メッセージの内容を電子メールメッセージ形式に変換します。

4. コネクタは、特定のユーザーのメールボックスにモバイル通信アイテムをインポートします。 [ **&** ] という名前の新しいフォルダーがユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メールアドレス* プロパティの値を使用して、このマッピングを行います。 すべての SMS および MMS メッセージには、このプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メールアドレスが設定されます。
 
   *ユーザーの電子メールアドレス*プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを定義することもできます。 このマッピングファイルには、組織内のユーザーの携帯電話番号と、対応する Microsoft 365 メールアドレスが含まれています。 自動ユーザーマッピングとカスタムマッピングの両方を有効にした場合、すべての電子メールアイテムに対して、コネクタは最初にカスタムマッピングファイルを参照します。 携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタはインポートしようとしているアイテムの [電子メールアドレス] プロパティの値を使用します。 コネクタがカスタムマッピングファイルまたは電子メールアイテムの電子メールアドレスプロパティに有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

&T ネットワークデータでアーカイブするために必要な実装手順の一部は、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に完了する必要があります。

- [Mobile archiver service を TeleMessage から](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)注文して、組織の有効な管理アカウントを取得します。 コンプライアンスセンターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- TeleMessage のオンプレ&T のアカウントと請求先の連絡先の詳細を取得して、&T からメッセージアーカイブサービスの注文を行うことができるようにします。

- TeleMessage アカウントで、SMS/MMS ネットワークアーカイブを&する必要があるすべてのユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントに使用しているのと同じ電子メールアドレスを使用してください。

- 従業員は、社内所有の携帯電話と会社が責任を負い、AT&のモバイルネットワークに設置する必要があります。 Microsoft 365 のメッセージのアーカイブは、従業員が所有している場合、または "独自のデバイス (BYOD) デバイスを使用している場合には利用できません。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この同意を得るには、コネクタを作成する必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Microsoft 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 AT&T ネットワークコネクタを正常に作成するには、この手順を完了する必要があります。

- AT&T ネットワークコネクタを作成したユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="create-a-att-network-connector"></a>AT&T ネットワークコネクタを作成する

前のセクションで説明されている前提条件を完了した後、Microsoft 365 コンプライアンスセンターで、AT&T ネットワークコネクタを作成できます。 コネクタは、提供された情報を使用して、TeleMessage サイトに接続し、SMS および MMS メッセージを Microsoft 365 の対応するユーザーメールボックスに転送します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データコネクタ**] をクリックし  \  **&T Network**] をクリックします。

2. [ **AT&T Network product** description] ページで、[**コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[ **次へ**] をクリックします。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage のパスワードを入力します。

5. コネクタが作成されたら、ポップアップウィンドウを閉じて次のページに進むことができます。

6. [ **ユーザーマッピング** ] ページで、[自動ユーザーマッピング] を有効にします。 カスタムマッピングを有効にするには、ユーザーマッピング情報を含む CSV ファイルをアップロードし、[ **次へ**] をクリックします。

7. 管理者の同意を得てから、[ **次へ**] をクリックします。

   管理者の同意を得るには、Office 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。 

8. 設定内容を確認し、[ **完了** ] をクリックしてコネクタを作成します。

9. コンプライアンスセンターの [**データコネクタ**] ページで、[**コネクタ**] タブに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きいアイテムのサポートは、後日提供されます。
