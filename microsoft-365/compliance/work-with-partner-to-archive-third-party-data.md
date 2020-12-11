---
title: パートナーと共同作業して、サード パーティのデータをアーカイブする
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Salesforce Chatter、Yahoo Messenger、または Yammer などのデータ ソースからサード パーティのデータをインポートするカスタム コネクタを設定する方法について説明します。
ms.openlocfilehash: 64e903604ea56e5f53e3cc154bd54459a6d8d554
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620213"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>パートナーと共同作業して、サード パーティのデータをアーカイブする

Microsoft パートナーと一緒に、サードパーティのデータ ソースから Microsoft 365 にデータをインポートおよびアーカイブできます。 パートナーは、サード パーティのデータ ソースからアイテムを (定期的に) 抽出し、それらのアイテムをインポートするように構成されたカスタム コネクタを提供できます。 パートナー コネクタは、アイテムのコンテンツをデータ ソースから電子メール メッセージ形式に変換し、アイテムをメールボックスに格納します。 サード パーティのデータをインポートした後は、訴訟ホールド、電子情報開示、In-Place アーカイブ、監査、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能をこのデータに適用できます。

>[!IMPORTANT]
>Microsoft [](communication-compliance.md) 365 の通信コンプライアンス ソリューションは、この記事で説明したパートナー コネクタによってインポートされたサードパーティのデータには適用できません。 

