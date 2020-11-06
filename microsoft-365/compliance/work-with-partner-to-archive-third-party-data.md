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
description: カスタムコネクタをセットアップして、Salesforce チャター、Yahoo Messenger、Yammer などのデータソースからサードパーティのデータをインポートする方法について説明します。
ms.openlocfilehash: 97e36566c3dcc9b069a39eb50e203cda971ba3c2
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931949"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>パートナーと共同作業して、サード パーティのデータをアーカイブする

Microsoft パートナーと協力して、サードパーティのデータソースから Microsoft 365 にデータをインポートしてアーカイブすることができます。 パートナーは、サードパーティのデータソースからアイテムを抽出するように構成されたカスタムコネクタ (定期的に) を提供して、それらのアイテムをインポートすることができます。 パートナーコネクタは、アイテムのコンテンツをデータソースから電子メールメッセージ形式に変換し、そのアイテムをメールボックスに格納します。 サードパーティのデータがインポートされたら、訴訟ホールド、電子情報開示、In-Place アーカイブ、監査、Microsoft 365 のアイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能をこのデータに適用できます。
 
>[!IMPORTANT]
>Microsoft 365 の [通信コンプライアンス](communication-compliance.md) ソリューションは、この記事で説明されているパートナーコネクタによってインポートされたサードパーティのデータには適用できません。 
 
