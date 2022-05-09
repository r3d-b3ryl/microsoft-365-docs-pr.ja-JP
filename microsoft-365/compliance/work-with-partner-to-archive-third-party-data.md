---
title: パートナーと共同作業して、サード パーティのデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: Salesforce Chatter、Yahoo Messenger、Yammerなどのデータ ソースからサード パーティのデータをインポートするようにカスタム コネクタを設定する方法について説明します。
ms.openlocfilehash: f0de03fb68b78779b6d1ed057a8b462c5c2a901b
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097560"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>パートナーと共同作業して、サード パーティのデータをアーカイブする

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft パートナーと協力して、サード パーティのデータ ソースからMicrosoft 365にデータをインポートおよびアーカイブできます。 パートナーは、(定期的に) サード パーティのデータ ソースからアイテムを抽出し、それらの項目をインポートするように構成されたカスタム コネクタを提供できます。 パートナー コネクタは、アイテムのコンテンツをデータ ソースから電子メール メッセージ形式に変換し、アイテムをメールボックスに格納します。 サード パーティのデータがインポートされたら、訴訟ホールド、電子情報開示、In-Placeアーカイブ、監査、Microsoft 365保持ポリシーなどの Microsoft Purview 機能をこのデータに適用できます。

> [!IMPORTANT]
> Microsoft 365の [Communication コンプライアンス](communication-compliance.md) ソリューションは、この記事で説明したパートナー コネクタによってインポートされたサード パーティのデータには適用できません。

