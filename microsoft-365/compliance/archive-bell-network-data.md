---
title: ベル SMS/MMS ネットワーク データをアーカイブするコネクタをセットアップする
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
description: 管理者は TeleMessage コネクタをセットアップして、ベルベル ネットワークから SMS および MMS データをインポートおよびアーカイブできます。 これにより、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: d615488e5f6441efd828a6b91c187e7a8f5ca2c8
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620478"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>ベルベル ネットワーク のデータをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの TeleMessage コネクタを使用して、Short Messaging Service (SMS) メッセージとマルチメディア メッセージング サービス (MMS) メッセージをベル ネットワークからインポートおよびアーカイブします。 コネクタをセットアップして構成した後、毎日 1 回、組織のベルベル ネットワークに接続し、SMS メッセージと MMS メッセージを Microsoft 365 のメールボックスにインポートします。

SMS および MMS メッセージがユーザー メールボックスに保存された後、訴訟ホールド、コンテンツ検索、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を、ベルベル ネットワーク データに適用できます。 たとえば、コンテンツ検索を使用してベルベル ネットワーク SMS/MMS を検索したり、ベルベル ネットワーク コネクタ データを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 ベル ネットワーク コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-bell-network-data"></a>ベルベル ネットワーク データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 でベルベル ネットワークのデータをアーカイブするプロセスについて説明します。

![ベル ネットワーク アーカイブ ワークフロー](../media/BellNetworkConnectorWorkflow.png)

1. 組織は TeleMessage およびベルと一緒に、ベル ネットワーク コネクタをセットアップします。 詳しくは、「ベルベル [ネットワーク アーカイブ」をご覧ください](https://www.telemessage.com/office365-activation-for-bell-network-archiver)。

2. 24 時間に 1 回、組織のベルネットワークからの SMS メッセージと MMS メッセージが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センターで作成するベル ネットワーク コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の SMS メッセージと MMS メッセージを Microsoft Cloud のセキュリティで保護された Azure Storage の場所に転送します。 コネクタは、SMS メッセージと MMS メッセージのコンテンツを電子メール メッセージ形式に変換します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 特定のユーザーのメールボックス **に、"ベルの SMS/MMS ネットワーク** アーカイブ" という名前の新しいフォルダーが作成され、アイテムがインポートされます。 コネクタは、ユーザーの電子メール アドレス プロパティの値を使用して *、このマッピングを行* います。 すべての SMS および MMS メッセージには、このプロパティが含まれるので、メッセージのすべての参加者の電子メール アドレスが設定されます。

   ユーザーの電子メール アドレス プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号と対応する Microsoft 365 電子メール アドレスが含まれている。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、すべてのベルネットワーク項目について、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタはインポートしようとしているアイテムの電子メール アドレス プロパティの値を使用します。 コネクタがカスタム マッピング ファイルまたはベルベル ネットワーク アイテムの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

ベルベル ネットワークのデータをアーカイブするために必要な実装手順の一部は Microsoft 365 の外部にあるので、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage からベルネットワーク アーカイブ サービスを](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- TeleMessage オンボード フォームに入力し、メッセージ アーカイブ サービスをベルから注文できるよう、ベルベル ネットワーク アカウントと請求連絡先の詳細を取得します。

- TeleMessage アカウントに、ベル SMS/MMS ネットワーク アーカイブが必要なすべてのユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントと同じメール アドレスを使用してください。

- 従業員は、会社が所有し、会社が責任を持つ携帯電話をベルのモバイル ネットワーク上に持っている必要があります。 Microsoft 365 のアーカイブ メッセージは、従業員が所有するデバイスや "Bring Your Own Devices (BYOD) デバイスでは使用できません。

- ベル ネットワーク コネクタを作成するユーザーには、Exchange Online の "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割が割り当てられている必要があります。 これは、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="create-a-bell-network-connector"></a>ベル ネットワーク コネクタを作成する

最後の手順では、Microsoft 365 コンプライアンス センターでベルベル ネットワーク コネクタを作成します。 このコネクタは、指定した情報を使用して TeleMessage サイトに接続し、SMS/MMS メッセージを Microsoft 365 の対応するユーザー メールボックス ボックスに転送します。

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click Data **connectors**  >  **Bell SMS/MMS Network Archiver**.

2. ベル ネットワーク **製品の説明ページ** で、[コネクタの追加] **をクリックします。**

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. **[TeleMessage へのログイン**] ページの手順 3 で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にする。 カスタム マッピングを有効にするには、ユーザー マッピング情報を含む CSV ファイルをアップロードし、[次へ] をクリック **します**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. コンプライアンス センターの **[データ** コネクタ] ページの [コネクタ] タブに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
