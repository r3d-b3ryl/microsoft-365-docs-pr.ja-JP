---
title: コネクタをセットアップしてインスタント ブルームバーグ データをアーカイブする
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がインスタント Bloomberg チャットツールから Microsoft 365 にデータをインポートしてアーカイブするためのデータコネクタをセットアップして使用する方法について説明します。
ms.openlocfilehash: 18635e6f197d954ae90c32bf5e3ae1ea8193f06d
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002362"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>コネクタをセットアップしてインスタント ブルームバーグ データをアーカイブする

Microsoft 365 コンプライアンスセンターのネイティブコネクタを使用して、 [インスタント Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) コラボレーションツールから金融サービスチャットデータをインポートおよびアーカイブします。 コネクタをセットアップして構成した後は、組織の Bloomberg secure FTP サイト (SFTP) に毎日接続して、チャットメッセージの内容を電子メールメッセージの形式に変換した後、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

ユーザーのメールボックスにインスタント Bloomberg データが格納された後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をインスタント Bloomberg データに適用することができます。 たとえば、コンテンツ検索を使用してインスタント Bloomberg チャットメッセージを検索したり、インスタント Bloomberg データを含むメールボックスを高度な電子情報開示ケースの保管担当者に関連付けることができます。 Microsoft 365 でインスタント Bloomberg コネクタを使用してデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-instant-bloomberg-data"></a>インスタント Bloomberg データのアーカイブの概要

次の概要では、コネクタを使用して、Microsoft 365 でインスタント Bloomberg チャットデータをアーカイブするプロセスについて説明します。 

![インスタント Bloomberg のインポートとアーカイブのプロセス](../media/InstantBloombergDataArchiving.png)

1. 組織は Bloomberg を使用して、Bloomberg SFTP サイトをセットアップします。 また、Bloomberg を使用して、チャットメッセージを Bloomberg SFTP サイトにコピーするようにインスタント Bloomberg を構成します。

2. 24時間ごとに、インスタント Bloomberg からのチャットメッセージが Bloomberg SFTP サイトにコピーされます。

3. Microsoft 365 コンプライアンスセンターで作成したインスタント Bloomberg コネクタは、毎日 Bloomberg SFTP サイトに接続して、過去24時間のチャットメッセージを Microsoft クラウドのセキュアな Azure ストレージ領域に転送します。 また、コネクタはチャットのメッセージの内容を電子メールメッセージの形式に変換します。

4. コネクタは、特定のユーザーのメールボックスにチャットメッセージアイテムをインポートします。 InstantBloomberg という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *CorporateEmailAddress* プロパティの値を使用してこれを実行します。 すべてのチャットメッセージには、このプロパティが含まれており、チャットメッセージのすべての参加者の電子メールアドレスが設定されます。 *CorporateEmailAddress* プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを定義することもできます。 このマッピングファイルには、各ユーザーの Bloomberg UUID および対応する Microsoft 365 メールボックスアドレスが含まれている必要があります。 自動ユーザーマッピングを有効にし、カスタムマッピングを指定すると、コネクタはまずカスタムマッピングファイルを参照します。 ユーザーの Bloomberg UUID に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタはチャットアイテムの *CorporateEmailAddress* プロパティを使用します。 コネクタが、カスタムマッピングファイルまたはチャットアイテムの *CorporateEmailAddress* プロパティに有効な Microsoft 365 ユーザーを見つけられない場合、そのアイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

インスタント Bloomberg データをアーカイブするために必要ないくつかの実装手順は、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に完了する必要があります。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、グローバル管理者の資格情報でサインインし、要求を承諾します。 手順3でインスタント Bloomberg コネクタを正常に作成するには、この手順を完了する必要があります。

- [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)にサブスクライブします。 これは、Bloomberg Anywhere にログインして、設定および構成する必要がある Bloomberg SFTP サイトにアクセスできるようにするために必要です。

- Bloomberg SFTP (Secure file transfer protocol) サイトをセットアップします。 Bloomberg を使用して SFTP サイトを設定した後は、インスタント Bloomberg のデータが毎日 SFTP サイトにアップロードされます。 手順2で作成したコネクタがこの SFTP サイトに接続し、チャットデータを Microsoft 365 メールボックスに転送します。 SFTP は、転送プロセス中にメールボックスに送信されるインスタント Bloomberg チャットデータも暗号化します。

  Bloomberg SFTP ( *BB* とも呼ばれます) の詳細については、以下を参照してください。

  - 「 [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/)」の「SFTP Connectivity 標準」ドキュメントを参照してください。

  - [Bloomberg カスタマーサポート](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)に問い合わせてください。

  Bloomberg を使用して SFTP サイトを設定した後、Bloomberg は Bloomberg 実装の電子メールメッセージに応答した後に情報を提供します。 次の情報のコピーを保存します。 これを使用して、手順3でコネクタを設定します。

  - 企業の ID であり、Bloomberg SFTP サイトにログインするために使用される、企業のコードです。

  - Bloomberg SFTP サイトのパスワード

  - Bloomberg SFTP サイトの URL (たとえば、sftp.bloomberg.com)

  - Bloomberg SFTP サイトのポート番号

- 手順3でインスタント Bloomberg コネクタを作成したユーザー (および手順1で公開キーと IP アドレスをダウンロードするユーザー) に、Exchange Online のメールボックスのインポートのエクスポート役割を割り当てる必要があります。 これは、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>手順 1: SSH と PGP の公開キーを取得する

