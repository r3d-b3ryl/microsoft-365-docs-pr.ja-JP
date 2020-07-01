---
title: Bloomberg メッセージデータをアーカイブするためのコネクタの設定
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、Bloomberg メッセージ電子メールツールから Microsoft 365 にデータをインポートしてアーカイブするためのデータコネクタをセットアップできます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 700a0619d2299fc7254628059787478cc0e168fa
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937364"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data-preview"></a>Bloomberg メッセージデータをアーカイブするコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンスセンターのデータコネクタを使用して、 [Bloomberg メッセージ](https://www.bloomberg.com/professional/product/collaboration/)コラボレーションツールから金融サービスの電子メールデータをインポートおよびアーカイブします。 コネクタをセットアップして構成した後は、組織の Bloomberg secure FTP (SFTP) サイトに毎日一度接続し、メールアイテムを Microsoft 365 のメールボックスにインポートします。

Bloomberg メッセージデータがユーザーのメールボックスに保存された後、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、通信コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を Bloomberg メッセージデータに適用することができます。 たとえば、コンテンツ検索ツールを使用して Bloomberg メッセージメールを検索したり、Bloomberg メッセージデータを含むメールボックスを高度な電子情報開示ケースの保管担当者に関連付けることができます。 Microsoft 365 で Bloomberg メッセージコネクタを使用してデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-bloomberg-message-data"></a>Bloomberg メッセージデータのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 で Bloomberg メッセージデータをアーカイブするプロセスについて説明します。

![Bloomberg メッセージのインポートとアーカイブのプロセス](../media/BloombergMessageArchiving.png)

1. 組織は Bloomberg を使用して、Bloomberg SFTP サイトをセットアップします。 また、Bloomberg を使用して Bloomberg メッセージを構成し、電子メールメッセージを Bloomberg SFTP サイトにコピーします。

2. 24時間ごとに、Bloomberg メッセージからの電子メールメッセージが Bloomberg SFTP サイトにコピーされます。

3. Microsoft 365 コンプライアンスセンターで作成した Bloomberg メッセージコネクタが、毎日 Bloomberg SFTP サイトに接続し、電子メールメッセージを、過去24時間から Microsoft クラウド内のセキュアな Azure ストレージ領域に転送します。

4. コネクタは、電子メールメッセージアイテムを特定のユーザーのメールボックスにインポートします。 BloombergMessage という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。 

   コネクタは、CorporateEmailAddress プロパティの値を使用してこれを実行します。 すべての電子メールメッセージにはこのプロパティが含まれており、電子メールメッセージのすべての参加者の電子メールアドレスが設定されます。 *CorporateEmailAddress*プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを定義することもできます。 このマッピングファイルには、組織内の各ユーザーの Bloomberg UUID と、対応する Microsoft 365 メールボックスアドレスが含まれています。 自動ユーザーマッピングを有効にしてカスタムマッピングを指定すると、コネクタはまずカスタムマッピングファイルを調べます。 ユーザーの Bloomberg UUID に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタは電子メールアイテムの*CorporateEmailAddress*プロパティを使用します。 コネクタが、カスタムマッピングファイルまたは電子メールアイテムの*CorporateEmailAddress*プロパティに有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>はじめに

Bloomberg メッセージデータをアーカイブするために必要な実装手順の多くは、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に、完了する必要があります。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Office 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 手順3で Bloomberg メッセージコネクタを正常に作成するには、この手順を完了する必要があります。

- [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)にサブスクライブします。 これは、Bloomberg Anywhere にログインして、設定および構成する必要がある Bloomberg SFTP サイトにアクセスできるようにするために必要です。

- Bloomberg SFTP (Secure file transfer protocol) サイトをセットアップします。 Bloomberg を使用して SFTP サイトを設定した後は、Bloomberg メッセージからのデータが毎日 SFTP サイトにアップロードされます。 手順2で作成したコネクタがこの SFTP サイトに接続し、電子メールデータを Microsoft 365 メールボックスに転送します。 SFTP は、転送プロセス中にメールボックスに送信される Bloomberg メッセージデータも暗号化します。

  Bloomberg SFTP ( *BB*とも呼ばれます) の詳細については、以下を参照してください。

  - 「 [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/)」の「SFTP Connectivity 標準」ドキュメントを参照してください。

  - [Bloomberg カスタマーサポート](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)に問い合わせてください。

   > [!NOTE]
   > 組織がインスタント Bloomberg データをアーカイブするためにコネクタを既に展開している場合は、別の SFTP サイトを設定する必要はありません。 Bloomberg メッセージコネクタと同じ SFTP サイトを使用できます。

- Bloomberg を使用して SFTP サイトを設定した後、Bloomberg は Bloomberg 実装の電子メールメッセージに応答した後に情報を提供します。 次の情報のコピーを保存します。 これを使用して、手順3でコネクタを設定します。

  - 企業の ID であり、Bloomberg SFTP サイトにログインするために使用される、企業のコードです。

  - Bloomberg SFTP サイトのパスワード

  - Bloomberg SFTP サイトの URL (たとえば、sftp.bloomberg.com)。 さらに、Bloomberg は Bloomberg SFTP サイトに対応する IP アドレスも提供することがあります。これは、コネクタの設定にも使用できます。

  - Bloomberg SFTP サイトのポート番号

- 手順3で Bloomberg メッセージコネクタを作成したユーザー (および手順1で公開キーと IP アドレスをダウンロードするユーザー) に、Exchange Online のメールボックスのインポートのエクスポート役割を割り当てる必要があります。 これは、Microsoft 365 コンプライアンスセンターの [**データコネクタ**] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。


## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>手順 1: SSH と PGP の公開キーを取得する

最初の手順として、Secure Shell (SSH) およびかなり良好なプライバシー (PGP) のための公開キーのコピーを取得します。 手順2でこれらのキーを使用して、Bloomberg SFTP サイトを構成して、コネクタ (手順3で作成したもの) が SFTP サイトに接続し、Bloomberg メッセージの電子メールデータを Microsoft 365 メールボックスに転送できるようにします。 また、この手順では IP アドレスも取得します。これは、Bloomberg SFTP サイトを構成するときに使用します。

1. [] に移動し https://compliance.microsoft.com\ https://compliance.microsoft.com) 、左側のナビゲーションで [**データコネクタ**] をクリックします。

2. [**データコネクタ**] ページの**Bloomberg メッセージ**で、[**表示**] をクリックします。

3. [ **Bloomberg Message** product description] ページで、[**コネクタの追加**] をクリックします。

4. [**サービス利用規約**] ページで、[**同意**する] をクリックします。

5. [ **BLOOMBERG SFTP の資格情報の追加**] の手順1で、 **[SSH キーのダウンロード**]、[ **PGP キーのダウンロード**]、および [ **IP アドレス**のダウンロード] リンクをクリックして、各ファイルのコピーをローカルコンピューターに保存します。 これらのファイルには、手順2で Bloomberg SFTP サイトを構成するために使用される次の項目が含まれています。

   - SSH 公開キー: このキーは、コネクタが Bloomberg SFTP サイトに接続する際にセキュリティで保護されたリモートログインを有効にするように Secure Shell (SSH) を構成するために使用されます。

   - PGP 公開キー: このキーは、Bloomberg SFTP サイトから Microsoft 365 に転送されるデータの暗号化を構成するために使用されます。

   - IP アドレス: Bloomberg SFTP サイトは、この IP アドレスからの接続要求のみを受け入れるように構成されています。これは、手順3で作成した Bloomberg メッセージコネクタによって使用されます。

6. ウィザードを閉じるには、[**キャンセル**] をクリックします。 このウィザードに戻り、手順3でコネクタを作成します。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>手順 2: Bloomberg SFTP サイトを構成する

> [!NOTE]
> 前述したように、インスタント Bloomberg データをアーカイブするために以前に Bloomberg SFTP サイトをセットアップしている組織の場合は、別のデータを設定する必要はありません。 手順3でコネクタを作成するときに、同じ SFTP サイトを指定することができます。

次の手順では、SSH と PGP の公開キーと、手順1で取得した IP アドレスを使用して、Bloomberg SFTP サイトの SSH 認証と PGP 暗号化を構成します。 これにより、手順3で作成した Bloomberg メッセージコネクタが Bloomberg SFTP サイトに接続し、Bloomberg メッセージデータを Microsoft 365 に転送できるようになります。 Bloomberg SFTP サイトを設定するには、Bloomberg カスタマーサポートと連携する必要があります。 詳細については、 [Bloomberg カスタマーサポート](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)にお問い合わせください。

> [!IMPORTANT]
> Bloomberg では、手順1でダウンロードした3つのファイルを電子メールメッセージに添付して、Bloomberg SFTP サイトを設定するために作業する際にカスタマーサポートチームに送信することをお勧めします。

## <a name="step-3-create-a-bloomberg-message-connector"></a>手順 3: Bloomberg メッセージコネクタを作成する

最後の手順では、Microsoft 365 コンプライアンスセンターで Bloomberg メッセージコネクタを作成します。 コネクタは、提供された情報を使用して、Bloomberg SFTP サイトに接続し、電子メールメッセージを Microsoft 365 の対応するユーザーメールボックスに転送します。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。

2. [**データコネクタ**] ページの**Bloomberg メッセージ**で、[**表示**] をクリックします。

3. [ **Bloomberg Message** product description] ページで、[**コネクタの追加**] をクリックします。

4. [**サービス利用規約**] ページで、[**同意**する] をクリックします。

5. [ **BLOOMBERG SFTP サイトの資格情報の追加**] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[**次へ**] をクリックします。

      - **確定コード:** Bloomberg SFTP サイトのユーザー名として使用される組織の ID。

      - **パスワード:** 組織の Bloomberg SFTP サイトのパスワード。

      - **SFTP URL:** Bloomberg SFTP サイトの URL (たとえば、sftp.bloomberg.com)。

      - **SFTP ポート:** Bloomberg SFTP サイトのポート番号。 コネクタはこのポートを使用して、SFTP サイトに接続します。

6. [**ユーザーマッピング**] ページで、自動ユーザーマッピングを有効にし、必要に応じてカスタムユーザーマッピングを提供します。

7. [**次へ**] をクリックして設定を確認し、[準備] をクリックしてコネクタを作成します。

8. [**データコネクタ**] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- Bloomberg のスレッド化 Microsoft 365 にインポートされた電子メールメッセージはサポートされていません。 個人に送信された個々のメッセージはインポートされますが、スレッド化された会話では表示されません。 Microsoft は、Bloomberg メッセージデータコネクタの今後のバージョンでのスレッド処理をサポートしています。
