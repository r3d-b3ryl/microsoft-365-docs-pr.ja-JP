---
title: ICE Chat データをアーカイブするコネクタを設定する
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
description: 管理者は、ICE チャット ツールから Microsoft 365 にデータをインポートおよびアーカイブするコネクタを設定できます。 これにより、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 79a18017ce7aa3c646fa6c7230bde4b001ddc4c8
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790171"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>ICE Chat データをアーカイブするコネクタを設定する

MICROSOFT 365 コンプライアンス センターのネイティブ コネクタを使用して、ICE Chat コラボレーション ツールから金融サービス のチャット データをインポートおよびアーカイブします。 コネクタをセットアップして構成した後、組織の ICE Chat セキュア FTP (SFTP) サイトに毎日 1 回接続し、チャット メッセージのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

ICE チャット データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アーカイブ、監査、通信コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を ICE Chat データに適用できます。 たとえば、コンテンツ検索を使用して ICE Chat メッセージを検索したり、ICE チャット データを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 ICE チャット コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-ice-chat-data"></a>ICE Chat データのアーカイブの概要

次の概要では、コネクタを使用して ICE チャット データを Microsoft 365 にアーカイブするプロセスについて説明します。

![ICE Chat archiving workflow](../media/ICEChatConnectorWorkflow.png)

1. 組織は ICE チャットと共同で ICE Chat SFTP サイトをセットアップします。 また、ICE Chat を使用して ICE Chat を構成し、チャット メッセージを ICE Chat SFTP サイトにコピーします。

2. 24 時間ごとに、ICE Chat からのチャット メッセージが ICE Chat SFTP サイトにコピーされます。

3. Microsoft 365 コンプライアンス センターで作成する ICE Chat コネクタは、毎日 ICE Chat SFTP サイトに接続し、過去 24 時間のチャット メッセージを Microsoft Cloud のセキュリティで保護された Azure Storage の場所に転送します。 コネクタは、チャットチャットの内容を電子メール メッセージ形式に変換します。

4. コネクタは、チャット メッセージ アイテムを特定のユーザーのメールボックスにインポートします。 ICE Chat という名前 **の新しい** フォルダーがユーザー メールボックスに作成され、チャット メッセージ アイテムがフォルダーにインポートされます。 コネクタは *、SenderEmail* プロパティと RecipientEmail プロパティの *値を使用して行* います。 すべてのチャット メッセージには、これらのプロパティが含まれるので、送信者の電子メール アドレスとチャット メッセージのすべての受信者/参加者が設定されます。

   *SenderEmail* プロパティと *RecipientEmail* プロパティの値を使用する自動ユーザー マッピング (つまり、コネクタが送信者のメールボックスとすべての受信者のメールボックスにチャット メッセージをインポートする) に加えて、CSV マッピング ファイルをアップロードしてカスタム ユーザー マッピングを定義することもできます。 このマッピング ファイルには、ICE Chat *ImId* と、組織内のすべてのユーザーの対応する Microsoft 365 メールボックス アドレスが含まれている。 自動ユーザー マッピングを有効にしてカスタム マッピング ファイルを提供する場合、すべてのチャット アイテムについて、コネクタは最初にカスタム マッピング ファイルを確認します。 ユーザーの ICE Chat ImId に対応する有効な Microsoft 365 ユーザー アカウントが見つからなかった場合、コネクタはチャット アイテムの *SenderEmail* プロパティと *RecipientEmail* プロパティを使用して、チャット参加者のメールボックスにアイテムをインポートします。 コネクタがカスタム マッピング ファイルまたは *SenderEmail* プロパティと *RecipientEmail* プロパティのどちらかに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

ICE Chat データをアーカイブするために必要な実装手順の一部は Microsoft 365 の外部にあるので、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- ICE チャットは、顧客に対して外部コンプライアンスの手数料を請求します。 組織は ICE Chat 営業グループに連絡して話し合い、ICE Chat データ サービス契約に署名する [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) 必要があります。 この契約は ICE Chat と組織の間で締結され、Microsoft は関与しないものとします。 手順 2 で ICE Chat SFTP サイトをセットアップすると、ICE Chat は FTP 資格情報を直接組織に提供します。 次に、手順 3 でコネクタを設定するときに、これらの資格情報を Microsoft に提供するユーザー。

- 手順 3 でコネクタを作成する前に、ICE Chat SFTP サイトをセットアップする必要があります。 ICE チャットを使用して SFTP サイトをセットアップした後、ICE チャットからのデータは毎日 SFTP サイトにアップロードされます。 手順 3 で作成したコネクタは、この SFTP サイトに接続し、チャット データを Microsoft 365 メールボックスに転送します。 SFTP は、転送プロセス中にメールボックスに送信される ICE チャット データも暗号化します。

- ICE Chat コネクタは、1 日に合計 200,000 アイテムをインポートできます。 SFTP サイトに 200,000 を超えるアイテムがある場合、それらのアイテムは Microsoft 365 にインポートされません。

