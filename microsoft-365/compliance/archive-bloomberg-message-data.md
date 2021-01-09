---
title: Bloomberg メッセージ データをアーカイブするコネクタを設定する
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
description: 管理者は、データ コネクタをセットアップして、Bloomberg メッセージ 電子メール ツールから Microsoft 365 にデータをインポートおよびアーカイブできます。 これにより、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: f9b082dace9301f5a664078e9028c646ffa28483
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790117"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Bloomberg メッセージ データをアーカイブするコネクタを設定する

Microsoft 365 コンプライアンス センターのデータ コネクタを使用して [、Bloomberg Message](https://www.bloomberg.com/professional/product/collaboration/) コラボレーション ツールから金融サービスの電子メール データをインポートしてアーカイブします。 コネクタをセットアップして構成すると、毎日 1 回、組織の Bloomberg セキュア FTP (SFTP) サイトに接続し、Microsoft 365 のメールボックスに電子メール アイテムをインポートします。

Bloomberg メッセージ データがユーザー メールボックスに保存された後、訴訟ホールド、コンテンツ検索、インサイト アーカイブ、監査、通信コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を Bloomberg メッセージ データに適用できます。 たとえば、コンテンツ検索ツールを使用して Bloomberg メッセージのメールを検索したり、Bloomberg メッセージ データを含むメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 Bloomberg メッセージ コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="overview-of-archiving-bloomberg-message-data"></a>Bloomberg メッセージ データのアーカイブの概要

次の概要では、コネクタを使用して、Microsoft 365 の Bloomberg メッセージ データをアーカイブするプロセスについて説明します。

![Bloomberg メッセージのインポートとアーカイブのプロセス](../media/BloombergMessageArchiving.png)

1. 組織は Bloomberg と共同で Bloomberg SFTP サイトをセットアップします。 また、Bloomberg と共同で、電子メール メッセージを Bloomberg SFTP サイトにコピーする Bloomberg Message を構成します。

2. 24 時間ごとに、Bloomberg メッセージからの電子メール メッセージが Bloomberg SFTP サイトにコピーされます。

3. Microsoft 365 コンプライアンス センターで作成する Bloomberg メッセージ コネクタは、毎日 Bloomberg SFTP サイトに接続し、過去 24 時間の電子メール メッセージを Microsoft Cloud のセキュリティで保護された Azure Storage 領域に転送します。

4. コネクタは、電子メール メッセージ アイテムを特定のユーザーのメールボックスにインポートします。 BloombergMessage という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 

   コネクタは、CorporateEmailAddress プロパティの値を使用してこれを行います。 すべての電子メール メッセージには、このプロパティが含まれるので、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。 *CorporateEmailAddress* プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。 このマッピング ファイルには、組織内の各ユーザーの Bloomberg UUID と対応する Microsoft 365 メールボックス アドレスが含まれている。 自動ユーザー マッピングを有効にし、カスタム マッピングを提供する場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを確認します。 ユーザーの Bloomberg UUID に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタは電子メール アイテムの *CorporateEmailAddress* プロパティを使用します。 コネクタがメール アイテムのカスタム マッピング ファイルまたは *CorporateEmailAddress* プロパティのどちらかに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

Bloomberg メッセージ データをアーカイブするために必要な実装手順の一部は Microsoft 365 の外部にあるので、コンプライアンス センターでコネクタを作成する前に完了する必要があります。

- [Bloomberg Anywhere にサブスクライブします](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)。 これは、設定と構成が必要な Bloomberg SFTP サイトにアクセスするために、Bloomberg Anywhere にログインするために必要です。

- Bloomberg SFTP (セキュア ファイル転送プロトコル) サイトをセットアップします。 Bloomberg と共同で SFTP サイトをセットアップした後、Bloomberg Message からのデータは毎日 SFTP サイトにアップロードされます。 手順 2 で作成したコネクタは、この SFTP サイトに接続し、電子メール データを Microsoft 365 メールボックスに転送します。 SFTP は、転送プロセス中にメールボックスに送信される Bloomberg メッセージ データも暗号化します。

  Bloomberg SFTP *(BB-SFTP* とも呼ばれる) の詳細については、次の情報を参照してください。

  - Bloomberg サポートの「SFTP Connectivity Standards」ドキュメント [を参照してください](https://www.bloomberg.com/professional/support/documentation/)。

  - [Bloomberg カスタマー サポートにお問い合わせください](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)。

   > [!NOTE]
   > Instant Bloomberg データをアーカイブするコネクタが組織で既に展開されている場合は、別の SFTP サイトをセットアップする必要があります。 Bloomberg メッセージ コネクタには同じ SFTP サイトを使用できます。

- Bloomberg と共同で SFTP サイトをセットアップすると、Bloomberg 実装の電子メール メッセージに応答した後、Bloomberg から情報が提供されます。 次の情報のコピーを保存します。 手順 3 でコネクタをセットアップするために使用します。

  - 会社コード。組織の ID であり、Bloomberg SFTP サイトへのログインに使用されます。

  - Bloomberg SFTP サイトのパスワード

  - Bloomberg SFTP サイトの URL (例: sftp.bloomberg.com)。 また、Bloomberg は、コネクタのセットアップにも使用できる、Bloomberg SFTP サイトの対応する IP アドレスを提供する場合もあります。

  - Bloomberg SFTP サイトのポート番号

- Bloomberg メッセージ コネクタは、1 日に合計 200,000 アイテムをインポートできます。 SFTP サイトに 200,000 を超えるアイテムがある場合、それらのアイテムは Microsoft 365 にインポートされません。

- 手順 3 で Bloomberg メッセージ コネクタを作成するユーザー (および手順 1 で公開キーと IP アドレスをダウンロードするユーザー) には、Exchange Online の Mailbox Import Export 役割が割り当てられている必要があります。 これは、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>手順 1: SSH および PGP 公開キーを取得する

最初の手順では、セキュア シェル (SSH) と Pretty Good Privacy (PGP) の公開キーのコピーを取得します。 手順 2 でこれらのキーを使用して、(手順 3 で作成した) コネクタが SFTP サイトに接続し、Bloomberg メッセージの電子メール データを Microsoft 365 メールボックスに転送することを許可するために、Bloomberg SFTP サイトを構成します。 この手順では、Bloomberg SFTP サイトを構成するときに使用する IP アドレスも取得します。

1. []( に https://compliance.microsoft.com\ 移動 https://compliance.microsoft.com) し、左側のナビゲーションで **[** データ コネクタ] をクリックします。

2. [データ **コネクタ] ページの** **[Bloomberg** メッセージ] で、[表示] を **クリックします**。

3. **Bloomberg メッセージ製品の** 説明ページで、[コネクタの追加]**をクリックします。**

4. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

5. 手順 1 の下にある **Bloomberg SFTP** サイトの資格情報の追加で **、SSH** キーのダウンロード **、PGP** キーのダウンロード **、IP** アドレス のダウンロードリンクをクリックして、各ファイルのコピーをローカル コンピューターに保存します。 これらのファイルには、手順 2 で Bloomberg SFTP サイトを構成するために使用される次の項目が含まれています。

   - SSH 公開キー: このキーは、コネクタが Bloomberg SFTP サイトに接続するときにセキュリティで保護されたリモート ログインを有効にするためのセキュア シェル (SSH) を構成するために使用されます。

   - PGP 公開キー: このキーは、Bloomberg SFTP サイトから Microsoft 365 に転送されるデータの暗号化を構成するために使用されます。

   - IP アドレス: Bloomberg SFTP サイトは、この IP アドレスからの接続要求のみを受け付けするように構成されています。この IP アドレスは、手順 3 で作成した Bloomberg メッセージ コネクタによって使用されます。

6. [ **キャンセル] を** クリックしてウィザードを閉じます。 コネクタを作成するには、手順 3 でこのウィザードに戻ります。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>手順 2: Bloomberg SFTP サイトを構成する

> [!NOTE]
> 前に説明したように、組織が以前に Bloomberg SFTP サイトをセットアップして Instant Bloomberg データをアーカイブしている場合は、別のサイトをセットアップする必要がなされます。 手順 3 でコネクタを作成するときに、同じ SFTP サイトを指定できます。

次の手順では、SSH と PGP の公開キーと、手順 1 で取得した IP アドレスを使用して、Bloomberg SFTP サイトの SSH 認証と PGP 暗号化を構成します。 これにより、手順 3 で作成した Bloomberg メッセージ コネクタが Bloomberg SFTP サイトに接続し、Bloomberg メッセージ データを Microsoft 365 に転送できます。 Bloomberg SFTP サイトをセットアップするには、Bloomberg カスタマー サポートと一緒に作業する必要があります。 [Bloomberg カスタマー サポートにお問い](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)合わせください。

> [!IMPORTANT]
> Bloomberg は、手順 1 でダウンロードした 3 つのファイルを電子メール メッセージに添付し、Bloomberg SFTP サイトをセットアップする際に顧客サポート チームに送信することを推奨します。

## <a name="step-3-create-a-bloomberg-message-connector"></a>手順 3: Bloomberg メッセージ コネクタを作成する

最後の手順では、Microsoft 365 コンプライアンス センターで Bloomberg メッセージ コネクタを作成します。 コネクタは、入力した情報を使用して Bloomberg SFTP サイトに接続し、Microsoft 365 の対応するユーザー メールボックス ボックスに電子メール メッセージを転送します。

1. 左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。

2. [データ **コネクタ] ページの** **[Bloomberg** メッセージ] で、[表示] を **クリックします**。

3. **Bloomberg メッセージ製品の** 説明ページで、[コネクタの追加]**をクリックします。**

4. [サービス条件 **] ページで、[** 承諾] を **クリックします**。

5. **[Bloomberg SFTP** サイトの資格情報の追加] ページの手順 3 で、次のボックスに必要な情報を入力し、[次へ] をクリック **します**。

      - **会社コード:** Bloomberg SFTP サイトのユーザー名として使用される組織の ID。

      - **パスワード:** 組織の Bloomberg SFTP サイトのパスワード。

      - **SFTP URL:** Bloomberg SFTP サイトの URL (例: sftp.bloomberg.com)。

      - **SFTP ポート:** Bloomberg SFTP サイトのポート番号。 コネクタはこのポートを使用して SFTP サイトに接続します。

6. [ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にし、必要に応じてカスタム ユーザー マッピングを提供します。

7. [ **次へ]** をクリックし、設定を確認し、[準備] をクリックしてコネクタを作成します。

8. [データ コネクタ **] ページに移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- Microsoft 365 にインポートされた Bloomberg メッセージメールのスレッドはサポートされていません。 個人に送信された個々のメッセージはインポートされますが、スレッド化された会話では表示されません。 Microsoft は、Bloomberg メッセージ データ コネクタの新しいバージョンでスレッド化をサポートする取り組みです。
