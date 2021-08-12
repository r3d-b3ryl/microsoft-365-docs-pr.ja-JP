---
title: 組織の PST ファイルのインポートの概要
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
ms.custom:
- seo-marvel-apr2020
description: セキュリティ/コンプライアンス センターのインポート サービスを使用して、メール データ (PSTファイル) をユーザーのメールボックスに一括でインポートする方法について説明します。
ms.openlocfilehash: 0bb2235eebfcb6cc85172a286ed4f0f9b24112fda5f6c3246552bc2c8297bcc8
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819881"
---
# <a name="overview-of-importing-your-organizations-pst-files"></a>組織の PST ファイルのインポートの概要

> [!NOTE]
> この記事は管理者向けです。 自分のメールボックスに PST ファイルをインポートしようとしていますか? 「[Outlook.pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。

セキュリティ/コンプライアンス センターのインポート サービスを使用して、PST ファイルを組織の Exchange Online メールボックスにすばやく一括でインポートできます。PST ファイルを Office 365 にインポートするには 2 つの方法があります:

- **ネットワーク アップロード** ![クラウド アップロード](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - PST ファイルをネットワーク経由で Microsoft クラウド内の一時的な Azure Storage の場所にアップロードします。 次に、Office 365 インポート サービスを使用して、組織のメールボックスに PST データをインポートします。

- **ドライブの発送** ![ハード ディスク](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - PST ファイルを BitLocker で暗号化されたハード ディスク ドライブにコピーし、Microsoft にそのドライブを物理的に発送します。 Microsoft はそのハード ドライブを受け取ると、データ センターの担当者がデータを Microsoft クラウド内の一時的な Azure Storage の場所にアップロードします。 次に、Office 365 インポート サービスを使用して、組織のメールボックスにデータをインポートします。

## <a name="step-by-step-instructions"></a>詳しい手順

組織の PST ファイルを Office 365 に一括インポートする詳しい手順については、次のいずれかのトピックを参照してください。

- [ネットワーク アップロードを使用して PST ファイルを Office 365 にインストールする](use-network-upload-to-import-pst-files.md)

- [ドライブ送付を使用して PST ファイルをインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>PST ファイルのインポートのしくみ

完全な PST インポート プロセスの図と説明を示します。 図には、プライマリ ワークフローが示され、ネットワーク アップロード方法とドライブ送付方法の違いを明らかにしています。

![PST インポート プロセスのワークフロー](../media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)

1. **PST インポート ツールとキーをプライベート Azure Storage の場所にダウンロードする** - 最初の手順は、PST ファイルのアップロードまたはそれらのハード ドライブへのコピーに使用されるツールとアクセス キーのダウンロードになります。 これらは、セキュリティ/コンプライアンス センター の [**インポート**] ページで取得します。 このキーにより、PST ファイルをプライベートのセキュリティで保護された Azure Storage の場所にアップロードするために必要なアクセス許可がユーザー (またはドライブ送付の場合は、Microsoft データ センター担当者) に提供されます。 このアクセス キーは組織に固有のもので、PST ファイルを Microsoft クラウドにアップロードした後に、PST ファイルへの不正アクセスから保護するのに役立ちます。 Microsoft 365 への PST ファイルのインポートには、組織で別の Azure サブスクリプションを持つ必要はありません。

2. **PST ファイルをアップロードまたはコピーする** - 次の手順は、ネットワーク アップロード、またはドライブ送付のどちらを使用して PST ファイルをインポートするかによって異なります。 いずれの場合も、ツールと、前の手順で取得したセキュリティで保護されたストレージ キーを使用します。

    - **ネットワーク アップロード:** (手順 1 でダウンロードした) Microsoft クラウド内の Azure Storage の場所に PST ファイルをアップロードして保存するために、AzCopy.exe ツールを使用します。 PST ファイルをアップロードする Azure Storage の場所は、組織と同じ地域の Microsoft データセンターにあります。

      PST ファイルをアップロードするには、インポートするファイルが組織のファイル共有またはファイル サーバー上にある必要があります。

    - **ドライブ送付:** (手順 1 でダウンロードした) WAImportExport.exe ツールを使用して、PST ファイルをハード ドライブにコピーします。 このツールは、BitLocker を使用してハード ドライブを暗号化してから、PST ファイルをハード ドライブにコピーします。 ネットワーク アップロードと同様、ハード ドライブにコピーする PST ファイルは、組織のファイル共有またはファイル サーバー上にある必要があります。

3. **PST インポート マッピング ファイルを作成する** - PST ファイルを Azure Storage の場所にアップロードまたはハード ドライブにコピーしたら、次は PST ファイルのインポート先となるユーザーのメールボックスを指定する、コンマ区切り値 (CSV) ファイルを作成します (PST ファイルはユーザーのプライマリ メールボックスまたはアーカイブ メールボックスにインポートできます)。 Office 365 インポート サービスは、情報を使用して PST ファイルをインポートします。

4. **PST インポート ジョブを作成する** - 次の手順では、セキュリティ/コンプライアンス センターの [**PST のインポート**] ページで PST インポート ジョブを作成し、前の手順で作成した PST インポート マッピング ファイルを送信します。 ネットワーク アップロードの場合、(PST ファイルが Azure にアップロードされているため) Microsoft 365 は PST ファイル内のデータを分析し、実際に PST インポート マッピング ファイルで指定したメールボックスにインポートするデータを制御するフィルターを設定する機会を提供します。

    ドライブ送付の場合は、プロセスのこの時点で、他に次のことが行われます。

    - Microsoft データ センターにハード ドライブを物理的に送付します (Microsoft データ センターの送付先のアドレスは、インポート ジョブを作成したときに表示されます)。

    - Microsoft データ センターの担当者がハード ドライブを受け取ると、担当者はハード ドライブ上の PST ファイルをユーザーの組織の Azure Storage の場所にアップロードします。 前に説明したように、PST ファイルは、ユーザーの組織があるのと同じ地域の Microsoft データセンターにある Azure Storage の場所にアップロードされます。

      > [!NOTE]
      > ハード ドライブの PST ファイルは、Microsoft がハード ドライブを受信してから 7 から10 営業日以内に Azure にアップロードされます。

      ネットワーク アップロード プロセスと同様に、Microsoft 365 は PST ファイル内のデータを分析し、実際に PST インポート マッピング ファイルで指定したメールボックスにインポートするデータを制御するフィルターを設定する機会を提供します。

    - Microsoft がハード ドライブを返送します。

5. **メールボックスにインポートされる PST データをフィルター処理する** - インポート ジョブを作成すると (およびドライブ送付ジョブから PST ファイルが Azure Storage の場所にアップロードされると)、Microsoft 365 は PST ファイルに含まれているアイテムの経過時間とさまざまなメッセージの種類を識別することで、PST ファイル内のデータを (安全に) 分析します。 分析が完了し、データをインポートする準備ができたら、PST ファイルに含まれるすべてのデータをインポートするか、インポートするデータをトリミングするかを選ぶことができます。データをトリミングする場合は、インポートするデータを制御するフィルターを設定します。

6. **PST インポート ジョブを開始する** - インポート ジョブを開始すると、Microsoft 365 は PST インポート マッピング ファイルの情報を使用して、PST ファイルを Azure Storage の場所からユーザーのメールボックスにインポートします。 インポート ジョブの進捗情報 (インポート中の各 PST ファイルに関する情報を含む) が セキュリティ/コンプライアンス センターの [**PST のインポート**] ページに表示されます。 インポート ジョブが完了すると、ジョブの状態が [**完了**] に設定されます。

## <a name="why-import-email-data-to-microsoft-365"></a>Microsoft 365 にメール データをインポートする理由

- 組織のアーカイブ メッセージング データを Microsoft 365 にインポートする方法として役立つからです。

- [インテリジェント インポート](filter-data-when-importing-pst-files.md)機能を使用すると、PST ファイル内のアイテムをフィルター処理して、インポート先のメールボックスに実際にインポートされるアイテムを指定できます。 これにより、インポートされるデータを制御するフィルターを設定して、インポートされるデータをトリミングできます。

- メール データを Microsoft 365 にインポートすると、次のことが可能になるため、組織のアドレスのコンプライアンス確保に役立ちます。

  - [[アーカイブ メールボックス](enable-archive-mailboxes.md)] と [[無制限アーカイブ](unlimited-archiving.md)] を有効にして、ユーザーに追加のメールボックス記憶域を与える。

  - メールボックスを[訴訟ホールド](./create-a-litigation-hold.md)に配置して、コンテンツを保持する。

  - [コンテンツ検索ツール](content-search.md)を使用して、メールボックスのコンテンツを検索します。

  - [電子情報開示のケース](./get-started-core-ediscovery.md)を使用して組織の法的な調査を管理する

  - セキュリティ/コンプライアンス センターの[保持ポリシー](retention.md)を使用して、メールボックスのコンテンツを保持する期間を制御し、保存期間が終了したらコンテンツを削除する。

  - [通信コンプライアンス ポリシー](communication-compliance.md)を使用してメッセージを検査し、メッセージ基準に準拠しているかどうかを確認して、分類タイプを追加します。

- Microsoft 365 へのデータのインポートは、データ損失を防ぐのに役立ちます。 Microsoft 365 にインポートされたメール データは、Exchange Online の高可用性機能を継承します。

- メール データがクラウドに格納されるので、ユーザーはあらゆるデバイスからデータを利用できます。

## <a name="importing-sharepoint-data-to-microsoft-365"></a>SharePoint データの Microsoft 365 へのインポート

組織内の SharePoint サイトと OneDrive アカウントにファイルとドキュメントをインポートすることもできます。詳細については、次の記事を参照してください。

- [SharePoint Online に移行する](/sharepointmigration/migrate-to-sharepoint-online)

- [SharePoint 移行ツールの概要](/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [PowerShell を使用して SharePoint Onine に移行する](/sharepointmigration/overview-spmt-ps-cmdlets)

- [Azure Data Box を使用して ファイル共有コンテンツを SharePoint Onine に移行する](/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)

## <a name="frequently-asked-questions-about-importing-pst-files"></a>PST ファイルのインポートについてよく寄せられる質問

Office 365 インポート サービスを使用して PST ファイルを Microsoft 365 のメールボックスに一括インポートすることについてよく寄せられる質問を紹介します。

- [ネットワーク アップロードを使用して PST ファイルをインポートする](#using-network-upload-to-import-pst-files)

- [ドライブ送付を使用して PST ファイルをインポートする](#using-drive-shipping-to-import-pst-files)

### <a name="using-network-upload-to-import-pst-files"></a>ネットワーク アップロードを使用して PST ファイルをインポートする

#### <a name="what-permissions-are-required-to-create-import-jobs-in-the-office-365-import-service-using-network-upload"></a>Office 365 インポート サービスでネットワーク アップロードを使用してインポート ジョブを作成するにはどのようなアクセス許可が必要ですか?

PST ファイルを Microsoft 365 メールボックスにインポートするには、Exchange Online で Mailbox Import Export の役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は "Organization Management/組織の管理" 役割グループに追加できます。 または、新しい役割グループを作成し、Mailbox Import Export 役割を割り当て、自分や他のユーザーをメンバーとして追加できます。 詳細については、「[Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups)」 (Exchange Online の役割グループの管理) の "Add a role to a role group" (役割グループに役割を追加する) または "Create a role group" (役割グループを作成する) を参照してください。

さらに、セキュリティ/コンプライアンス センターでインポート ジョブを作成するには、次のいずれかを満たす必要があります。

- Exchange Online の Mail Recipients 役割が割り当てられている必要があります。既定では、この役割は組織の管理の役割グループと受信者の管理の役割グループに割り当てられます。

    または

- 組織の全体管理者である必要があります。

> [!TIP]
> PST ファイルを Office 365 にインポートするための新しい役割グループを Exchange Online で作成することを検討してください。PST ファイルのインポートに必要な最小限の特権レベルについては、メールボックスのインポート エクスポートとメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。

#### <a name="where-is-network-upload-available"></a>ネットワーク アップロードはどこで利用できますか? 

現在のところ、ネットワーク アップロードは米国、カナダ、ブラジル、英国、フランス、ドイツ、スイス、ノルウェー、欧州、インド、東アジア、東南アジア、日本、韓国、オーストラリア、アラブ首長国連邦 (UAE) でご利用いただけます。ネットワーク アップロードはその他の地域でも間もなく利用可能になります。

#### <a name="what-is-the-pricing-for-importing-pst-files-by-using-network-upload"></a>What is the pricing for importing PST files by using network upload?

Using network upload to import PST files is free.

つまり、PST ファイルが Azure Storage 領域から削除されると、Microsoft 365 管理センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。 インポート ジョブは引き続き [**Office 365 へのデータのインポート**] ページに表示されることがありますが、古いインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。

#### <a name="what-version-of-the-pst-file-format-is-supported-for-importing-to-office-365"></a>What version of the PST file format is supported for importing to Office 365?

There are two versions of the PST file format: ANSI and Unicode. Unicode PST ファイル形式を使用したファイルをインポートすることをお勧めします。 ただし、2 バイト文字セット (DBCS) を使用する言語のファイルのように、ANSI PST ファイル形式を使用したファイルも Office 365 にインポートできます。 ANSI PST ファイルをインポートする方法の詳細については、「[ネットワーク アップロードを使用して PST ファイルを Office 365 にインポートする](./use-network-upload-to-import-pst-files.md)」の手順 4 を参照してください。

また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にもインポートできます。

#### <a name="after-i-upload-my-pst-files-to-the-azure-storage-area-how-long-are-they-kept-in-azure-before-theyre-deleted"></a>Azure Storage 領域に PST ファイルをアップロードした後、ファイルが削除されるまで、どれくらいの期間 Azure に保持されますか?

ネットワーク アップロードの方法を使用して PST ファイルをインポートする場合、ファイルは `ingestiondata` という Azure の blob コンテナーにアップロードします。 セキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページで進捗中のインポート ジョブがない場合、一番新しいインポート ジョブが セキュリティ/コンプライアンス センター で作成されてから 30 日後に、Azure の `ingestiondata` コンテナーにあるすべての PST ファイルが削除されます。 つまり、ユーザーは PST ファイルを Azure にアップロードしてから 30 日以内に、(ネットワークのアップロード手順の手順 5 で示すように) セキュリティ/コンプライアンス センター で新しいインポート ジョブを作成する必要があります。

つまり、PST ファイルが Azure Storage 領域から削除されると、セキュリティ/コンプライアンス センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。 インポート ジョブがセキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページの一覧に引き続き表示されていても、以前のインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。

#### <a name="how-long-does-it-take-to-import-a-pst-file-to-a-mailbox-using-network-upload"></a>ネットワーク アップロードを使用してメールボックスに PST ファイルをインポートするには、どれぐらい時間がかかりますか?

ネットワークの性能によって異なりますが、一般的には組織の Azure Storage 領域にアップロードするデータ 1 TB あたり数時間かかります。 PST ファイルが Azure Storage 領域にコピーされると、各 PST ファイルは 1 日あたり 24 GB 以上の速度で Microsoft 365 のメールボックスにインポートされます<sup>\*</sup>。 この速度ではお客様のニーズが満たされない場合、メール データを Office 365 に移行するための他の方法を検討することをお勧めします。 詳細については、「[複数のメール アカウントを Office 365 に移行する方法](/Exchange/mailbox-migration/mailbox-migration)」を参照してください。

<sup>\*</sup> このレートは保証されません。 サーバー ワークロードと一時的なパフォーマンスの問題により、この速度が低下する可能性があります。

複数の PST ファイルを異なる複数のメールボックスにインポートする場合、インポート プロセスは並行して実行されます。つまり、対になるそれぞれの PST とメールボックスが同時にインポートされます。 複数の PST ファイルを同じメールボックスにインポートする場合も、同時ではなく順次インポートされます (一度に 1 ファイルずつ)。

#### <a name="how-does-the-pst-import-process-handle-duplicate-email-items"></a>PST インポート プロセスでは、重複するメールアイテムはどのように処理されますか?

PST　インポート プロセスによってアイテムの重複がチェックされます。インポート先のメールボックス内またはインポート先のアーカイブ内のインポート先フォルダーに一致するアイテムがある場合、一致するアイテムは PST ファイルからメールボックスまたはアーカイブにコピーされません。 同じ PST ファイルをインポートして、(PST インポート マッピング ファイルの TargetRootFolder プロパティを使用して) 異なるインポート先フォルダーを指定すると、その PST ファイル内のすべてのアイテムが再インポートされます。

#### <a name="is-there-a-message-size-limit-when-importing-pst-files-using-network-upload"></a>ネットワーク アップロードを使用して PST ファイルをインポートするときにメッセージ サイズに制限はありますか?

はい。 PST ファイルに 150 MB を超えるメールボックス アイテムが含まれる場合、そのアイテムはインポート プロセスでスキップされ、インポートされません。 Exchange Online では 150 MB がメッセージ サイズの制限であるため、150 MB を超えるアイテムはインポートされません。 詳細については、「[Exchange Online のメッセージの制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits)」を参照してください。

#### <a name="are-message-properties-such-as-when-the-message-was-sent-or-received-the-list-of-recipients-and-other-properties-preserved-when-pst-files-are-imported-to-a-microsoft-365-mailbox-using-network-upload"></a>メッセージの送受信時刻や受信者のリストなどのメッセージ プロパティは、PST ファイルをネットワーク アップロードを使用して Microsoft 365 メールボックスにインポートするときに保持されますか?

はい。インポート プロセス中は、元のメッセージのメタデータが変更されることはありません。

#### <a name="is-there-a-limit-to-the-number-of-levels-in-a-folder-hierarchy-for-a-pst-file-that-i-want-to-import-to-a-mailbox-using-network-upload"></a>ネットワーク アップロードを使用してメールボックスにインポートする PST ファイルのフォルダー階層のレベルの数に制限はありますか?

はい。300 以上のネストされたフォルダーのレベルを持つ PST ファイルをインポートすることはできません。

#### <a name="can-i-use-network-upload-to-import-pst-files-to-an-inactive-mailbox-in-office-365"></a>Can I use network upload to import PST files to an inactive mailbox in Office 365?

Yes, this capability is now available.

#### <a name="can-i-use-network-upload-to-import-pst-files-to-an-online-archive-mailbox-in-an-exchange-hybrid-deployment"></a>Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?

Yes, this capability is now available.

#### <a name="can-i-use-network-upload-to-import-pst-files-to-public-folders-in-exchange-online"></a>ネットワーク アップロードを使用して PST ファイルを Exchange Online のパブリック フォルダーにインポートできますか?

いいえ、PST ファイルをパブリック フォルダーにはインポートできません。

### <a name="using-drive-shipping-to-import-pst-files"></a>ドライブ送付を使用して PST ファイルをインポートする

#### <a name="what-permissions-are-required-to-create-import-jobs-in-the-office-365-import-service-using-drive-shipping"></a>Office 365 インポート サービスでドライブ送付を使用してインポート ジョブを作成するにはどのようなアクセス許可が必要ですか?

PST ファイルを Microsoft 365 メールボックス にインポートするには、Mailbox Import Export の役割を割り当てる必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は "Organization Management/組織の管理" 役割グループに追加できます。 または、新しい役割グループを作成し、Mailbox Import Export 役割を割り当て、自分や他のユーザーをメンバーとして追加できます。 詳細については、「[Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups)」 (Exchange Online の役割グループの管理) の "Add a role to a role group" (役割グループに役割を追加する) または "Create a role group" (役割グループを作成する) を参照してください。

さらに、セキュリティ/コンプライアンス センターでインポート ジョブを作成するには、次のいずれかを満たす必要があります。

- Exchange Online の Mail Recipients 役割が割り当てられている必要があります。既定では、この役割は組織の管理の役割グループと受信者の管理の役割グループに割り当てられます。

    または

- 組織の全体管理者である必要があります。

> [!TIP]
> PST ファイルを Office 365 にインポートするための新しい役割グループを Exchange Online で作成することを検討してください。PST ファイルのインポートに必要な最小限の特権レベルについては、メールボックスのインポート エクスポートとメール受信者の役割を新しい役割グループに割り当ててから、メンバーを追加します。

#### <a name="where-is-drive-shipping-available"></a>ドライブ発送はどこで利用できますか? 

現在のところ、ドライブ発送は米国、カナダ、ブラジル、英国、欧州、インド、東アジア、東南アジア、日本、韓国、オーストラリアでご利用いただけます。ドライブ発送はその他の地域でも間もなく利用可能になります。

> [!NOTE]
> 現時点では、PST ファイルをインポートするためのドライブ送付は、ドイツとスイスでは利用できません。 この FAQ は、これらの国でドライブ送付が利用可能になると更新されます。

#### <a name="what-commercial-licensing-agreements-support-drive-shipping"></a>ドライブ発送をサポートする商用の使用許諾契約は何ですか。

Microsoft 365 に PST ファイルをインポートするためのドライブ発送は、Microsoft Enterprise Agreement (EA) に従って入手できます。ドライブの発送は、Microsoft 製品サービス契約 (MPSA) では利用できません。

#### <a name="what-is-the-pricing-for-using-drive-shipping-to-import-pst-files-to-microsoft-365"></a>ドライブの発送を使用して PST ファイルを Microsoft 365 にインポートすると、料金はいくらですか?

ドライブの発送を使用して PST ファイルを Microsoft 365 メールボックスにインポートするコストは、1 GB のデータあたり 2 米ドルです。 たとえば、1,000 GB (1 TB) の PST ファイルを含むハード ディスク ドライブを発送する場合のコストは、2,000 米ドルです。 インポート手数料は、パートナーと分担して支払うことができます。 パートナーを探す方法については、「[Microsoft パートナーまたは販売店を探す](../admin/manage/find-your-partner-or-reseller.md)」を参照してください。

#### <a name="what-kind-of-hard-drives-are-supported-for-drive-shipping"></a>ドライブ発送では、どのような種類のハード ドライブがサポートされていますか。

Office 365 インポート サービスで使用できるのは、2.5 インチ ソリッド ステート ドライブ (SSD) または 2.5 インチまたは 3.5 インチ SATA II/III 内部ハード ドライブのみです。最大 10 TB のハード ドライブを使用できます。インポート ジョブの場合、ハード ドライブ上の最初のデータ ボリュームのみが処理されます。データ ボリュームは NTFS でフォーマットする必要があります。データをハード ドライブにコピーする場合は、2.5 インチ SSD または 2.5 インチまたは 3.5 インチ SATA II/III コネクタを使用して直接接続するか、外付けの 2.5 インチ SSD または 2.5 インチまたは 3.5 インチ SATA II/III USB アダプターを使用して外部に接続できます。

> [!IMPORTANT]
> 組み込みの USB アダプターに付属する外付けハード ドライブは、Office 365 インポート サービスではサポートされていません。また、外付けハード ドライブのケース内のディスクは使用できません。外付けハード ドライブは発送しないでください。

#### <a name="how-many-hard-drives-can-i-ship-for-a-single-import-job"></a>How many hard drives can I ship for a single import job?

You can ship a maximum of 10 hard drives for a single import job.

#### <a name="after-i-ship-my-hard-drive-how-long-does-it-take-to-get-to-the-microsoft-datacenter"></a>ハードドライブを送付した後、Microsoft データセンターに到着するまでどのくらいの時間がかかりますか?

いくつかの要因によって決まります。Microsoft データ センターからの距離や、ハード ディスク ドライブを発送するために使用した発送オプションの種類 (翌日到、着翌々日到着、数日後到着) などです。ほとんどの運送会社で追跡番号を利用し、発送状況を追跡できます。

#### <a name="after-my-hard-drive-arrives-at-the-microsoft-datacenter-how-long-does-it-take-to-upload-my-pst-files-to-azure"></a>Microsoft データセンターにハード ドライブが到着してから PST ファイルが Azure にアップロードされるまで、どれくらいかかりますか?

Microsoft データ センターにハード ドライブが到着した後、PST ファイルが組織の Azure Storage 領域にアップロードされるまで、7 から 10 営業日かかります。 PST ファイルは、`ingestiondata` と呼ばれる Azure blob コンテナーにアップロードされます。

#### <a name="how-long-does-it-take-to-import-a-pst-file-to-a-mailbox-using-drive-shipping"></a>ドライブ送付を使用してメールボックスに PST ファイルをインポートするには、どれぐらい時間がかかりますか?

PST ファイルが Azure Storage 領域にアップロードされると、Microsoft 365 が (セキュリティで保護された安全な方法で) PST ファイル内のデータを分析して、アイテムの経過時間と、PST ファイルに含まれるさまざまなメッセージの種類を識別します。 この分析が完了したら、PST ファイルのすべてのデータをインポートしたり、フィルターを設定してインポートするデータを制御したりできます。 インポート ジョブを開始した後、PST ファイルは 1 日に少なくとも 24 GB の速さで Microsoft 365 メールボックスにインポートされます。 この速度ではお客様のニーズが満たされない場合、メール データを Microsoft 365 に移行するための他の方法を検討することをお勧めします。 詳細については、「[複数のメール アカウントを Microsoft 365 に移行する方法](/Exchange/mailbox-migration/mailbox-migration)」を参照してください。

複数の PST ファイルを異なる複数のメールボックスにインポートする場合、インポート プロセスは並行して実行されます。つまり、対になるそれぞれの PST とメールボックスが同時にインポートされます。 複数の PST ファイルを同じメールボックスにインポートする場合も、同時ではなく順次インポートされます (一度に 1 ファイルずつ)。

#### <a name="after-microsoft-uploads-my-pst-files-to-azure-how-long-are-they-kept-in-azure-before-theyre-deleted"></a>Microsoft が私の PST ファイルを Azure にアップロードした後、削除されるまで、どのくらいの期間 Azure に保持されますか?

組織の Azure Storage の保存場所 (`ingestiondata` と呼ばれる blob コンテナー) にあるすべての PST ファイルは、最新のインポート ジョブがセキュリティ/コンプライアンス センターの [**PST ファイルのインポート**] ページで作成されてから 30 日後に削除されます。

つまり、PST ファイルが Azure Storage 領域から削除されると、セキュリティ/コンプライアンス センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。 インポート ジョブがセキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページの一覧に引き続き表示されていても、以前のインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。

#### <a name="what-version-of-the-pst-file-format-is-supported-for-importing-to-microsoft-365"></a>Microsoft 365 へのインポートがサポートされている PST ファイル形式のバージョンは何ですか?

PST ファイル形式には、ANSI と Unicode という 2 つのバージョンがあります。 Unicode PST ファイル形式を使用したファイルをインポートすることをお勧めします。 ただし、2 バイト文字セット (DBCS) を使用する言語のファイルのように、ANSI PST ファイル形式を使用したファイルも Microsoft 365 にインポートできます。 ANSI PST ファイルをインポートする方法の詳細については、「[ドライブの発送を使用して組織の PST ファイルを Microsoft 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)」の手順 3 を参照してください。

また、Outlook 2007 以降のバージョンの PST ファイルを Microsoft 365 にもインポートできます。

#### <a name="is-there-a-message-size-limit-when-importing-pst-files-using-drive-shipping"></a>ドライブ送付を使用して PST ファイルをインポートするときにメッセージ サイズに制限はありますか?

はい。 PST ファイルに 150 MB を超えるメールボックス アイテムが含まれる場合、そのアイテムはインポート プロセスでスキップされ、インポートされません。 Exchange Online では 150 MB がメッセージ サイズの制限であるため、150 MB を超えるアイテムはインポートされません。 詳細については、「[Exchange Online のメッセージの制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits)」を参照してください。

  PST インポート プロセスでは、重複するメールアイテムはどのように処理されますか?

PST　インポート プロセスによってアイテムの重複がチェックされます。インポート先のメールボックス内またはインポート先のアーカイブ内のインポート先フォルダーに一致するアイテムがある場合、一致するアイテムは PST ファイルからメールボックスまたはアーカイブにコピーされません。 同じ PST ファイルをインポートして、(PST インポート マッピング ファイルの TargetRootFolder プロパティを使用して) 異なるインポート先フォルダーを指定すると、その PST ファイル内のすべてのアイテムが再インポートされます。

#### <a name="are-message-properties-such-as-when-the-message-was-sent-or-received-the-list-of-recipients-and-other-properties-preserved-when-pst-files-are-imported-to-a-microsoft-365-mailbox-using-drive-shipping"></a>メッセージの送受信時刻や受信者のリストなどのメッセージ プロパティは、PST ファイルをドライブ送付を使用して Microsoft 365 メールボックスにインポートするときに保持されますか?

はい。インポート プロセス中は、元のメッセージのメタデータが変更されることはありません

#### <a name="is-there-a-limit-to-the-number-of-levels-in-a-folder-hierarchy-for-a-pst-file-that-i-want-to-import-to-a-mailbox-using-drive-shipping"></a>ドライブ送付を使用してメールボックスにインポートする PST ファイルのフォルダー階層のレベルの数に制限はありますか?

はい。300 以上のネストされたフォルダーのレベルを持つ PST ファイルをインポートすることはできません。

#### <a name="can-i-use-drive-shipping-to-import-pst-files-to-an-inactive-mailbox-in-microsoft-365"></a>ドライブ発送を使用して PST ファイルを Microsoft 365 の非アクティブなメールボックスにインポートすることはできますか?

Yes, this capability is now available.

#### <a name="can-i-use-drive-shipping-to-import-pst-files-to-an-online-archive-mailbox-in-an-exchange-hybrid-deployment"></a>Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?

Yes, this capability is now available.

#### <a name="can-i-use-drive-shipping-to-import-pst-files-to-public-folders-in-exchange-online"></a>ドライブの発送を使用して PST ファイルを Exchange Online のパブリック フォルダーにインポートできますか?

いいえ、PST ファイルをパブリック フォルダーにはインポートできません。

#### <a name="can-microsoft-wipe-my-hard-drive-before-they-ship-it-back-to-me"></a>Microsoft からハード ディスク ドライブが返送される前に、Microsoft はハード ディスク ドライブのデータを消去できますか?

No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.

#### <a name="can-microsoft-shred-my-hard-drive-instead-of-shipping-it-back-to-me"></a>Can Microsoft shred my hard drive instead of shipping it back to me?

No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.

#### <a name="what-courier-services-are-supported-for-return-shipping"></a>What courier services are supported for return shipping?

If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.

#### <a name="what-are-the-return-shipping-costs"></a>What are the return shipping costs?

Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.

#### <a name="can-i-use-a-custom-courier-shipping-service-such-as-fedex-custom-shipping-to-ship-my-hard-drive-to-microsoft"></a>Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?

はい。

#### <a name="if-i-have-to-ship-my-hard-drive-to-another-country-is-there-anything-i-need-to-do"></a>If I have to ship my hard drive to another country, is there anything I need to do?

Microsoft 宛てに発送するハード ディスク ドライブは、国境を越える場合があります。この場合、ハード ディスク ドライブとドライブに含まれているデータが、輸出入に関する適用法に違反しないことを保証するのはお客様の責任になります。ハード ドライブを発送する前に、指定した Microsoft データ センターへのディスクとデータの送付について、法律違反事項がないことを助言者に確認してください。そうすることで、ドライブが Microsoft に適時に到着します。
