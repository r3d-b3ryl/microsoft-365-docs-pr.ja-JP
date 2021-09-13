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
description: カスタム コネクタをセットアップして、Salesforce Chatter、Yahoo Messenger、またはデータ ソースなどのデータ ソースからサードパーティのデータをインポートするYammer。
ms.openlocfilehash: 8a18f84cce226ce4255c47772e2f858eaa6f1bb4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221825"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>パートナーと共同作業して、サード パーティのデータをアーカイブする

Microsoft パートナーと一緒に作業して、サード パーティ製のデータ ソースからデータをインポートおよびアーカイブし、Microsoft 365。 パートナーは、サードパーティのデータ ソースからアイテムを抽出し (定期的に) それらのアイテムをインポートするように構成されたカスタム コネクタを提供できます。 パートナー コネクタは、アイテムのコンテンツをデータ ソースから電子メール メッセージ形式に変換し、アイテムをメールボックスに格納します。 サード パーティのデータをインポートした後、訴訟ホールド、電子情報開示、In-Place アーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をこのデータに適用できます。

> [!IMPORTANT]
> この[記事で](communication-compliance.md)説明Microsoft 365コネクタによってインポートされたサード パーティのデータには、通信コンプライアンス ソリューションを適用できません。

Microsoft パートナーと一緒にサード パーティのデータをインポートするために必要なプロセスと手順の概要を次に示します。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[手順 2: サード パーティ製のデータ メールボックスを作成して構成する](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[手順 4: パートナーに情報を提供する](#step-4-provide-your-partner-with-information)

[手順 5: サード パーティ製のデータ コネクタをデバイスに登録Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>サードパーティのデータのインポート プロセスが実行される方法

次の図と説明では、パートナーを操作するときにサード パーティのデータ インポート プロセスがどのように機能しているかについて説明します。

![サード パーティ製のデータインポート プロセスのしくみ。](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. お客様は、選択したパートナーと一緒に、サードパーティのデータ ソースからアイテムを抽出し、そのアイテムを外部にインポートするコネクタを構成Microsoft 365。

2. パートナー コネクタは、サード パーティ製 API を介して (スケジュールまたは構成済み) サードパーティ のデータ ソースに接続し、データ ソースからアイテムを抽出します。 パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。 メッセージ形式 [スキーマの説明](#more-information) については、「詳細」セクションを参照してください。

3. パートナー コネクタは、既知のエンド Microsoft 365経由で Exchange Web サービス (EWS) を使用して、Azure サービスに接続します。

4. アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。

   1. **ユーザー アカウントに対応するユーザー ID を持つアイテム。** パートナー コネクタがサードパーティ データ ソース内のアイテムのユーザー ID を Microsoft 365 の特定のユーザー ID にマップできる場合、そのアイテムはユーザーの回復可能なアイテム フォルダーの **Purges** フォルダーにコピーされます。 ユーザーは Purges フォルダー内のアイテムにアクセスできません。 ただし、電子情報開示ツールを使用して、Purges フォルダー内のアイテムを検索できます。

   1. **ユーザー アカウントに対応するユーザー ID を持** つアイテム:パートナー コネクタがアイテムのユーザー ID を特定のユーザー ID にマップできない場合、そのアイテムはサードパーティのデータ メールボックスの **受信** トレイ フォルダーにコピーされます。 アイテムを受信トレイにインポートすると、自分または組織内の誰かがサード パーティのメールボックスにサインインして、これらのアイテムを表示および管理し、パートナー コネクタ構成で調整が必要な場合に確認できます。

## <a name="step-1-find-a-third-party-data-partner"></a>手順 1: サード パーティのデータのパートナーを見つける

Microsoft 365 でサード パーティのデータをアーカイブするための重要なコンポーネントは、サード パーティのデータ ソースからのデータのキャプチャと Microsoft 365 へのインポートに特化した Microsoft パートナーの検索と操作です。 データをインポートした後、Exchange からのメールや SharePoint および OneDrive for Business からのドキュメントなど、組織の他の Microsoft データと共にアーカイブおよび保存できます。 パートナーは、組織のサードパーティデータ ソース (BlackBerry、Facebook、Google+、トムソン ロイター、Twitter、YouTube など) からデータを抽出するコネクタを作成し、そのデータを Microsoft 365 API に渡して、アイテムを Exchange メールボックスに電子メール メッセージとしてインポートします。

次のセクションでは、microsoft パートナー (およびサポートしているサード パーティのデータ ソース) を一覧表示します。このプログラムは、Microsoft 365 でサード パーティのデータをアーカイブするプログラムに参加しています。

[17a-4 LLC](#17a-4-llc)

[ArchiveSocial](#archivesocial)

[Veritas](#veritas)

[OpenText](#opentext)

[Smarsh](#smarsh)

[Verba](#verba)

### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC では](https://www.17a-4.com) 、次のサード パーティ製データ ソースがサポートされています。

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

[ArchiveSocial は](https://www.archivesocial.com) 、次のサード パーティ製データ ソースをサポートしています。

- Facebook

- Flickr

- Instagram

- LinkedIn

- Pinterest

- Twitter

- YouTube

- Vimeo

### <a name="veritas"></a>Veritas

[Veritas は](https://www.globanet.com) 、次のサード パーティ製データ ソースをサポートしています。

- AOL with Pivot クライアント

- BlackBerry 呼び出しログ (v5、v10、v12)

- BlackBerry メッセンジャー (v5、v10、v12)

- BlackBerry PIN (v5、v10、v12)

- BlackBerry SMS (v5、v10、v12)

- Bloomberg チャット

- Bloomberg メール

- Box

- CipherCloud for Salesforce Chatter

- Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- カスタム区切りテキスト ファイル

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

[OpenText は](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) 、次のサード パーティ製データ ソースをサポートしています。

- Axs Encrypted

- Axs Exchange

- Axs Local Archive

- Axs PlaceHolder

- Axs Signed

- ブルームバーグ

- Thomson Reuters

### <a name="smarsh"></a>Smarsh

[Smarsh は](https://www.smarsh.com) 、次のサード パーティ製データ ソースをサポートしています。

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

- Cisco IM &amp; Presence Server (v9.0.1、v9.1、v9.1.1 SU1、v10、v10.5.1 SU1)

- Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)

- 共同作業のインポート

- 共同作業のリアルタイム ロギング

- Direct Connect

- Facebook

- FactSet

- FastTrack

- Gnutella

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

- MSN

- My Space

- NEONetwork

- Microsoft 365Lync 専用

- Microsoft 365共有 IM

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

[Verba](https://www.verba.com) は、次のサード パーティ製データ ソースをサポートしています。

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

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>手順 2: サード パーティ製のデータ メールボックスを作成して構成Microsoft 365

データを外部にインポートするためのサード パーティ製のデータ メールボックスを作成および構成する手順をMicrosoft 365。 前に説明したように、パートナー コネクタがアイテムのユーザー ID をユーザー アカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。

 **これらのタスクは、次の手順で実行Microsoft 365 管理センター**

1. ユーザー アカウントを作成し、プラン 2 ライセンスExchange Online割り当てる。「ユーザー[をユーザーに追加する」をMicrosoft 365。](../admin/add-users/add-users.md) 訴訟ホールドにメールボックスを配置するか、無制限の記憶域クォータを持つアーカイブ メールボックスを有効にするには、プラン 2 ライセンスが必要です。

2. サード パーティのデータ メールボックスのユーザー アカウントを、管理者の管理者Exchange役割に追加Microsoft 365。「管理者[ロールの割り当て」を参照Microsoft 365。](../admin/add-users/assign-admin-roles.md)

    > [!TIP]
    > このユーザー アカウントの資格情報を控えておきます。手順 4 で説明するように、この情報をパートナーに提供する必要があります。

 **管理センターでこれらのタスクExchange実行する**

1. 組織内のアドレス帳や他のアドレス一覧からサード パーティのデータ メールボックスを非表示にします。「ユーザー [メールボックスの管理」を参照してください](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)。 または、次の PowerShell コマンドを実行することもできます。

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 管理者またはコンプライアンス担当者がデスクトップ クライアントでサード パーティのデータ メールボックスを開くことができるので、サード パーティのデータ メールボックスに **FullAccess** アクセス許可を割り当Outlookします。「受信者 [のアクセス許可の管理」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=692104)。

3. サード パーティのデータ メールボックスに対して、次のコンプライアンス関連の機能を有効にします。

    - アーカイブ メールボックスを有効にします。「アーカイブ[メールボックスを有効にする」および「](enable-archive-mailboxes.md)[無制限のアーカイブを有効にする」を参照してください](enable-unlimited-archiving.md)。 これにより、サード パーティのデータ アイテムをアーカイブ メールボックスに移動するアーカイブ ポリシーを設定することで、プライマリ メールボックスの記憶域を解放できます。 これにより、サードパーティのデータに対する無制限のストレージが提供されます。

    - サードパーティ データのメールボックスを訴訟ホールドの対象にします。 セキュリティとコンプライアンス センター Microsoft 365保持ポリシーを適用できます。 このメールボックスを保留に設定すると、サード パーティのデータ アイテム (無期限または指定された期間) が保持され、メールボックスから削除されません。 次のいずれかのトピックを参照してください。

      - [メールボックスを訴訟ホールドの対象にする](./create-a-litigation-hold.md)

      - [アイテム保持ポリシーと保持ラベルの詳細](retention.md)

    - 所有者、代理人、および第三者データ メールボックスへの管理者アクセスのメールボックス監査ログを有効にします。「 [メールボックス監査を有効にする」を参照してください](enable-mailbox-auditing.md)。 これにより、サード パーティのデータ メールボックスにアクセスできるすべてのユーザーが実行するアクティビティを監査できます。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する

次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。 これらのタスクは、管理センター Exchange、または対応するコマンドレットを使用してWindows PowerShellします。

1. 各ユーザーのアーカイブ メールボックスを有効にします。「アーカイブ[メールボックスを有効にする」および「](enable-archive-mailboxes.md)[無制限のアーカイブを有効にする」を参照してください](enable-unlimited-archiving.md)。

2. ユーザー メールボックスを訴訟ホールドに配置するか、ユーザー保持ポリシー Microsoft 365適用します。次のいずれかのトピックを参照してください。

    - [メールボックスを訴訟ホールドの対象にする](./create-a-litigation-hold.md)

    - [アイテム保持ポリシーと保持ラベルの詳細](retention.md)

    前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。

## <a name="step-4-provide-your-partner-with-information"></a>手順 4: パートナーに情報を提供する

最後の手順は、パートナーに次の情報を提供し、ユーザー のメールボックスとサード パーティのデータ メールボックスにデータをインポートするために、組織に接続するためのコネクタを構成することです。

- Azure サービスへの接続に使用するエンドポイントは、次Microsoft 365。

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 手順 2 で作成Microsoft 365サード パーティ製のデータ メールボックスのサインイン資格情報 (ユーザー ID とパスワードを含む)。 パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>手順 5: サード パーティ製のデータ コネクタをデバイスに登録Azure Active Directory

2018 年 9 月 30 日から、Microsoft 365 の Azure サービスは Exchange Online で最新の認証を使用して、組織に接続してデータをインポートしようとするサードパーティのデータ コネクタの認証を開始します。 この変更の理由は、最新の認証は、前述のエンドポイントを使用して Azure サービスに接続するサード パーティ製コネクタの許可リストに基づいて、現在のメソッドよりもセキュリティが高いという点です。

新しい最新の認証方法を使用してサード パーティ製のデータ コネクタが Microsoft 365 に接続するには、組織内の管理者がコネクタを Azure Active Directory で信頼できるサービス アプリケーションとして登録する同意が必要です。 これは、アクセス許可要求を受け入れて、コネクタが組織内の組織のデータにアクセスAzure Active Directory。 この要求を受け入れると、サード パーティ製のデータ コネクタがエンタープライズ アプリケーションとして Azure Active Directoryサービス プリンシパルとして表されます。 同意プロセスの詳細については、「テナント管理者の同意  [」を参照してください](/skype-sdk/trusted-application-api/docs/tenantadminconsent)。

コネクタの登録要求にアクセスして承諾する手順を次に示します。

1. このページ [に移動し](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 、グローバル管理者の資格情報を使用してサインインします。

   次のダイアログ ボックスが表示されます。 キャレットを展開して、コネクタに割り当てられるアクセス許可を確認できます。

   ![[アクセス許可の要求] ダイアログが表示されます。](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. [**Accept**] をクリックします。

要求に同意すると [、Azure ポータルが](https://portal.azure.com) 表示されます。 組織のアプリケーションの一覧を表示するには、[アプリケーション]をクリック  >  **Azure Active Directory Enterpriseクリックします**。 サード Microsoft 365 データ コネクタの一覧は、[アプリケーション] ブレードEnterprise **一覧表示** されます。

> [!IMPORTANT]
> 2018 年 9 月 30 日以降、サード パーティ製データ コネクタを Azure Active Directory に登録しない場合、サードパーティのデータは組織内のメールボックスにインポートされなくなりました。 既存のサード パーティ製データ コネクタ (2018 年 9 月 30 日より前に作成されたコネクタ) も、手順 5 の手順に従って Azure Active Directory に登録する必要があります。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>サード パーティ製データ コネクタに対する同意の取り下

組織が Azure Active Directory にサード パーティのデータ コネクタを登録するためのアクセス許可要求に同意した後、組織はいつでもその同意を取り消す可能性があります。 ただし、コネクタの同意を取り戻すということは、サード パーティ製のデータ ソースからのデータがデータ ソースにインポートされなくなるMicrosoft 365。

サード パーティのデータ コネクタの同意を取り消す場合は、Azure portal の **Enterprise** アプリケーション ブレードを使用するか、Microsoft 365 PowerShell の [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal)を使用して、Azure Active Directory から (対応するサービス プリンシパルを削除して) アプリケーションを削除できます。 また、PowerShell で[Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal)コマンドレットAzure Active Directoryできます。

## <a name="more-information"></a>詳細情報

- 前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。 パートナー コネクタは、API で必要なスキーマを使用してアイテムMicrosoft 365します。 次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。 この表では、メッセージのプロパティが必須かどうかも示します。 必須プロパティは設定されている必要があります。 アイテムに必須プロパティが存在しない場合、アイテムは必須プロパティにインポートMicrosoft 365。 インポート プロセスは、アイテムがインポートされていない理由と、不足しているプロパティを説明するエラー メッセージを返します。<br/><br/>

    |**メッセージのプロパティ**|**必須かどうか?**|**説明**|**値の例**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |はい  <br/> |最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。 パートナー コネクタは、ソース アイテム (Twitter ハンドルなど) からすべての参加者 (FROM フィールドと TO フィールドのユーザー) のユーザー アカウントにユーザー ID をマップします。 メッセージのコピーが、すべての参加者のメールボックスにインポートされます。 アイテムの参加者のいずれもユーザー アカウントにマップしない場合、アイテムはユーザー アカウント内のサード パーティのアーカイブ メールボックスにインポートMicrosoft 365。  <br/> <br/> アイテムの送信者として識別される参加者は、アイテムのインポート先である組織内のアクティブなメールボックスを持っている必要があります。 送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |はい  <br/> |アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。  <br/> | `bob@contoso.com` <br/> |
    |**件名** <br/> |いいえ  <br/> |ソース アイテムの件名。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |はい  <br/> |アイテムが最初に作成または顧客データ ソースに投稿された日付。 たとえば、Twitter メッセージがツイートされた日付です。  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |いいえ  <br/> |メッセージまたは投稿のコンテンツ。 一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。 インポート プロセス中、パートナー コネクタはコンテンツ ソースからの完全な忠実度を可能な限り維持します。 可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。 それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。 このプロパティの内容は、パートナー コネクタとソース プラットフォームの機能によって異なります。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |いいえ  <br/> |データ ソース内のアイテム (Twitter でのツイートやインスタント メッセージング会話など) に添付ファイルまたは画像が含まれる場合、パートナー接続はまず **BODY** プロパティに添付ファイルを含める試みを行います。 それができない場合は、 ** ATTACHMENT ** プロパティに追加されます。 添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |はい  <br/> | これは複数値のプロパティで、パートナー コネクタによって作成および設定されます。 このプロパティの形式はです  `IPM.NOTE.Source.Event` 。 (このプロパティはで始まる必要があります  `IPM.NOTE` 。 この形式は、メッセージ クラスの形式と  `IPM.NOTE.X` 似ています)。このプロパティには、次の情報が含まれています。  <br/><br/>`Source`: サードパーティのデータ ソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。  <br/> <br/>  `Event`: アイテムを生成したサードパーティのデータ ソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイートや Facebook の投稿などです。 イベントはデータ ソースに固有です。  <br/> <br/>  このプロパティの目的の 1 つは、アイテムが発生したデータ ソースに基づいて、またはイベントの種類に基づいて特定のアイテムをフィルター処理することです。 たとえば、電子情報開示検索で検索クエリを作成して、特定のユーザーが投稿したツイートを検索できます。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- アイテムが Microsoft 365 内のメールボックスに正常にインポートされると、HTTP 応答の一部として一意の識別子が呼び出し元に返されます。 この識別子 (呼び出し) は、アイテムのエンドツーエンドの追跡のためにパートナーが後続のトラブルシューティングの目的  `x-IngestionCorrelationID` で使用できます。 パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。 この識別子を示す HTTP 応答の例を以下に示します。

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT
    ```

- セキュリティとコンプライアンス センターのコンテンツ検索ツールを使用して、サード パーティのデータ ソースからメールボックスにインポートされたアイテムを検索できます。 これらのインポートされたアイテムを具体的に検索するには、コンテンツ検索のキーワード ボックスで次のメッセージ プロパティと値のペアを使用できます。

  - **`kind:externaldata`**: このプロパティと値のペアを使用して、すべてのサード パーティのデータ型を検索します。 たとえば、サードパーティのデータ ソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、キーワード クエリを使用します  `kind:externaldata AND subject:contoso` 。

  - **`itemclass:ipm.externaldata.<third-party data type>`**: このプロパティと値のペアを使用して、指定した種類のサード パーティデータのみを検索します。 たとえば、Subject プロパティの "contoso" という単語を含む Facebook データのみを検索するには、キーワード クエリを使用します  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 。

  プロパティのサード パーティのデータ型に使用する値の完全な一覧については、「コンテンツ検索を使用して、このプロパティにインポートされたサード パーティのデータを検索する」 `itemclass` [を参照Microsoft 365。](use-content-search-to-search-third-party-data-that-was-imported.md)

   コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。

  - [コンテンツ検索](content-search.md)

  - [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)