ここでは、Microsoft パートナーと一緒にサードパーティデータをインポートするために必要なプロセスと手順の概要を示します。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[手順 2: サード パーティ製のデータ メールボックスを作成して構成する](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[手順 4: パートナーに情報を提供する](#step-4-provide-your-partner-with-information)

[手順 5: Azure Active Directory にサードパーティのデータ コネクタを登録する](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>サードパーティのデータのインポート プロセスが実行される方法

次の図と説明では、パートナーとの作業時にサードパーティのデータインポート プロセスがどのように動作するのかについて説明します。
  
![サードパーティのデータのインポート プロセスが実行される方法](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. お客様は、選択したパートナーと一緒に、サードパーティのデータ ソースからアイテムを抽出し、それらのアイテムを Microsoft 365 にインポートするコネクタを構成します。
    
2. パートナー コネクタは、サードパーティの API を介して (スケジュールまたは構成に基づいて) サードパーティのデータ ソースに接続し、データ ソースからアイテムを抽出します。 パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。 メッセージ形式 [スキーマの](#more-information) 説明については、「詳細」セクションを参照してください。 
    
3. パートナー コネクタは、既知のエンド ポイント経由で Exchange Web サービス (EWS) を使用して Microsoft 365 の Azure サービスに接続します。
    
4. アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。
    
   1. **ユーザー アカウントに対応するユーザー ID を持つアイテム:** パートナー コネクタがサード パーティデータ ソース内のアイテムのユーザー ID を Microsoft 365 の特定のユーザー ID にマップできる場合、そのアイテムはユーザーの回復可能なアイテム フォルダーの **Purges** フォルダーにコピーされます。 ユーザーは Purges フォルダー内のアイテムにアクセスできません。 ただし、電子情報開示ツールを使用して Purges フォルダー内のアイテムを検索できます。
    
   1. **ユーザー アカウントに対応するユーザー ID を持たなかったアイテム:** パートナー コネクタがアイテムのユーザー ID を特定のユーザー ID にマップできない場合、そのアイテムはサードパーティのデータ メールボックスの受信トレイ フォルダーにコピーされます。 受信トレイにアイテムをインポートすると、自分または組織内の誰かがサード パーティのメールボックスにサインインして、これらのアイテムを表示および管理し、パートナー コネクタ構成で調整が必要な場合に確認できます。
 
## <a name="step-1-find-a-third-party-data-partner"></a>手順 1: サード パーティのデータのパートナーを見つける

Microsoft 365 でサード パーティのデータをアーカイブするための主要なコンポーネントは、サードパーティのデータ ソースからデータを取得し、Microsoft 365 にインポートする Microsoft パートナーを検索して操作することです。 データをインポートした後、Exchange からのメールや SharePoint および OneDrive for Business のドキュメントなど、組織の他の Microsoft データと共にアーカイブおよび保持できます。 パートナーは、組織のサード パーティデータ ソース (BlackBerry、Facebook、Google+、Thomson Reuters、Twitter、YouTube など) からデータを抽出するコネクタを作成し、そのデータを Microsoft 365 API に渡してアイテムを Exchange メールボックスに電子メール メッセージとしてインポートします。
  
次のセクションでは、Microsoft 365 のサード パーティデータをアーカイブするプログラムに参加している Microsoft パートナー (およびサポートするサード パーティデータ ソース) の一覧を示します。

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC は、次](https://www.17a-4.com) のサードパーティデータ ソースをサポートしています。
  
- BlackBerry
    
- Bloomberg データ ストリーム
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- MessageLabs データ ストリーム
    
- OpenText
    
- Oracle/ATG 'click-to-call' Live ヘルプ
    
- Pivot IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype for Business (Lync/OCS)
    
- Skype for Business Online (Lync Online)
    
- SQL データベース
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  

  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial は ](https://www.archivesocial.com) 、次のサードパーティデータ ソースをサポートしています。 
  
- Facebook
    
- Flickr
    
- 数
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet は](https://www.globanet.com) 、次のサード パーティデータ ソースをサポートしています。 
  
- AOL with Pivot クライアント 
    
- BlackBerry 呼び出しログ (v5、v10、v12)
    
- BlackBerry メッセンジャー (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg チャット
    
- Bloomberg メール
    
- Box
    
- CipherCloud for Salesforce Chatter
    
- Cisco IM &amp; プレゼンス サーバー (v10、v10.5.1 SU1、v11.0、v11.5 SU2)

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- クラウド パス

- ユーザー設定で区切られたテキスト ファイル
    
- カスタムの XML ファイル
    
- Facebook (ページ)
    
- Factset
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive
    
- Macgregor XIP

- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- ピボット
    
- Salesforce Chatter

- Skype for Business Online
    
- Skype for Business、バージョン 2007 R2 ～ 2016 (オンプレミス)
    
- Slack Enterprise Grid
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX トレーディング
    
- Twitter
    
- UBS チャット
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText は](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) 、次のサードパーティデータ ソースをサポートしています。 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

[Smarsh は](https://www.smarsh.com) 、次のサードパーティデータ ソースをサポートしています。 
  
- AIM
    
- American Idol
    
- Apple Juice
    
- AOL with Pivot クライアント
    
- Ares
    
- Bazaarvoice
    
- Bearshare
    
- BitTorrent
    
- BlackBerry 呼び出しログ (v5、v10、v12)
    
- BlackBerry メッセンジャー (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg メール
    
- CellTrust
    
- チャットのインポート
    
- チャットのリアルタイム ロギングとポリシー
    
- Chatter
    
- Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)
    
- 共同作業のインポート
    
- 共同作業のリアルタイム ロギング
    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- グテラ
    
- Google+
    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- ICE/YellowJacket
    
- IM のインポート
    
- IM のリアルタイム ロギングとポリシー
    
- Indii Messenger
    
- Instant Bloomberg
    
- IRC
    
- Jive
    
- Jive 6 Real Time Logging (v6、v7)
    
- Jive のインポート
    
- PRJTA
    
- LinkedIn
    
- Microsoft Lync (2010、2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010、2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- (1)
    
- Microsoft 365 Lync 専用
    
- Microsoft 365 共有 IM
    
- Pinterest
    
- ピボット
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo
    
- Yammer
    
- YouTube
    

### <a name="verba"></a>Verba

[Verba は](https://www.verba.com) 、次のサード パーティのデータ ソースをサポートしています。 
  
- Avaya Aura ビデオ
    
- Avaya Aura 音声
    
- Avtec ラジオ
    
- Bosch/Telex ラジオ
    
- BroadSoft ビデオ
    
- BroadSoft 音声
    
- Centile 音声
    
- Cisco Jabber IM
    
- Cisco UC ビデオ
    
- Cisco UC 音声
    
- Cisco UCCX/UCCE ビデオ
    
- Cisco UCCX/UCCE Voice
    
- ESChat ラジオ
    
- Geoman Contact Expert
    
- IP Trade 音声
    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre)
    
- Oracle / Acme Packet Session Border Controller ビデオ
    
- Oracle / Acme Packet Session Border Controller 音声
    
- Singtel モバイル ボイス
    
- SIPREC ビデオ
    
-  SIPREC 音声 
    
- Skype for Business / Lync IM
    
- Skype for Business / Lync ビデオ
    
- Skype for Business / Lync 音声
    
- Speakerbus 音声
    
- 標準的な SIP/H.323 ビデオ
    
- 標準的な SIP/H.323 音声
    
- Truphone 音声
    
- TwistedPair ラジオ
    
- Windows デスクトップ コンピューターの画面
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>手順 2: Microsoft 365 でサード パーティ製のデータ メールボックスを作成して構成する

Microsoft 365 にデータをインポートするためのサードパーティのデータ メールボックスを作成および構成する手順を次に示します。 前に説明したように、パートナー コネクタがアイテムのユーザー ID をユーザー アカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。
  
 **Microsoft 365 管理センターでこれらのタスクを完了する**
  
1. ユーザー アカウントを作成し、Exchange Online プラン 2 のライセンスを割り当てる。「Microsoft [365 にユーザーを追加する」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=692098)。 メールボックスを訴訟ホールドの対象にしたり、無制限のストレージ クォータを持つアーカイブ メールボックスを有効にするには、プラン 2 のライセンスが必要です。
    
2. Microsoft 365 の **Exchange** 管理者の役割に、サード パーティのデータ メールボックスのユーザー アカウントを追加します。 [「Microsoft 365 で管理者ロールを割り当てる」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=532393)。
    
    > [!TIP]
    > このユーザー アカウントの資格情報を控えておきます。 手順 4 で説明するように、この情報をパートナーに提供する必要があります。 
  
 **Exchange 管理センターでこれらのタスクを完了する**
  
1. 組織内のアドレス帳や他のアドレス一覧からサード パーティのデータ メールボックスを非表示にする。「ユーザー [メールボックスの管理」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=616058)。 または、次の PowerShell コマンドを実行することもできます。
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 管理者または法令遵守責任者が Outlook デスクトップ クライアントでサード パーティのデータ メールボックスを開くことができるので、サード パーティのデータ メールボックスに **FullAccess** アクセス許可を割り当てる。「受信者 [のアクセス許可の管理」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=692104)。
    
3. サード パーティのデータ メールボックスに対して、次のコンプライアンス関連機能を有効にします。
    
    - アーカイブ メールボックスを有効にします。「アーカイブ [メールボックスを有効にする」および「無制限](enable-archive-mailboxes.md) アーカイブ [を有効にする」を参照してください](enable-unlimited-archiving.md)。 これにより、サード パーティのデータ アイテムをアーカイブ メールボックスに移動するアーカイブ ポリシーを設定することで、プライマリ メールボックスの記憶領域を解放できます。 これにより、サード パーティのデータに無制限のストレージが提供されます。
    
    - サードパーティ データのメールボックスを訴訟ホールドの対象にします。 セキュリティ/コンプライアンス センターで Microsoft 365 アイテム保持ポリシーを適用できます。 このメールボックスを保留にすることで、サード パーティのデータ アイテム (無期限または指定した期間) が保持され、メールボックスから削除されるのを防ぐ。 次のいずれかのトピックを参照してください。
    
      - [メールボックスを訴訟ホールドの対象にする](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [アイテム保持ポリシーと保持ラベルの詳細](retention.md)
    
    - サードパーティのデータ メールボックスへの所有者、代理人、および管理者アクセスのメールボックス監査ログを有効にします。「メールボックス [監査を有効にする」を参照してください](enable-mailbox-auditing.md)。 これにより、サード パーティのデータ メールボックスにアクセスできるすべてのユーザーが実行したアクティビティを監査できます。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する

次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。 Exchange 管理センターを使用するか、対応するコマンドレットを使用して、これらのタスクWindows PowerShellします。
  
1. 各ユーザーのアーカイブ メールボックスを有効にします。「アーカイブ [メールボックスを有効にする」および「無制限](enable-archive-mailboxes.md) アーカイブ [を有効にする」を参照してください](enable-unlimited-archiving.md)。
    
2. ユーザーメールボックスを訴訟ホールドの対象にするか、Microsoft 365 アイテム保持ポリシーを適用する次のいずれかのトピックを参照してください。 
    
    - [メールボックスを訴訟ホールドの対象にする](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [アイテム保持ポリシーと保持ラベルの詳細](retention.md)
    
    前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。

## <a name="step-4-provide-your-partner-with-information"></a>手順 4: パートナーに情報を提供する

最後の手順では、パートナーに次の情報を提供し、ユーザー のメールボックスとサード パーティのデータ メールボックスにデータをインポートするために、組織に接続するコネクタを構成します。 
  
- Microsoft 365 の Azure サービスへの接続に使用するエンドポイント:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 手順 2 で作成したサード パーティのデータ メールボックスのサインイン資格情報 (Microsoft 365 ユーザー ID とパスワード)。 パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>手順 5: Azure Active Directory にサードパーティのデータ コネクタを登録する

2018 年 9 月 30 日から、Microsoft 365 の Azure サービスは Exchange Online の最新認証を使用して、組織に接続してデータをインポートしようとするサード パーティのデータ コネクタを認証し始める予定です。 この変更の理由は、最新の認証は、前述のエンドポイントを使用して Azure サービスに接続するサードパーティコネクタの許可リストに基づいて作成された、現在の方法よりも多くのセキュリティを提供する点にあります。

サードパーティのデータ コネクタが新しい最新の認証方法を使用して Microsoft 365 に接続するには、組織内の管理者がコネクタを Azure Active Directory に信頼できるサービス アプリケーションとして登録する同意を得る必要があります。 これは、コネクタが Azure Active Directory 内の組織のデータにアクセスするためのアクセス許可要求を受け入れて行われます。 この要求を受け入れると、サード パーティのデータ コネクタがエンタープライズ アプリケーションとして Azure Active Directory に追加され、サービス プリンシパルとして表されます。 同意プロセスの詳細については、「テナント管理者の同意  [」を参照してください](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

コネクタを登録するための要求にアクセスして受け入れる手順を次に示します。

1. このページ [に移動し](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 、グローバル管理者の資格情報を使用してサインインします。

   次のダイアログ ボックスが表示されます。 カレットを展開して、コネクタに割り当てるアクセス許可を確認できます。

   ![アクセス許可要求ダイアログが表示されます](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. [**Accept**] をクリックします。

要求を承諾すると [、Azure ポータルが](https://portal.azure.com) 表示されます。 組織のアプリケーションの一覧を表示するには **、Azure Active Directory** Enterprise アプリケーション  >  **をクリックします**。 Microsoft 365 のサード パーティ製データ コネクタが [エンタープライズ アプリケーション] ブレード **に一覧表示** されます。

> [!IMPORTANT]
> 2018 年 9 月 30 日より後、Azure Active Directory にサード パーティデータ コネクタを登録しない場合、サード パーティのデータは組織内のメールボックスにインポートされなくなりました。 既存のサードパーティ データ コネクタ (2018 年 9 月 30 日より前に作成されたコネクタ) も、手順 5 の手順に従って Azure Active Directory に登録する必要があります。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>サード パーティのデータ コネクタに対する同意の取り下

組織が Azure Active Directory にサードパーティのデータ コネクタを登録するためのアクセス許可要求に同意すると、組織はいつでもその同意を取り消す可能性があります。 ただし、コネクタの同意を取り戻すということは、サード パーティのデータ ソースからのデータが Microsoft 365 にインポートされなくなるという意味です。

サードパーティのデータ コネクタに対する同意を取り消す場合は、Azure Portal の [エンタープライズ アプリケーション] ブレードを使用するか、Microsoft 365 PowerShell の[Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal)を使用して、Azure Active Directory からアプリケーションを削除します (対応するサービス プリンシパルを削除します)。 Azure Active Directory PowerShell [で Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) コマンドレットを使用することもできます。
  
## <a name="more-information"></a>詳細

- 前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。 パートナー コネクタは、Microsoft 365 API で必要なスキーマを使用してアイテムをインポートします。 次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。 この表では、メッセージのプロパティが必須かどうかも示します。 必須プロパティは設定されている必要があります。 アイテムに必須のプロパティが存在しない場合は、Microsoft 365 にインポートされません。 インポート プロセスは、アイテムがインポートされていない理由と、不足しているプロパティを説明するエラー メッセージを返します。<br/><br/>
    
    |**メッセージのプロパティ**|**必須かどうか?**|**説明**|**値の例**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |はい  <br/> |最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。 パートナー コネクタは、ソース アイテム (Twitter ハンドルなど) のユーザー ID を、すべての参加者 (FROM フィールドと TO フィールドのユーザー) のユーザー アカウントにマップします。 メッセージのコピーが、すべての参加者のメールボックスにインポートされます。 アイテムの参加者をユーザー アカウントにマップできる場合、アイテムは Microsoft 365 のサード パーティのアーカイブ メールボックスにインポートされます。  <br/> <br/> アイテムの送信者として識別される参加者は、アイテムのインポート先の組織内にアクティブなメールボックスを持っている必要があります。 送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |はい  <br/> |アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。  <br/> | `bob@contoso.com` <br/> |
    |**件名** <br/> |いいえ  <br/> |ソース アイテムの件名。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |はい  <br/> |アイテムが最初に作成または顧客データ ソースに投稿された日付。 たとえば、Twitter メッセージがツイートされた日付などです。  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |いいえ  <br/> |メッセージまたは投稿のコンテンツ。 一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。 インポート プロセス中に、パートナー コネクタはコンテンツ ソースからの完全な忠実性を可能な限り維持します。 可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。 それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。 このプロパティの内容は、パートナー コネクタとソース プラットフォームの機能によって異なります。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |いいえ  <br/> |データ ソース内のアイテム (Twitter でのツイートやインスタント メッセージングの会話など) にファイルが添付されている場合、または画像が含まれる場合、パートナー接続はまず **BODY** プロパティに添付ファイルを含め試行します。 If that isn't possible, then it's added to the ** ATTACHMENT ** property. 添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |はい  <br/> | これは、パートナー コネクタによって作成および設定される複数値プロパティです。 このプロパティの形式は次の形式です  `IPM.NOTE.Source.Event` 。 (このプロパティは、で始まる必要があります  `IPM.NOTE` 。 この形式は、メッセージ クラスの形式  `IPM.NOTE.X` に似ています)。このプロパティには、次の情報が含まれます。  <br/><br/>`Source`: サードパーティのデータ ソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。  <br/> <br/>  `Event`: アイテムを生成したサードパーティのデータ ソースで実行されたアクティビティの種類を示します。たとえば、Twitter でのツイートや Facebook の投稿などです。 イベントはデータ ソースに固有です。  <br/> <br/>  このプロパティの目的の 1 つは、アイテムが発生したデータ ソースに基づいて、またはイベントの種類に基づいて特定のアイテムをフィルター処理することです。 たとえば、電子情報開示検索では、特定のユーザーによって投稿されたツイートを検索する検索クエリを作成できます。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Microsoft 365 のメールボックスにアイテムが正常にインポートされると、HTTP 応答の一部として一意の識別子が呼び出し元に返されます。 この識別子は、パートナーがアイテムをエンドツーエンドで追跡するために、後続のトラブルシューティングの目的  `x-IngestionCorrelationID` で使用できます。 パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。 この識別子を示す HTTP 応答の例を以下に示します。

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- セキュリティ/コンプライアンス センターのコンテンツ検索ツールを使用して、サード パーティのデータ ソースからメールボックスにインポートされたアイテムを検索できます。 これらのインポートされたアイテムを具体的に検索するには、コンテンツ検索のキーワード ボックスで次のメッセージ プロパティと値のペアを使用できます。
    
  - **`kind:externaldata`**: このプロパティと値のペアを使用して、すべてのサード パーティのデータ型を検索します。 たとえば、サード パーティのデータ ソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、キーワード クエリを使用します  `kind:externaldata AND subject:contoso` 。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**: このプロパティと値のペアを使用して、サードパーティデータの指定の種類のみを検索します。 たとえば、Subject プロパティに "contoso" という単語を含む Facebook データのみを検索するには、キーワード クエリを使用します  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 。 

  プロパティのサード パーティのデータ型に使用する値の完全な一覧については、「コンテンツ検索を使用して  `itemclass` [、Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md)にインポートされたサード パーティのデータを検索する」を参照してください。
    
   コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。
    
  - [コンテンツ検索](content-search.md)
    
  - [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
