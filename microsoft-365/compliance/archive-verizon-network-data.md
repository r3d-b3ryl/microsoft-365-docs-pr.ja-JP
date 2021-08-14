---
title: コネクタをセットアップして、Verizon Network データをアーカイブMicrosoft 365
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
description: 管理者は、TeleMessage コネクタをセットアップして、Sms および MMS データを Verizon Network からインポートおよびアーカイブMicrosoft 365。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: a484d8919c549bedf43bdf3895da5d0a7795f041f6514ac2720681894bfeabc4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53820656"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a>Verizon Network データをアーカイブするコネクタをセットアップする

Verizon Network からショート メッセージング サービス (SMS) およびマルチメディア メッセージング サービス (MMS) データをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センター の TeleMessage コネクタを使用します。 コネクタをセットアップして構成した後、毎日 1 回、組織の Verizon Network に接続し、SMS および MMS データを Microsoft 365 のメールボックスにインポートします。

Verizon Network コネクタ データをユーザー メールボックスに格納した後、訴訟ホールド、コンテンツ検索、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Verizon データに適用できます。 たとえば、コンテンツ検索を使用して Verizon SMS メッセージと MMS メッセージを検索したり、Verizon Network データを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 Verizon Network コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="overview-of-archiving-verizon-network-data"></a>Verizon Network データのアーカイブの概要

次の概要では、コネクタを使用して Verizon Network データをアーカイブするプロセスについて説明Microsoft 365。

![Verizon ネットワークのアーカイブ ワークフロー](../media/VerizonNetworkConnectorWorkflow.png)

1. 組織は、TeleMessage と Verizon を使用して Verizon ネットワーク コネクタをセットアップします。 詳細については [、「Verizon Network Archiver」を参照してください](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/)。

2. 24 時間に 1 回、組織の Verizon Network からの SMS メッセージと MMS メッセージが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンス センター で作成した Verizon ネットワーク コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の SMS メッセージと MMS メッセージを Microsoft クラウドの安全な Azure Storage 場所に転送します。 また、コネクタは SMS メッセージと MMS メッセージのコンテンツを電子メール メッセージ形式に変換します。

4. コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。 **Verizon SMS/MMS Network Archiver** という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、User の [電子メール アドレス] プロパティの値を使用して *、このマッピングを実行* します。 すべての SMS メッセージと MMS メッセージには、このプロパティが含まれるので、メッセージのすべての参加者の電子メール アドレスが設定されます。

   *User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを実装できます。 このマッピング ファイルには、組織内のユーザーの携帯電話番号Microsoft 365対応するメール アドレスが含まれる。 自動ユーザー マッピングとカスタム マッピングの両方を有効にした場合、すべての Verizon アイテムに対して、コネクタは最初にカスタム マッピング ファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタはインポートしようとしているアイテムの電子メール アドレス プロパティの値を使用します。 コネクタがカスタム マッピング ファイルまたは Verizon アイテムの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

Verizon Network データのアーカイブに必要な実装手順の一部は、Microsoft 365 の外部であり、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [TeleMessage から Verizon Network Archiver サービス](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)を注文し、組織の有効な管理アカウントを取得します。 コンプライアンス センターでコネクタを作成する場合は、このアカウントにサインインする必要があります。

- Verizon Network アカウントと請求連絡先の詳細を取得して、TeleMessage オンボーディング フォームに入力し、Verizon からメッセージ アーカイブ サービスを注文できます。

- TeleMessage アカウントに Verizon SMS と MMS アーカイブが必要なすべてのユーザーを登録します。 ユーザーを登録する場合は、ユーザーのアカウントに使用するメール アドレスと同じMicrosoft 365してください。

- 従業員は、Verizon モバイル ネットワーク上に企業所有および企業責任の携帯電話を持っている必要があります。 ユーザーが所有Microsoft 365デバイスまたは自分のデバイスを持ち込む (BYOD) デバイスでは、アーカイブ メッセージを使用できません。

- Verizon Network コネクタを作成するユーザーには、ユーザーにメールボックスインポートエクスポートの役割が割り当てられている必要Exchange Online。 これは、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

- このデータ コネクタは、米国政府機関GCCのMicrosoft 365環境で使用できます。 サード パーティのアプリケーションとサービスには、Microsoft 365 インフラストラクチャの外部にあるサードパーティ システムに組織の顧客データを格納、送信、処理する必要がある場合があります。したがって、Microsoft 365 コンプライアンスとデータ保護のコミットメントの対象とはなってはいけなかっています。 Microsoft は、この製品を使用してサード パーティ製アプリケーションに接続する場合、これらのサード パーティ製アプリケーションが FEDRAMP に準拠しているという意味を示していません。

## <a name="create-a-verizon-network-connector"></a>Verizon ネットワーク コネクタの作成

前のセクションで説明した前提条件を完了したら、次のセクションで Verizon Network コネクタを作成Microsoft 365 コンプライアンス センター。 コネクタは、指定した情報を使用して TeleMessage サイトに接続し、SMS メッセージと MMS メッセージを、メッセージ内の対応するユーザー メールボックス ボックスに転送Microsoft 365。

1. に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com) 、[データ コネクタ  >  **Verizon Network] をクリックします**。

2. **[Verizon Network 製品の説明] ページ** で、[コネクタの追加]**をクリックします。**

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