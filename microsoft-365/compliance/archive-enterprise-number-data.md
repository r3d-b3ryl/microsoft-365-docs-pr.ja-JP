---
title: TeleMessage Enterprise Number Archiver からデータをアーカイブするコネクタを設定する
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
description: 管理者は、TeleMessage Enterprise Number Archiver から SMS および MMS データをインポートおよびアーカイブするコネクタを設定できます。 これにより、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 01c2807606449c576e292f8819a861b1193b4723
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620023"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>エンタープライズ番号データをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの TeleMessage コネクタを使用して、エンタープライズ番号アーカイブ ツールからショート メッセージング サービス (SMS) およびマルチメディア メッセージング サービス (MMS) メッセージ、チャット メッセージ、音声通話録音、および音声通話ログをインポートおよびアーカイブします。 コネクタをセットアップして構成した後、毎日 1 回、組織の TeleMessage アカウントに接続し、TeleMessage Enterprise Number Archiver を使用して従業員のモバイル通信データを Microsoft 365 のメールボックスにインポートします。

TeleMessage Enterprise Number Archiver コネクタ データがユーザー メールボックスに格納された後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、および Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能をエンタープライズ番号アーカイブ 機能に適用できます。 たとえば、コンテンツ検索を使用して TeleMessage Enterprise Number Archiver SMS、MMS、および Voice Call を検索したり、Enterprise Number Archiver コネクタ データを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 Enterprise Number Archiver コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-enterprise-number-data"></a>エンタープライズ番号データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 のエンタープライズ ネットワーク データをアーカイブするプロセスについて説明します。

![エンタープライズ番号のアーカイブ ワークフロー](../media/EnterpriseNumberConnectorWorkflow.png)

1. 組織は TeleMessage と一緒にエンタープライズ番号アーカイブ コネクタをセットアップします。 詳細については、こちらを参照 [してください](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/)。

2. Microsoft 365 コンプライアンス センターで作成する Enterprise Number Archiver コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の電子メール メッセージを Microsoft Cloud のセキュリティで保護された Azure Storage 領域に転送します。

3. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 特定のユーザーのメールボックスに Enterprise Number Archiver という名前の新しいフォルダーが作成され、アイテムがインポートされます。 コネクタは、ユーザーの電子メール アドレス プロパティの値 *を使用してマッピングを行* います。 すべての電子メール メッセージには、このプロパティが含まれるので、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。 ユーザーの電子メール アドレス プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、ユーザーのモバイル番号と、各ユーザーの対応する Microsoft 365 メールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にしてカスタム マッピングを提供する場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。 コネクタがメール アイテムのカスタム マッピング ファイルまたはユーザーの電子メール アドレス プロパティに有効なMicrosoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

Enterprise Number Archiver データをアーカイブするために必要な実装手順のいくつかは Microsoft 365 の外部にあるので、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から Enterprise Number Archiver サービスを](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- TeleMessage アカウントにエンタープライズ番号 SMS/MMS ネットワーク アーカイブが必要なすべてのユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントと同じメール アドレスを使用してください。

- 従業員の携帯電話に TeleMessage Enterprise Number Archiver アプリをインストールしてアクティブ化します。

- エンタープライズ番号アーカイブ コネクタを作成するユーザーには、Exchange Online の "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割が割り当てられている必要があります。 これは、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="create-an-enterprise-number-archiver-connector"></a>エンタープライズ番号アーカイブ コネクタを作成する

前のセクションで説明した前提条件を完了したら、Microsoft 365 コンプライアンス センターでエンタープライズ番号アーカイブ コネクタを作成できます。 このコネクタは、指定した情報を使用して TeleMessage サイトに接続し、SMS、MMS、および音声通話メッセージを Microsoft 365 の対応するユーザー メールボックス ボックスに転送します。

1. [データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタエンタープライズ番号アーカイブ ツール] に \> **移動し、[データ コネクタ] をクリックします**。

2. [エンタープライズ番号 **アーカイブツール製品の** 説明] ページで、[コネクタの追加] **をクリックします。**

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. **[TeleMessage へのログイン**] ページの手順 3 で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にする。 カスタム マッピングを有効にするには、ユーザー マッピング情報を含む CSV ファイルをアップロードし、[次へ] をクリック **します**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. [データ コネクタ] ページの [コネクタ] タブに **移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