プロセスの概要と、サード パーティのデータをインポートするために Microsoft パートナーと連携するために必要な手順を次に示します。

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[手順 2: サード パーティのデータ メールボックスを作成して構成する](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[手順 4: パートナーに情報を提供する](#step-4-provide-your-partner-with-information)

[手順 5: サードパーティのデータ コネクタをAzure Active Directoryに登録する](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>サードパーティのデータのインポート プロセスが実行される方法

次の図と説明は、パートナーと連携する際のサード パーティのデータインポート プロセスのしくみを説明しています。

![サード パーティのデータインポート プロセスのしくみ。](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. 顧客は、選択したパートナーと協力して、サード パーティのデータ ソースからアイテムを抽出し、それらの項目をMicrosoft 365にインポートするコネクタを構成します。

2. パートナー コネクタは、サード パーティ API を使用してサード パーティのデータ ソースに接続し (スケジュールまたは構成済みベースで) データ ソースから項目を抽出します。 パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。 メッセージ形式スキーマの説明については、「 [詳細情報](#more-information) 」セクションを参照してください。

3. パートナー コネクタは、既知のエンドポイント経由で Exchange Web サービス (EWS) を使用して、Microsoft 365の Azure サービスに接続します。

4. アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。

   1. **ユーザー アカウントに対応するユーザー ID を持つアイテム:** パートナー コネクタがサード パーティのデータ ソース内のアイテムのユーザー ID をMicrosoft 365の特定のユーザー ID にマップできる場合、アイテムはユーザーの回復可能なアイテム フォルダーの **Purges** フォルダーにコピーされます。 ユーザーは Purges フォルダー内のアイテムにアクセスできません。 ただし、電子情報開示ツールを使用して、Purges フォルダー内のアイテムを検索できます。

   1. **ユーザー アカウントに対応するユーザー ID を持たない項目:** パートナー コネクタがアイテムのユーザー ID を特定のユーザー ID にマップできない場合、そのアイテムはサード パーティのデータ メールボックスの **受信トレイ** フォルダーにコピーされます。 受信トレイにアイテムをインポートすると、自分または組織内の他のユーザーがサード パーティのメールボックスにサインインしてこれらのアイテムを表示および管理し、パートナー コネクタ構成で調整が必要かどうかを確認できます。

## <a name="step-1-find-a-third-party-data-partner"></a>手順 1: サード パーティのデータのパートナーを見つける

Microsoft 365でサード パーティのデータをアーカイブするための重要なコンポーネントは、サード パーティのデータ ソースからデータをキャプチャし、それをMicrosoft 365にインポートすることに特化した Microsoft パートナーを見つけて操作することです。 データをインポートした後は、組織の他の Microsoft データ (ExchangeからのメールやSharePointやOneDrive for Businessからのドキュメントなど) と共にアーカイブおよび保持できます。 パートナーは、組織のサードパーティのデータ ソース (BlackBerry、Facebook、Google+、トムソン ロイター、Twitter、YouTube など) からデータを抽出し、そのデータをメール メッセージとしてExchangeメールボックスにインポートするMicrosoft 365 API に渡すコネクタを作成します。

次のセクションでは、Microsoft 365でサード パーティのデータをアーカイブするためのプログラムに参加している Microsoft パートナー (およびサポートしているサード パーティのデータ ソース) の一覧を示します。

[17a-4 LLC](#17a-4-llc)

[ArchiveSocial](#archivesocial)

[Veritas](#veritas)

[OpenText](#opentext)

[Smarsh](#smarsh)

[バーバ](#verba)

### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC](https://www.17a-4.com) では、次のサード パーティのデータ ソースがサポートされます。

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

[ArchiveSocial では](https://www.archivesocial.com) 、次のサード パーティのデータ ソースがサポートされています。

- Facebook

- Flickr

- Instagram

- LinkedIn

- Pinterest

- Twitter

- YouTube

- Vimeo

### <a name="veritas"></a>Veritas

[Veritas では、](https://www.globanet.com) 次のサード パーティのデータ ソースがサポートされています。

- AOL with Pivot クライアント

- BlackBerry 呼び出しログ (v5、v10、v12)

- BlackBerry メッセンジャー (v5、v10、v12)

- BlackBerry PIN (v5、v10、v12)

- BlackBerry SMS (v5、v10、v12)

- Bloomberg チャット

- Bloomberg メール

- 検索ボックス

- CipherCloud for Salesforce Chatter

- Cisco IM &amp; Presence Server (v10、v10.5.1 SU1、v11.0、v11.5 SU2)

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- カスタム区切りテキスト ファイル

- カスタムの XML ファイル

- Facebook (Pages)

- ファクトセット

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

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) では、次のサード パーティのデータ ソースがサポートされています。

- Axs Encrypted

- Axs Exchange

- Axs Local Archive

- Axs PlaceHolder

- Axs Signed

- ブルームバーグ

- Thomson Reuters

### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com) では、次のサード パーティのデータ ソースがサポートされています。

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

- おしゃべり

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

- Gotomypc

- ホップスター

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

- Microsoft 365 Lync Dedicated

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

- Winmx

- Winny

- Yahoo

- Yammer

- YouTube


### <a name="verba"></a>バーバ

[Verba](https://www.verba.com) では、次のサード パーティのデータ ソースがサポートされています。

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

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>手順 2: Microsoft 365でサード パーティのデータ メールボックスを作成して構成する

Microsoft 365にデータをインポートするためのサード パーティ製のデータ メールボックスを作成して構成する手順を次に示します。 前述のように、パートナー コネクタがアイテムのユーザー ID をユーザー アカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。

 **Microsoft 365 管理センターでこれらのタスクを完了する**

1. ユーザー アカウントを作成し、プラン 2 ライセンスExchange Online割り当てます。[「Microsoft 365にユーザーを追加する」を](../admin/add-users/add-users.md)参照してください。 メールボックスを訴訟ホールドにするか、最大 1.5 TB のストレージ クォータを持つアーカイブ メールボックスを有効にするには、プラン 2 ライセンスが必要です。

2. サード パーティのデータ メールボックスのユーザー アカウントを **Microsoft 365のExchange管理者** 管理者ロールに追加します。「Microsoft 365 [で管理者ロールを割り当てる](../admin/add-users/assign-admin-roles.md)」を参照してください。

    > [!TIP]
    > このユーザー アカウントの資格情報を控えておきます。手順 4 で説明するように、この情報をパートナーに提供する必要があります。

 **Exchange管理センターでこれらのタスクを完了する**

1. 組織内のアドレス帳やその他のアドレス一覧からサード パーティのデータ メールボックスを非表示にします。 [ユーザー メールボックスの管理に関するページを](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)参照してください。 または、次の PowerShell コマンドを実行することもできます。

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. 管理者またはコンプライアンス担当者がOutlook デスクトップ クライアントでサード パーティのデータ メールボックスを開くことができるように、サード パーティのデータ メールボックスに **FullAccess** アクセス許可を割り当てます。[受信者のアクセス許可の管理に関するページを](https://go.microsoft.com/fwlink/p/?LinkId=692104)参照してください。

3. サード パーティのデータ メールボックスに対して、次のコンプライアンス関連機能を有効にします。

    - アーカイブ メールボックスを有効にします。 [「アーカイブ メールボックスを有効にする」](enable-archive-mailboxes.md) および「 [自動展開アーカイブを有効にする](enable-autoexpanding-archiving.md)」を参照してください。 これにより、サード パーティのデータ項目をアーカイブ メールボックスに移動するアーカイブ ポリシーを設定することで、プライマリ メールボックスのストレージ領域を解放できます。 これにより、サード パーティのデータに最大 1.5 TB のストレージが提供されます。

    - サードパーティ データのメールボックスを訴訟ホールドの対象にします。 セキュリティとコンプライアンス センターでMicrosoft 365アイテム保持ポリシーを適用することもできます。 このメールボックスを保留にすると、サード パーティのデータアイテムが (無期限または指定された期間) 保持され、メールボックスから削除されなくなります。 次のいずれかのトピックを参照してください。

      - [メールボックスを訴訟ホールドの対象にする](./create-a-litigation-hold.md)

      - [アイテム保持ポリシーと保持ラベルの詳細](retention.md)

    - サード パーティのデータ メールボックスに対する所有者、代理人、管理者アクセスのメールボックス監査ログを有効にします。 [「メールボックス監査を有効にする」を](enable-mailbox-auditing.md)参照してください。 これにより、サード パーティのデータ メールボックスにアクセスできるユーザーが実行するすべてのアクティビティを監査できます。

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する

次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。 これらのタスクは、<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>を使用するか、対応するWindows PowerShell コマンドレットを使用して実行します。

1. 各ユーザーのアーカイブ メールボックスを有効にします。 [「アーカイブ メールボックスを有効にする」](enable-archive-mailboxes.md) および「 [自動展開アーカイブを有効にする](enable-autoexpanding-archiving.md)」を参照してください。

2. 訴訟ホールドにユーザー メールボックスを配置するか、Microsoft 365アイテム保持ポリシーを適用します。次のいずれかのトピックを参照してください。

    - [メールボックスを訴訟ホールドの対象にする](./create-a-litigation-hold.md)

    - [アイテム保持ポリシーと保持ラベルの詳細](retention.md)

    前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。

## <a name="step-4-provide-your-partner-with-information"></a>手順 4: パートナーに情報を提供する

最後の手順は、ユーザー メールボックスとサード パーティのデータ メールボックスにデータをインポートするために組織に接続するようにコネクタを構成できるように、パートナーに次の情報を提供することです。

- Microsoft 365で Azure サービスに接続するために使用されるエンドポイント:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- 手順 2. で作成したサード パーティ製のデータ メールボックスのサインイン資格情報 (ユーザー ID とパスワードをMicrosoft 365します)。 パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>手順 5: サードパーティのデータ コネクタをAzure Active Directoryに登録する

2018 年 9 月 30 日から、Microsoft 365 の Azure サービスは、Exchange Onlineで最新の認証を使用して、組織に接続してデータをインポートしようとするサードパーティのデータ コネクタを認証し始めます。 この変更の理由は、先進認証は、前述のエンドポイントを使用して Azure サービスに接続するサード パーティコネクタの許可リストに基づく、現在の方法よりもセキュリティが高いからです。

新しい最新の認証方法を使用してサード パーティのデータ コネクタがMicrosoft 365に接続できるようにするには、組織内の管理者がコネクタを信頼されたサービス アプリケーションとしてAzure Active Directoryに登録することに同意する必要があります。 これは、コネクタがAzure Active Directory内の組織のデータにアクセスできるようにするアクセス許可要求を受け入れることによって行われます。 この要求を受け入れた後、サード パーティのデータ コネクタがエンタープライズ アプリケーションとしてAzure Active Directoryに追加され、サービス プリンシパルとして表されます。 同意プロセスの詳細については、「  [テナント管理者の同意」を](/skype-sdk/trusted-application-api/docs/tenantadminconsent)参照してください。

コネクタを登録する要求にアクセスして受け入れる手順を次に示します。

1. [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動し、グローバル管理者の資格情報を使用してサインインします。

   次のダイアログ ボックスが表示されます。 キャレットを展開して、コネクタに割り当てられるアクセス許可を確認できます。

   ![アクセス許可要求ダイアログが表示されます。](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. [**Accept**] をクリックします。

要求を受け入れた後、[Azure portal](https://portal.azure.com)が表示されます。 組織のアプリケーションの一覧を表示するには、[**Azure Active Directory** >  **Enterprise アプリケーション**] をクリックします。 Microsoft 365サード パーティのデータ コネクタは、[**Enterprise アプリケーション**] ブレードに一覧表示されます。

> [!IMPORTANT]
> 2018 年 9 月 30 日以降、サード パーティのデータ コネクタをAzure Active Directoryに登録しないと、サード パーティのデータは組織内のメールボックスにインポートされなくなります。 既存のサード パーティ製データ コネクタ (2018 年 9 月 30 日より前に作成されたもの) も、手順 5 の手順に従ってAzure Active Directoryに登録する必要があることに注意してください。

### <a name="revoking-consent-for-a-third-party-data-connector"></a>サード パーティのデータ コネクタの同意を取り消す

組織がサード パーティのデータ コネクタをAzure Active Directoryに登録するためのアクセス許可要求に同意した後、組織はいつでもその同意を取り消すことができます。 ただし、コネクタの同意を取り消すと、サード パーティのデータ ソースからのデータはMicrosoft 365にインポートされなくなります。

サード パーティのデータ コネクタの同意を取り消すには、Azure portalの [Enterprise **アプリケーション**] ブレードを使用するか、Microsoft 365で [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) を使用して、アプリケーションを (対応するサービス プリンシパルを削除して) Azure Active Directoryから削除します。Powershell。 また、PowerShell で [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) コマンドレットAzure Active Directory使用することもできます。

## <a name="more-information"></a>詳細情報

- 前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。 パートナー コネクタは、Microsoft 365 API で必要なスキーマを使用してアイテムをインポートします。 次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。 この表では、メッセージのプロパティが必須かどうかも示します。 必須プロパティは設定されている必要があります。 必須プロパティがないアイテムは、Microsoft 365にインポートされません。 インポート プロセスは、アイテムがインポートされなかった理由と、どのプロパティが見つからないかを説明するエラー メッセージを返します。<br/><br/>

    |**メッセージのプロパティ**|**必須かどうか?**|**説明**|**値の例**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |はい  <br/> |最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。 パートナー コネクタは、ソース アイテム (Twitter ハンドルなど) からすべての参加者 (FROM フィールドと TO フィールドのユーザー) のユーザー アカウントにユーザー ID をマップしようとします。 メッセージのコピーが、すべての参加者のメールボックスにインポートされます。 アイテムの参加者のいずれもユーザー アカウントにマップできない場合、アイテムはMicrosoft 365のサード パーティのアーカイブ メールボックスにインポートされます。  <br/> <br/> アイテムの送信者として識別された参加者には、アイテムのインポート先となる組織内のアクティブなメールボックスが必要です。 送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |はい  <br/> |アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。  <br/> | `bob@contoso.com` <br/> |
    |**件名** <br/> |いいえ  <br/> |ソース アイテムの件名。  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |はい  <br/> |顧客データ ソースでアイテムが最初に作成または投稿された日付。 たとえば、Twitter メッセージがツイートされた日付です。  <br/> | `01 NOV 2015` <br/> |
    |**体** <br/> |いいえ  <br/> |メッセージまたは投稿のコンテンツ。 一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。 インポート プロセス中、パートナー コネクタはコンテンツ ソースからの完全な忠実性を可能な限り維持しようとします。 可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。 それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。 このプロパティの内容は、パートナー コネクタとソース プラットフォームの機能によって異なります。  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**添付 ファイル** <br/> |いいえ  <br/> |データ ソース内のアイテム (Twitter のツイートやインスタント メッセージング会話など) に添付ファイルがある場合、または画像を含める場合、パートナーの接続は最初に **BODY** プロパティに添付ファイルを含めようとします。 それが不可能な場合は、** ATTACHMENT ** プロパティに追加されます。 添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |はい  <br/> | これは、パートナー コネクタによって作成および設定される複数値プロパティです。 このプロパティの形式は  `IPM.NOTE.Source.Event`. (このプロパティは、 で始まる  `IPM.NOTE`必要があります。 この形式は、メッセージ クラスの形式に  `IPM.NOTE.X` 似ています)。このプロパティには、次の情報が含まれます。  <br/><br/>`Source`: サード パーティのデータ ソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。  <br/> <br/>  `Event`: 項目を生成したサード パーティのデータ ソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイートや Facebook の投稿などです。 イベントはデータ ソースに固有です。  <br/> <br/>  このプロパティの目的の 1 つは、アイテムが発生したデータ ソースに基づいて、またはイベントの種類に基づいて特定の項目をフィルター処理することです。 たとえば、電子情報開示検索では、特定のユーザーによって投稿されたすべてのツイートを検索する検索クエリを作成できます。  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- アイテムがMicrosoft 365のメールボックスに正常にインポートされると、HTTP 応答の一部として一意の識別子が呼び出し元に返されます。 この識別子 (呼び出し)  `x-IngestionCorrelationID`は、アイテムのエンド ツー エンドの追跡にパートナーが後続のトラブルシューティングを行うために使用できます。 パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。 この識別子を示す HTTP 応答の例を以下に示します。

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

  - **`kind:externaldata`**: このプロパティと値のペアを使用して、すべてのサード パーティのデータ型を検索します。 たとえば、サード パーティのデータ ソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、キーワード クエリを使用します  `kind:externaldata AND subject:contoso`。

  - **`itemclass:ipm.externaldata.<third-party data type>`**: このプロパティと値のペアを使用して、指定した種類のサード パーティのデータのみを検索します。 たとえば、Subject プロパティで "contoso" という単語を含む Facebook データのみを検索するには、キーワード クエリを使用します  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`。

  プロパティのサード パーティのデータ型に使用する値の完全な`itemclass`一覧については、「[コンテンツ検索を使用して、Microsoft 365にインポートされたサード パーティのデータを検索する」を](use-content-search-to-search-third-party-data-that-was-imported.md)参照してください。

   コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。

  - [コンテンツ検索](content-search.md)

  - [コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)