最初の手順として、Secure Shell (SSH) およびかなり良好なプライバシー (PGP) のための公開キーのコピーを取得します。 手順2でこれらのキーを使用して、Bloomberg SFTP サイトを構成して、コネクタ (手順3で作成したもの) が SFTP サイトに接続し、インスタント Bloomberg チャットデータを Microsoft 365 メールボックスに転送できるようにします。 また、この手順では IP アドレスも取得します。これは、Bloomberg SFTP サイトを構成するときに使用します。

1. に移動 <https://compliance.microsoft.com> して、[ **データコネクタ**  >  **インスタント Bloomberg** ] をクリックします。

2. [ **インスタント Bloomberg** 製品の説明] ページで、[ **コネクタの追加** ] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。

4. [ **BLOOMBERG SFTP の資格情報の追加** ] の手順1で、 **[SSH キーのダウンロード** ]、[ **PGP キーのダウンロード** ]、および [ **IP アドレス** のダウンロード] リンクをクリックして、各ファイルのコピーをローカルコンピューターに保存します。 これらのファイルには、手順2で Bloomberg SFTP サイトを構成するために使用される次の項目が含まれています。

   - SSH 公開キー: このキーは、コネクタが Bloomberg SFTP サイトに接続する際にセキュリティで保護されたリモートログインを有効にするように Secure Shell (SSH) を構成するために使用されます。

   - PGP 公開キー: このキーは、Bloomberg SFTP サイトから Microsoft 365 に転送されるデータの暗号化を構成するために使用されます。

   - IP アドレス: Bloomberg SFTP サイトは、この IP アドレスからの接続要求のみを受け入れるように構成されています。これは、手順3で作成したインスタント Bloomberg コネクタによって使用されます。 

5. ウィザードを閉じるには、[ **キャンセル** ] をクリックします。 このウィザードに戻り、手順3でコネクタを作成します。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>手順 2: Bloomberg SFTP サイトを構成する

次の手順では、SSH と PGP の公開キーと、手順1で取得した IP アドレスを使用して、Bloomberg SFTP サイトの SSH 認証と PGP 暗号化を構成します。 これにより、手順3で作成したインスタント Bloomberg コネクタが Bloomberg SFTP サイトに接続し、インスタント Bloomberg データを Microsoft 365 に転送できるようになります。 Bloomberg SFTP サイトを設定するには、Bloomberg カスタマーサポートと連携する必要があります。 詳細については、 [Bloomberg カスタマーサポート](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) にお問い合わせください。 

> [!IMPORTANT]
> Bloomberg では、手順1でダウンロードした3つのファイルを電子メールメッセージに添付して、Bloomberg SFTP サイトを設定するために作業する際にカスタマーサポートチームに送信することをお勧めします。

## <a name="step-3-create-an-instant-bloomberg-connector"></a>手順 3: インスタント Bloomberg コネクタを作成する

最後の手順では、Microsoft 365 コンプライアンスセンターでインスタント Bloomberg コネクタを作成します。 コネクタは、提供された情報を使用して、Bloomberg SFTP サイトに接続し、チャットメッセージを Microsoft 365 の対応するユーザーメールボックスに転送します。

1. に移動 <https://compliance.microsoft.com> して、[ **データコネクタ**  >  **インスタント Bloomberg** ] をクリックします。

2. [ **インスタント Bloomberg** 製品の説明] ページで、[ **コネクタの追加** ] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。

4. [ **BLOOMBERG SFTP サイトの資格情報の追加** ] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[ **次へ** ] をクリックします。

    - **確定コード:** Bloomberg SFTP サイトのユーザー名として使用される組織の ID。

    - **パスワード:** Bloomberg SFTP サイトのパスワード。

    - **SFTP URL:** Bloomberg SFTP サイトの URL (たとえば、sftp.bloomberg.com)。

    - **SFTP ポート:** Bloomberg SFTP サイトのポート番号。 コネクタはこのポートを使用して、SFTP サイトに接続します。

5. [ **インポートするデータの種類の選択** ] ページで、 **メッセージ** とは別にインポートする必要のあるデータ型を選択します。

6. [ **ユーザーマッピング** ] ページで、自動ユーザーマッピングを有効にし、必要に応じてカスタムユーザーマッピングを提供します。

   > [!NOTE]
   > コネクタは、特定のユーザーのメールボックスにチャットメッセージアイテムをインポートします。 **InstantBloomberg** という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 コネクタは、 *CorporateEmailAddress* プロパティの値を使用して実行されます。 すべてのチャットメッセージにこのプロパティが含まれており、プロパティにはチャットメッセージのすべての参加者の電子メールアドレスが設定されています。 *CorporateEmailAddress* プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを定義することもできます。 マッピングファイルには、各ユーザーの Bloomberg UUID および対応する Microsoft 365 メールボックスアドレスが含まれている必要があります。 自動ユーザーマッピングを有効にし、カスタムマッピングを指定すると、コネクタはまずカスタムマッピングファイルを参照します。 ユーザーの Bloomberg UUID に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタはチャットアイテムの *CorporateEmailAddress* プロパティを使用します。 コネクタがカスタムマッピングファイルまたはチャットアイテムの *CorporateEmailAddress* プロパティに有効な Microsoft 365 ユーザーを見つけられない場合、そのアイテムはインポートされません。

7. [ **次へ** ] をクリックして設定を確認し、[ **準備** ] をクリックしてコネクタを作成します。

8. [ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。