ここでは、サードパーティのデータをインポートするために Microsoft パートナーと連携するために必要なプロセスと手順の概要について説明します。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[手順 2: サードパーティのデータメールボックスを作成して構成する](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[手順 4: パートナーに情報を提供する](#step-4-provide-your-partner-with-information)

[手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>サードパーティのデータのインポート プロセスが実行される方法

次の図と説明は、パートナーと連携している場合にサードパーティのデータインポートプロセスがどのように動作するかを説明します。
  
![サードパーティのデータのインポート プロセスが実行される方法](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. お客様は、選択したパートナーと連携して、サードパーティのデータソースからアイテムを抽出し、それらのアイテムを Microsoft 365 にインポートするコネクタを構成します。
    
2. パートナーコネクタは、サードパーティの API を使用してサードパーティのデータソースに接続し (スケジュールに従って、または構成されている場合)、データソースからアイテムを抽出します。 パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。 メッセージ形式スキーマの詳細については、「 [More information](#more-information) 」セクションを参照してください。 
    
3. パートナーコネクタは、既知のエンドポイントを介して Exchange Web サービス (EWS) を使用して、Microsoft 365 の Azure サービスに接続します。
    
4. アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。
    
   1. ユーザー **アカウントに対応するユーザー ID を持つアイテム:** パートナーコネクタがサードパーティのデータソース内のアイテムのユーザー ID を Office 365 の特定のユーザー ID にマップできる場合、そのアイテムはユーザーの [回復可能なアイテム] フォルダー **内の [削除] フォルダーに** コピーされます。 ユーザーがパージフォルダー内のアイテムにアクセスできません。 ただし、電子情報開示ツールを使用して、[削除] フォルダー内のアイテムを検索できます。
    
   1. ユーザー **アカウントに対応するユーザー ID を持たないアイテム:** パートナーコネクタがアイテムのユーザー ID を特定のユーザー ID にマップできない場合、そのアイテムはサードパーティのデータメールボックスの **受信トレイ** フォルダーにコピーされます。 受信トレイにアイテムをインポートすると、組織内のユーザーがサードパーティのメールボックスにサインインしてこれらのアイテムを表示および管理できるようになります。また、パートナーコネクタ構成で調整が必要かどうかを確認します。
 
## <a name="step-1-find-a-third-party-data-partner"></a>手順 1: サード パーティのデータのパートナーを見つける

Microsoft 365 でサードパーティのデータをアーカイブするための主要なコンポーネントは、サードパーティのデータソースからデータを取得して Office 365 にインポートすることに特化した Microsoft パートナーを検索して作業することです。 インポートされたデータは、組織の他の Microsoft データ (Exchange からの電子メールや SharePoint および OneDrive for business からのメールなど) と共にアーカイブおよび保存することができます。 パートナーは、組織のサードパーティのデータソース (BlackBerry、Facebook、Google +、Thomson Reuters、Twitter、YouTube など) からデータを抽出し、そのデータを電子メールメッセージとして Exchange メールボックスにインポートする Office 365 API に渡すコネクタを作成します。 
  
次のセクションでは、Office 365 でサードパーティのデータをアーカイブするためにプログラムに参加している Microsoft パートナー (およびサポートされているサードパーティのデータソース) を一覧表示します。

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 で](https://www.17a-4.com) は、次のサードパーティデータソースをサポートしています。
  
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

[ArchiveSocial ](https://www.archivesocial.com) は、次のサードパーティデータソースをサポートしています。 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com) は、次のサードパーティデータソースをサポートしています。 
  
- AOL with Pivot クライアント 
    
- BlackBerry 呼び出しログ (v5、v10、v12)
    
- BlackBerry メッセンジャー (v5、v10、v12)
    
- BlackBerry PIN (v5、v10、v12)
    
- BlackBerry SMS (v5、v10、v12)
    
- Bloomberg チャット
    
- Bloomberg メール
    
- 検索ボックス
    
- CipherCloud for Salesforce Chatter
    
- Cisco IM &amp; プレゼンスサーバー (v10、v V10.5.1 SU1、v 11.0、v 11.5 SU2)

- Cisco Webex Teams

- Citrix ワークスペースの編集 &amp; ファイル

- CrowdCompass

- カスタム区切りのテキストファイル
    
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

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) は、次のサードパーティデータソースをサポートしています。 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com) は、次のサードパーティデータソースをサポートしています。 
  
- 目的
    
- American Idol
    
- Apple Juice
    
- AOL with Pivot クライアント
    
- アレス
    
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
    
- チャター
    
- Cisco IM &amp; プレゼンスサーバー (v 9.0.1、v 9.1、v 9.1.1 SU1、v10、v V10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)
    
- 共同作業のインポート
    
- 共同作業のリアルタイム ロギング
    
- Direct Connect
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google +
    
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
    
- JXTA
    
- LinkedIn
    
- Microsoft Lync (2010、2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010、2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- ウェブ
    
- My Space
    
- NEONetwork
    
- Office 365 Lync Dedicated
    
- Office 365 Shared IM
    
- Pinterest
    
- ピボット
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- 終わり
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo
    
- Yammer
    
- YouTube
    

### <a name="verba"></a>Verba

[Verba](https://www.verba.com) は、次のサードパーティデータソースをサポートしています。 
  
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
    
- Cisco UCCX/UCCX ビデオ
    
- Cisco UCCX/UCCX 音声
    
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
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する

Office 365 にデータをインポートするためにサードパーティ製のデータメールボックスを作成して構成する手順を次に示します。 前に説明したように、パートナーコネクタがアイテムのユーザー ID をユーザーアカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。
  
 **Microsoft 365 管理センターでこれらのタスクを完了する**
  
1. ユーザーアカウントを作成し、Exchange Online プラン2ライセンスを割り当てます。「 [Office 365 にユーザーを追加する」を](https://go.microsoft.com/fwlink/p/?LinkId=692098)参照してください。 プラン2ライセンスは、メールボックスを訴訟ホールドの対象にするため、または記憶域クォータが無制限のアーカイブメールボックスを有効にするために必要です。
    
2. Office 365 で、サードパーティのデータメールボックスのユーザーアカウントを **Exchange 管理** 者の役割に追加します。「 [Office 365 で管理者ロールを割り当てる」を](https://go.microsoft.com/fwlink/p/?LinkId=532393)参照してください。
    
    > [!TIP]
    > このユーザー アカウントの資格情報を控えておきます。 手順 4 で説明するように、この情報をパートナーに提供する必要があります。 
  
 **Exchange 管理センターでこれらのタスクを完了する**
  
1. 組織内のアドレス帳およびその他のアドレス一覧から、サードパーティのデータメールボックスを非表示にします。「 [ユーザーメールボックスの管理](https://go.microsoft.com/fwlink/p/?LinkId=616058)」を参照してください。 または、次の PowerShell コマンドを実行することもできます。
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. サードパーティのデータメールボックスに **Fullaccess** のアクセス許可を割り当てて、管理者またはコンプライアンス責任者が Outlook デスクトップクライアントでサードパーティのデータメールボックスを開くことができるようにします。「 [管理者のアクセス許可を管理する」を](https://go.microsoft.com/fwlink/p/?LinkId=692104)参照してください。
    
3. サードパーティのデータメールボックスに対して、次のコンプライアンス関連の機能を有効にします。
    
    - アーカイブメールボックスを有効にします。「 [アーカイブメールボックスを有効に](enable-archive-mailboxes.md) する」および「 [無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。 これにより、サードパーティのデータアイテムをアーカイブメールボックスに移動するアーカイブポリシーを設定することによって、プライマリメールボックスの記憶域スペースを解放できます。 これにより、サードパーティのデータに対して無制限のストレージが提供されます。
    
    - サードパーティ データのメールボックスを訴訟ホールドの対象にします。 セキュリティ/コンプライアンスセンターでは、Microsoft 365 のアイテム保持ポリシーを適用することもできます。 このメールボックスを保留にすると、サードパーティのデータアイテム (無期限または指定した期間中) が保持され、それらがメールボックスから削除されるのを防ぐことができます。 次のいずれかのトピックを参照してください。
    
      - [メールボックスを訴訟ホールドの対象にする](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [アイテム保持ポリシーと保持ラベルの詳細](retention.md)
    
    - サードパーティデータメールボックスへの所有者、代理人、および管理者のアクセスに対してメールボックス監査ログを有効にします。「 [メールボックス監査を有効にする」を](enable-mailbox-auditing.md)参照してください。 これにより、サードパーティのデータメールボックスにアクセスできるすべてのユーザーによって実行されたすべてのアクティビティを監査できます。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する

次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。 Exchange 管理センターまたは対応する Windows PowerShell コマンドレットを使用して、これらのタスクを完了します。
  
1. 各ユーザーのアーカイブメールボックスを有効にします。「 [アーカイブメールボックスを有効に](enable-archive-mailboxes.md) する」および「 [無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。
    
2. ユーザーメールボックスを訴訟ホールドの対象にするか、Microsoft 365 アイテム保持ポリシーを適用します。次のいずれかのトピックを参照してください。 
    
    - [メールボックスを訴訟ホールドの対象にする](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [アイテム保持ポリシーと保持ラベルの詳細](retention.md)
    
    前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。

## <a name="step-4-provide-your-partner-with-information"></a>手順 4: パートナーに情報を提供する

最後の手順として、パートナーに次の情報を提供し、ユーザーのメールボックスとサードパーティデータメールボックスにデータをインポートするために組織に接続するためのコネクタを構成できるようにします。 
  
- Office 365 の Azure サービスに接続するために使用されるエンドポイント:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 手順2で作成したサードパーティデータメールボックスのサインイン資格情報 (Microsoft 365 ユーザー ID とパスワード)。 パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する

2018年9月30日から、Office 365 の Azure サービスは、Exchange Online での先進認証の使用を開始して、組織に接続してデータをインポートするサードパーティデータコネクタを認証します。 この変更の理由は、モダン認証によって、現在のメソッドよりも高いセキュリティが提供されるためです。これは、以前に説明したエンドポイントを使用して Azure サービスに接続するサードパーティ製コネクタの許可リストに基づいていました。

新しいモダン認証方法を使用してサードパーティ製データコネクタを Office 365 に接続できるようにするには、組織の管理者が、Azure Active Directory の信頼できるサービスアプリケーションとしてそのコネクタを登録するために同意する必要があります。 これを行うには、アクセス許可要求を受け入れ、コネクタが Azure Active Directory 内の組織のデータにアクセスできるようにします。 この要求を承諾すると、サードパーティのデータコネクタがエンタープライズアプリケーションとして Azure Active Directory に追加され、サービスプリンシパルとして表されます。 同意プロセスの詳細については、「  [テナント管理者の同意](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent)」を参照してください。

コネクタを登録するための要求をアクセスして受け入れる手順を次に示します。

1. [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動し、全体管理者の資格情報を使用してサインインします。

   次のダイアログボックスが表示されます。 Carets を展開して、コネクタに割り当てられているアクセス許可を確認できます。

   ![[アクセス許可の要求] ダイアログが表示されます。](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. [ **Accept** ] をクリックします。

要求を受け入れると、 [Azure portal](https://portal.azure.com) が表示されます。 組織のアプリケーションの一覧を表示するには、[ **Azure Active Directory**  >  **エンタープライズアプリケーション** ] をクリックします。 Office 365 サードパーティデータコネクタは、 **エンタープライズアプリケーション** ブレードに一覧表示されています。

> [!IMPORTANT]
> 2018年9月30日以降、サードパーティのデータコネクタを Azure Active Directory に登録しない場合、組織内のメールボックスにサードパーティのデータがインポートされなくなります。 注: 既存のサードパーティのデータコネクタ (2018 年9月30日より前に作成されたもの) は、手順5の手順に従って Azure Active Directory に登録する必要もあります。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>サードパーティのデータコネクタの同意を取り消す

組織がアクセス許可要求に同意して、Azure Active Directory にサードパーティデータコネクタを登録すると、組織はいつでもその同意を取り消すことができます。 ただし、コネクタの同意を取り消すということは、サードパーティのデータソースからのデータが Office 365 にインポートされなくなることを意味します。

サードパーティのデータコネクタの同意を取り消すには、Azure ポータルの [ **エンタープライズアプリケーション** ] ブレードまたは Office 365 PowerShell で [new-msolserviceprincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) を使用して、azure Active Directory からアプリケーションを削除します (対応するサービスプリンシパルを削除する)。 Azure Active Directory PowerShell で [AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) コマンドレットを使用することもできます。
  
## <a name="more-information"></a>詳細情報

- 前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。 パートナーコネクタは、Office 365 API によって必要とされるスキーマを使用してアイテムをインポートします。 次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。 この表では、メッセージのプロパティが必須かどうかも示します。 必須プロパティは設定されている必要があります。 必須のプロパティが設定されていないアイテムは、Office 365 にインポートされません。 インポートプロセスでは、アイテムがインポートされなかった理由と、不足しているプロパティがあることを示すエラーメッセージが返されます。<br/><br/>
    
    |**メッセージのプロパティ**|**必須かどうか?**|**説明**|**値の例**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |必要  <br/> |最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。 パートナーコネクタは、ソースアイテム (Twitter ハンドルなど) から、すべての参加者 ([差出人] および [宛先] フィールド内のユーザー) のユーザーアカウントにユーザー ID をマップしようとします。 メッセージのコピーが、すべての参加者のメールボックスにインポートされます。 アイテムの参加者が1人のユーザーアカウントにマップできない場合、そのアイテムは Office 365 のサードパーティ製のアーカイブメールボックスにインポートされます。  <br/> <br/> アイテムの送信者として識別される参加者は、アイテムのインポート先の組織内にアクティブなメールボックスを持っている必要があります。 送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |必要  <br/> |アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。  <br/> | `bob@contoso.com` <br/> |
    |**件名** <br/> |いいえ  <br/> |ソース アイテムの件名。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |必要  <br/> |アイテムが最初に作成または顧客データソースに投稿された日付。 たとえば、Twitter メッセージがツイートされた日時です。  <br/> | `01 NOV 2015` <br/> |
    |**物体** <br/> |いいえ  <br/> |メッセージまたは投稿のコンテンツ。 一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。 インポート処理中に、パートナーコネクタは、可能な限りコンテンツソースの完全な忠実性を維持しようとします。 可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。 それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。 このプロパティの内容は、パートナーコネクタとソースプラットフォームの機能によって異なります。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**資料** <br/> |いいえ  <br/> |データソース内のアイテム (Twitter のツイート、インスタントメッセージングの会話など) に添付ファイルがあり、画像が含まれている場合、パートナー接続は最初に **BODY** プロパティに添付ファイルを含めようとします。 これができない場合は、* * ATTACHMENT * * プロパティに追加されます。 添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |必要  <br/> | これは、パートナーコネクタによって作成および設定される複数値プロパティです。 このプロパティの形式は  `IPM.NOTE.Source.Event` です。 (このプロパティはで始まる必要があり  `IPM.NOTE` ます。 この形式は、メッセージクラスの形式と似て  `IPM.NOTE.X` います)。このプロパティには、次の情報が含まれます。  <br/><br/>`Source`: サードパーティのデータソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。  <br/> <br/>  `Event`: アイテムを生成したサードパーティのデータソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイート、または Facebook の投稿。 イベントは、データソースに固有のものです。  <br/> <br/>  このプロパティの目的の1つは、アイテムが発生元であるデータソースに基づいて、またはイベントの種類に基づいて、特定のアイテムをフィルター処理することです。 たとえば、電子情報開示検索では、検索クエリを作成して、特定のユーザーによって投稿されたすべてのツイートなど) を検索できます。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- アイテムが Office 365 のメールボックスに正常にインポートされると、一意識別子が HTTP 応答の一部として発信者に戻されます。 と呼ばれるこの識別子は  `x-IngestionCorrelationID` 、アイテムのエンドツーエンドの追跡のためにパートナーによって、以降のトラブルシューティングのために使用できます。 パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。 この識別子を示す HTTP 応答の例を以下に示します。

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、サードパーティのデータソースからメールボックスにインポートされたアイテムを検索できます。 これらのインポートされたアイテムを検索するには、次のようなメッセージのプロパティと値のペアをキーワードボックスで使用します。
    
  - **`kind:externaldata`** : このプロパティと値のペアを使用して、すべてのサードパーティのデータ型を検索します。 たとえば、サードパーティのデータソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、キーワードクエリを使用し  `kind:externaldata AND subject:contoso` ます。
    
  - **`itemclass:ipm.externaldata.<third-party data type>`** : このプロパティと値のペアを使用して、サードパーティのデータの指定した種類のみを検索します。 たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データのみを検索するには、キーワードクエリを使用し  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` ます。 

  プロパティのサードパーティデータ型に使用する値の完全な一覧につい  `itemclass` ては、「 [コンテンツ検索を使用して、Office 365 にインポートされたサードパーティのデータを検索する](use-content-search-to-search-third-party-data-that-was-imported.md)」を参照してください。
    
   コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。
    
  - [Office 365 のコンテンツ検索](content-search.md)
    
  - [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)
 