- 手順 3 で ICE Chat コネクタを作成する管理者 (および手順 1 で公開キーと IP アドレスをダウンロードする管理者) には、Exchange Online の Mailbox Import Export 役割が割り当てられている必要があります。 この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>手順 1: SSH および PGP 公開キーを取得する

最初の手順では、セキュア シェル (SSH) と Pretty Good Privacy (PGP) の公開キーのコピーを取得します。 手順 2 でこれらのキーを使用して、ICE Chat SFTP サイトを構成して、コネクタ (手順 3 で作成) が SFTP サイトに接続し、ICE Chat データを Microsoft 365 メールボックスに転送することを許可します。 この手順では、ICE Chat SFTP サイトを構成するときに使用する IP アドレスも取得します。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [データ コネクタ **] ページの** **[ICE チャット**] で、[表示] を **クリックします**。

3. **[ICE チャット] ページで**、[コネクタの追加]**をクリックします**。

4. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

5. 手順 1 の下の **[ICE Chat SFTP** サイトの資格情報の追加] ページで **、SSH** キーのダウンロード **、PGP** キーのダウンロード **、IP** アドレス のダウンロードリンクをクリックして、各ファイルのコピーをローカル コンピューターに保存します。 これらのファイルには、手順 2 で ICE Chat SFTP サイトを構成するために使用される次の項目が含まれています。

   - SSH 公開キー: このキーは、コネクタが ICE Chat SFTP サイトに接続するときにセキュリティで保護されたリモート ログインを有効にするための Secure SSH を構成するために使用されます。

   - PGP 公開キー: このキーは、ICE Chat SFTP サイトから Microsoft 365 に転送されるデータの暗号化を構成するために使用されます。

   - IP アドレス: ICE Chat SFTP サイトは、この IP アドレスからの接続要求のみを受け付けするように構成されています。この IP アドレスは、手順 3 で作成した ICE Chat コネクタによって使用されます。

6. [ **キャンセル] を** クリックしてウィザードを閉じます。 手順 3 でこのウィザードに戻り、コネクタを作成します。

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>手順 2: ICE Chat SFTP サイトを構成する

次の手順では、SSH および PGP 公開キーと、手順 1 で取得した IP アドレスを使用して、ICE Chat SFTP サイトの SSH 認証と PGP 暗号化を構成します。 これにより、手順 3 で作成した ICE Chat コネクタは ICE Chat SFTP サイトに接続し、ICE Chat データを Microsoft 365 に転送できます。 ICE Chat SFTP サイトをセットアップするには、ICE Chat カスタマー サポートと一緒に作業する必要があります。

## <a name="step-3-create-an-ice-chat-connector"></a>手順 3: ICE チャット コネクタを作成する

最後の手順では、Microsoft 365 コンプライアンス センターで ICE Chat コネクタを作成します。 コネクタは、入力した情報を使用して ICE Chat SFTP サイトに接続し、Microsoft 365 の対応するユーザー メールボックス ボックスにチャット メッセージを転送します。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [データ コネクタ **] ページの** **[ICE チャット**] で、[表示] を **クリックします**。

3. **[ICE チャット] ページで**、[コネクタの追加]**をクリックします**。

4. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

5. **[ICE Chat SFTP** サイトの資格情報の追加] ページの手順 3 で、次のボックスに必要な情報を入力し、[接続の検証] を **クリックします**。

   - **会社コード:** ICE Chat SFTP サイトのユーザー名として使用される組織の ID。

   - **パスワード:** ICE Chat SFTP サイトのパスワード。

   - **SFTP URL:** ICE Chat SFTP サイトの URL (例: sftp.theice.com)。

   - **SFTP ポート:** ICE Chat SFTP サイトのポート番号。 コネクタはこのポートを使用して SFTP サイトに接続します。

6. 接続が検証された後、[次へ] を **クリックします**。

7. [外部ユーザー **を Microsoft 365** ユーザーにマップする] ページで、自動ユーザー マッピングを有効にし、必要に応じてカスタム ユーザー マッピングを提供します。 このページでは、ユーザー マッピング CSV ファイルのコピーをダウンロードできます。 ユーザー マッピングをファイルに追加し、アップロードできます。

   > [!NOTE]
   > 前に説明したように、カスタム マッピング ファイル CSV ファイルには、各ユーザーの ICE Chat imid と対応する Microsoft 365 メールボックス アドレスが含まれている必要があります。 自動ユーザー マッピングを有効にし、カスタム マッピングを提供する場合、すべてのチャット アイテムに対して、コネクタは最初にカスタム マッピング ファイルを確認します。 ユーザーの ICE Chat imid に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタは、チャット アイテムの *SenderEmail* プロパティと *RecipientEmail* プロパティで指定されたユーザーのメールボックスにアイテムをインポートします。 コネクタが自動ユーザー マッピングまたはカスタム ユーザー マッピングによって有効な Microsoft 365 ユーザーを検出しない場合、アイテムはインポートされません。

8. [ **次へ]** をクリックし、設定を確認し、[完了] **をクリックして** コネクタを作成します。

9. [データ コネクタ **] ページに移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。
