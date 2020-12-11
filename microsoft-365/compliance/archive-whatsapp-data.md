---
title: Microsoft 365 で WhatsApp データをアーカイブするコネクタを設定する
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
description: 管理者は、Microsoft 365 で WhatsApp データをインポートおよびアーカイブする TeleMessage コネクタを設定できます。 これにより、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 573316f262295cce417876ef77510da14b877c67
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620183"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>WhatsApp データをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターの TeleMessage コネクタを使用して、WhatsApp の呼び出し、チャット、添付ファイル、ファイル、削除されたメッセージをインポートおよびアーカイブします。 コネクタをセットアップして構成した後、組織の TeleMessage アカウントに毎日 1 回接続し、TeleMessage WhatsApp Phone Archiver または TeleMessage WhatsApp Cloud Archiver を使用して従業員のモバイル通信を Microsoft 365 のメールボックスにインポートします。

WhatsApp データがユーザー メールボックスに保存された後、訴訟ホールド、コンテンツ検索、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を WhatsApp データに適用できます。 たとえば、コンテンツ検索を使用して WhatsApp メッセージを検索したり、WhatsApp メッセージを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 WhatsApp コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-whatsapp-data"></a>WhatsApp データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の WhatsApp データをアーカイブするプロセスについて説明します。

![WhatsApp アーカイブ ワークフロー](../media/WhatsAppConnectorWorkflow.png)

1. 組織は TeleMessage と一緒に WhatsApp Archiver コネクタをセットアップします。 詳細については [、WhatsApp Archiver を参照してください](https://www.telemessage.com/office365-activation-for-whatsapp-archiver)。

2. 24 時間ごとに、組織の WhatsApp データが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センターで作成する WhatsApp コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の WhatsApp データを Microsoft Cloud のセキュリティで保護された Azure Storage の場所に転送します。 コネクタは、コンテンツ WhatsApp データを電子メール メッセージ形式に変換します。

4. コネクタは、WhatsApp データを特定のユーザーのメールボックスにインポートします。 **WhatsApp Archiver という名前の新** しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、ユーザーの電子メール アドレス プロパティの値を使用して *、このマッピングを行* います。 すべての WhatsApp メッセージには、このプロパティが含まれるので、メッセージのすべての参加者の電子メール アドレスが設定されます。

   ユーザーの電子メール アドレス プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを実装できます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号と対応する Microsoft 365 電子メール アドレスが含まれている。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、各 WhatsApp アイテムについて、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタはインポートしようとしているアイテムの電子メール アドレス プロパティの値を使用します。 コネクタがカスタム マッピング ファイルまたは WhatsApp アイテムの電子メール アドレス プロパティのどちらかに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

WhatsApp 通信データをアーカイブするために必要な実装手順のいくつかは、Microsoft 365 の外部にあるので、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から WhatsApp Archiver サービスを](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- TeleMessage アカウントに WhatsApp アーカイブを必要とするユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントと同じメール アドレスを使用してください。

- 従業員の携帯電話に TeleMessage [WhatsApp Phone Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) アプリをインストールし、アクティブ化します。 または、従業員の携帯電話に通常の WhatsApp または WhatsApp Business アプリをインストールし、TeleMessage Web サイトの QR コードをスキャンして WhatsApp Cloud Archiver サービスをアクティブ化することもできます。 詳細については [、「WhatsApp Cloud Archiver」を参照してください](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)。

- Verizon Network コネクタを作成するユーザーには、Exchange Online の Mailbox Import Export 役割が割り当てられている必要があります。 これは、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="create-a-whatsapp-archiver-connector"></a>WhatsApp Archiver コネクタを作成する

前のセクションで説明した前提条件が完了したら、Microsoft 365 コンプライアンス センターで WhatsApp コネクタを作成できます。 このコネクタは、指定した情報を使用して TeleMessage サイトに接続し、WhatsApp データを Microsoft 365 の対応するユーザー メールボックス ボックスに転送します。

1. データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/)   >  **WhatsApp Archiver に移動してクリックします**。

2. **WhatsApp Archiver 製品の説明** ページで、[コネクタの追加]**をクリックします。**

3. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

4. **[TeleMessage へのログイン**] ページの手順 3 で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にし、[次へ] を **クリックします**。 カスタム マッピングで CSV ファイルをアップロードする必要がある場合は、[次へ] をクリック **します**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. [データ コネクタ] ページの [コネクタ] タブに **移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。 より大きなアイテムのサポートは、後日利用可能になります。
