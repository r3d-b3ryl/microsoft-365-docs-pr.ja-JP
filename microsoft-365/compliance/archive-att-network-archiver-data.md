---
title: AT&T SMS/MMS ネットワーク データをアーカイブするコネクタを設定する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: 管理者は TeleMessage コネクタを設定して、AT&T Mobile Network から SMS および MMS データをインポートおよびアーカイブできます。 これにより、Microsoft Purview のサード パーティのデータ ソースからデータをアーカイブできるため、訴訟ホールド、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 1e7c3b1de79d4777beec22b0b1a5506fc8bccf6a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625877"
---
# <a name="set-up-a-connector-to-archive-att-smsmms-data"></a>AT&T SMS/MMS データをアーカイブするコネクタを設定する

MICROSOFT PURVIEW コンプライアンス ポータルの TeleMessage コネクタを使用して、AT&T Mobile Network から SMS および MMS データをインポートおよびアーカイブします。 コネクタを設定して構成すると、組織の AT&T Network に毎日 1 回接続され、SMS と MMS のデータが Microsoft Purview のメールボックスにインポートされます。

SMS および MMS メッセージがユーザー メールボックスに格納された後、訴訟ホールド、コンテンツ検索、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 Purview 機能を AT&T Network データに適用できます。 たとえば、コンテンツ検索を使用して AT&T Network データを検索したり、AT&T Network コネクタ データを含むメールボックスを電子情報開示 (Premium) ケースのカストディアンに関連付けることができます。 AT&T Network コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-att-network-data"></a>AT&T Network データのアーカイブの概要

次の概要では、コネクタを使用して MICROSOFT 365 で AT&T Network データをアーカイブするプロセスについて説明します。

![ATT Network アーカイブ ワークフロー。](../media/ATTNetworkConnectorWorkflow.png)

1. 組織は TeleMessage と連携して、AT&T Network コネクタを設定します。 詳細については、「 [AT&T Network Archiver」を](https://www.telemessage.com/office365-activation-for-atnt-network-archiver/)参照してください。

2. 組織の AT&T Network からの SMS メッセージと MMS メッセージは、リアルタイムで TeleMessage サイトにコピーされます。

3. コンプライアンス ポータルで作成した AT&T Network コネクタは、毎日 TeleMessage サイトに接続し、前の 24 時間の SMS および MMS メッセージを Microsoft クラウドのセキュリティで保護された Azure Storage の場所に転送します。 また、コネクタは SMS メッセージと MMS メッセージのコンテンツを電子メール メッセージ形式に変換します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 **AT&T SMS/MMS Network Archiver** という名前の新しいフォルダーがユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メール アドレス* プロパティの値を使用してこのマッピングを行います。 すべての SMS および MMS メッセージには、このプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メール アドレスが入力されます。
 
   *ユーザーの電子メール アドレス* プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義することもできます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号と対応する Microsoft 365 メール アドレスが含まれています。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを参照します。 携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタはインポートしようとしているアイテムのメール アドレス プロパティの値を使用します。 コネクタがカスタム マッピング ファイルまたは電子メール アイテムのメール アドレス プロパティで有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

AT&T Network データをアーカイブするために必要な実装手順の一部は Microsoft 365 の外部にあり、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage からモバイル アーカイバー サービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)を注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成するときは、このアカウントにサインインする必要があります。

- AT&T アカウントと課金連絡先の詳細を取得して、TeleMessage オンボード フォームに入力し、AT&T からメッセージ アーカイブ サービスを注文できるようにします。

- AT&T SMS/MMS Network アーカイブを必要とするすべてのユーザーを TeleMessage アカウントに登録します。 ユーザーを登録するときは、Microsoft 365 アカウントで使用されているのと同じメール アドレスを使用してください。

- 従業員は、AT&T モバイル ネットワークに会社所有の携帯電話と会社責任のある携帯電話を持っている必要があります。 Microsoft 365 のメッセージのアーカイブは、従業員所有のデバイスまたは "Bring Your Own Devices (BYOD) デバイスでは使用できません。

- AT&T Network コネクタを作成するユーザーには、Data Connector 管理 ロールが割り当てられている必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

- この TeleMessage データ コネクタは、Microsoft 365 US Government クラウドの GCC 環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあり、Microsoft Purview およびデータ保護コミットメントの対象外であるサード パーティ システムに対する組織の顧客データの保存、送信、処理が含まれる場合があります。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続することは、これらのサードパーティ アプリケーションが FEDRAMP に準拠していることを意味することを示しません。

## <a name="create-a-att-network-connector"></a>AT&T ネットワーク コネクタを作成する

前のセクションで説明した前提条件を完了したら、コンプライアンス ポータルで AT&T Network コネクタを作成できます。 コネクタは、指定した情報を使用して TeleMessage サイトに接続し、SMS および MMS メッセージを Microsoft 365 の対応するユーザー メールボックス ボックスに転送します。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com/)[**データ コネクタ** \ **AT&T Network**] に移動してクリックします。

2. **AT&T Network 製品** の説明ページで、[**コネクタの追加**] をクリックします。

3. [利用規約] ページ **で** 、[ **同意** する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [手順 3] で、次のボックスに必要な情報を入力し、[ **次へ**] をクリックします。

   - **名：** TeleMessage ユーザー名。

   - **パスワード：** TeleMessage のパスワード。

5. コネクタが作成されたら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ **ユーザー マッピング** ] ページで、自動ユーザー マッピングを有効にします。 カスタム マッピングを有効にするには、ユーザー マッピング情報を含む CSV ファイルをアップロードし、[ **次へ**] をクリックします。

7. 設定を確認し、[ **完了]** をクリックしてコネクタを作成します。

8. コンプライアンス **センターの [****データ コネクタ**] ページの [コネクタ] タブに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日提供される予定です。
