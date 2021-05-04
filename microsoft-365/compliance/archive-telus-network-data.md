---
title: コネクタをセットアップして、TELUS Network データをアーカイブMicrosoft 365
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
description: 管理者は、テレメッセージ コネクタをセットアップして、携帯ショートメールの TELUS ネットワークからデータをインポートおよびアーカイブMicrosoft 365。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 13ac3306d2541f5bc7393152abb6cefb5a11123e
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077351"
---
# <a name="set-up-a-connector-to-archive-telus-network-data"></a>TELUS ネットワーク データをアーカイブするコネクタをセットアップする

組織の TELUS ネットワークからショート メッセージング サービス (携帯ショートメール) データをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターの TeleMessage コネクタを使用します。 コネクタをセットアップして構成した後、毎日 1 回、組織の TELUS ネットワークに接続し、携帯ショートメール データを Microsoft 365 のメールボックスにインポートします。

メッセージ携帯ショートメールユーザー メールボックスに保存された後、訴訟ホールド、コンテンツ検索、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を TELUS データに適用できます。 たとえば、コンテンツ検索を使用して TELUS 携帯ショートメールメッセージを検索したり、TELUS データを含むメールボックスを管理者に関連付Advanced eDiscoveryできます。 TELUS ネットワーク コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-telus-network-data"></a>TELUS ネットワーク データのアーカイブの概要

次の概要では、コネクタを使用して TELUS Network データをアーカイブするプロセスについて説明Microsoft 365。

![TELUS ネットワークのアーカイブ ワークフロー](../media/TelusNetworkConnectorWorkflow.png)

1. 組織は、TeleMessage と TELUS を使用して TELUS ネットワーク コネクタをセットアップします。 詳細については [、「TELUS Network Archiver」を参照してください](https://www.telemessage.com/office365-activation-for-telus-network-archiver/)。

2. リアルタイムで、組織携帯ショートメール TELUS ネットワークからのメッセージが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センターで作成する TELUS ネットワーク コネクタは、毎日 TeleMessage サイトに接続し、携帯ショートメール メッセージを過去 24 時間から Microsoft クラウドの安全な Azure Storage 場所に転送します。 コネクタは、メッセージの内容を電子携帯ショートメール形式に変換します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 ネットワーク アーカイブ携帯ショートメール **TELUS** という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、そのメールボックスにアイテムがインポートされます。 コネクタは、User の [電子メール アドレス] プロパティの値を使用 *してマッピングを行* います。 すべての携帯ショートメールには、このプロパティが含まれるので、このプロパティには、メッセージのすべての参加者の電子メール アドレスが携帯ショートメールされます。

   *User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを実装できます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号Microsoft 365対応するメール アドレスが含まれる。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、すべての TELUS アイテムについて、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタはインポートしようとしているアイテムの電子メール アドレス プロパティの値を使用します。 コネクタがカスタム マッピング ファイルまたは TELUS アイテムの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>開始する前に

TELUS Network データのアーカイブに必要な実装手順の一部は、Microsoft 365 の外部であり、コンプライアンス センターにコネクタを作成する前に完了する必要があります。

- [TeleMessage から TELUS Network Archiver サービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成する場合は、このアカウントにサインインする必要があります。

- TELUS ネットワーク アカウントと請求連絡先の詳細を取得して、TeleMessage オンボーディング フォームに入力し、TELUS からメッセージ アーカイブ サービスを注文できます。

- TeleMessage アカウントで、TELUS 携帯ショートメール必要なすべてのユーザーを登録します。 ユーザーを登録する場合は、ユーザーのアカウントに使用するメール アドレスと同じMicrosoft 365してください。

- 従業員がTELUS モバイル ネットワーク上に企業所有および企業責任を持つ携帯電話を持っている必要があります。 ユーザーが所有Microsoft 365デバイスまたは自分のデバイスを持ち込む (BYOD) デバイスでは、アーカイブ メッセージを使用できません。

- TELUS ネットワーク コネクタを作成するユーザーには、メールボックス のインポート エクスポートの役割が割り当てられている必要Exchange Online。 これは、コンプライアンス センターの [データコネクタ] ページにコネクタを追加Microsoft 365必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="create-a-telus-network-connector"></a>TELUS ネットワーク コネクタの作成

前のセクションで説明した前提条件を完了したら、コンプライアンス センターで TELUS Network コネクタMicrosoft 365できます。 コネクタは、指定した情報を使用して、TeleMessage サイトに接続し、携帯ショートメール メッセージをユーザー の対応するユーザー メールボックス ボックスにMicrosoft 365。

1. [データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) TELUS ネットワーク] に移動し、[データ **コネクタ**  >  **] をクリックします**。

2. **[TELUS ネットワーク製品の説明]** ページで、[コネクタの追加]**をクリックします。**

3. [サービス条件 **] ページで、[** 同意する] を **クリックします**。

4. **[TeleMessage へのログイン]** ページの [手順 3] で、次のボックスに必要な情報を入力し、[次へ] を **クリックします**。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage パスワード。

5. コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にして、[次へ] を **クリックします**。 カスタム マッピングが必要な場合は、CSV ファイルをアップロードし、[次へ] を **クリックします**。

7. 設定を確認し、[完了] を **クリックして** コネクタを作成します。

8. [データ コネクタ] ページの [コネクタ] **タブに移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 大きいアイテムのサポートは、後日利用できます。
