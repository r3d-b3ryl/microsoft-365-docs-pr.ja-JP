---
title: Microsoft Cloud Deutschland からの移行の移行前アクティビティ
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域のOffice 365サービスに移行する場合の事前作業。'
ms.openlocfilehash: 8d2f33f7bd574610980e64c4da769f3418042bc302c1a5d33d081ceeeebfd4a9
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53899009"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行の移行前アクティビティ

これらのリンクを使用して、組織に関連する移行前の手順に移動します。

使用している場合

- **Office 365で、次の** 手順を [実行します](#general-tenant-migration-considerations)。
- **カスタム ドメインは、** この [手順を実行します](#dns-entries-for-custom-domains)。
- **Officeアプリの場合** は、この [手順を検討してください](#office-apps)。
- **SharePointオンラインで**、この [手順を実行します](#sharepoint-online)。
- **Exchange Online** またはハイブリッド **Exchange、** この手順 [を実行します](#exchange-online)。
- **Skype for Businessオンラインで**、この [手順を実行します](#skype-for-business-online)。
- **Dynamics 365 は**、この手順 [を実行します](#dynamics-365)。
- **Power BI、** この手順 [を実行します](#power-bi)。
- **Active Directory フェデレーション サービス** for Azure AD Connect、次の手順 [を実行します](#active-directory-federation-services-ad-fs)。
- **サード パーティのサービス** またはビジネスライン **(LOB)** アプリは、Office 365 [手順を実行します](#line-of-business-apps)。
- サードパーティのモバイル デバイス管理 (MDM) ソリューションで、この手順 [を実行します](#mobile-device-management)。
- **Azure サービスと** サブスクリプションOffice 365、この手順 [を実行します](#microsoft-azure)。

## <a name="general-tenant-migration-considerations"></a>テナントの移行に関する一般的な考慮事項

**適用対象:** Microsoft Deutschland Cloud インスタンスOffice 365を使用しているすべてのユーザー

Office 365ユーザー識別子は移行中に保持されます。 Azure ADサービス呼び出しは、Microsoft Cloud Deutschland からグローバル サービスOffice 365にリダイレクトされ、特定のサービスOffice 365されません。

- 一般的なデータ保護規則 (GDPR) データ主体要求 (DSR) は、Azure Admin ポータルから今後の要求のために実行されます。 Microsoft Cloud Deutschland に常駐している従来の診断データまたは顧客以外の診断データは、30 日以上経過した時点で削除されます。

- テナントがサービスにコピーされている間に、Microsoft Authenticatorをユーザー ObjectID (GUID) として表示する多要素認証 (MFA) 要求Office 365します。 MFA 要求は、この表示動作にもかかわらず期待通り実行されます。  Microsoft Authenticatorサービス エンドポイントを使用してアクティブ化Office 365アカウントには、ユーザー プリンシパル名 (UPN) が表示されます。  Microsoft Cloud Deutschland エンドポイントを使用して追加されたアカウントは、ユーザー ObjectID を表示しますが、Microsoft Cloud Deutschland エンドポイントと Office 365 サービス エンドポイントの両方で動作します。

<br>

****

|Step(s)|Description|影響|
|---|---|---|
|移行後にクライアントの再起動とサインインおよびクライアントへのサインインについてユーザーに通知する準備をします。|Officeクライアント ライセンスは、移行時に Microsoft Cloud Deutschland から Office 365サービスに移行します。 クライアントは、クライアントからサインインおよびサインインした後、新しい有効なライセンスをOfficeします。|ユーザーの製品Officeサービスからライセンスを更新するOffice 365があります。 ライセンスが更新されない場合、ライセンスOffice検証エラーが発生する可能性があります。|
|サービス URL と[IP アドレスOffice 365ネットワーク接続を確認します](https://aka.ms/o365urls)。|サービスへのアクセスに使用される顧客によってホストOffice 365サービスは、グローバル Office 365エンドポイントにアクセスできる必要があります。 <p> Office 365 サービスの URL と IP アドレスに記載されている URL と IP アドレスへのアクセスを妨げるファイアウォール ルールが設定されている場合は[、Office 365](https://aka.ms/o365urls) Global サービス エンドポイントへのアクセスを許可するファイアウォール ルールを変更する必要があります。|サービスまたはクライアント ソフトウェアの障害は、フェーズ 4 より前に実行されていない場合に発生する可能性があります。|
|試用版サブスクリプションをキャンセルします。|試用版サブスクリプションは移行されません。有料サブスクリプションの移行はブロックされます。|キャンセル後にユーザーがアクセスした場合、試用版サービスは期限切れであり、機能しません。|
|Microsoft Cloud Deutschland とグローバル サービスのライセンス機能Office 365分析します。|Office 365には、現在の Microsoft Cloud Deutschland では利用できない追加の機能とサービスが含まれます。 サブスクリプションの転送中に、新しい機能をユーザーが利用できます。|<ul><li>Microsoft Cloud Deutschland およびグローバル サービスのライセンスによって提供されるさまざまなOffice 365分析します。 最初に、Office 365[プラットフォームのサービスの説明を参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。</li><li>ユーザーまたはユーザーの変更管理への影響を制限し、必要に応じてユーザー ライセンスの割り当てを変更するために、Office 365 サービスの新機能を最初に無効にすべきかどうかを判断します。</li><li>ユーザーとヘルプ デスク のスタッフが、新しいサービスとサービスによって提供される機能をOffice 365します。</li></ul>|
|移行中にコンテンツ [が](/microsoft-365/compliance/retention) 不注意で削除されるのを回避するために、組織全体の保持ポリシーを作成します。|<ul><li>移行中にエンド ユーザーによってコンテンツが誤って削除されるのを回避するために、組織全体の保持ポリシーを有効にすることもできます。</li><li>保持は必要ありませんが、移行中はいつでも保持が期待通り動作する必要があります。保持ポリシーを持つことはバックアップの安全メカニズムです。 同時に、保持ポリシーは、すべての顧客、特に保存過多を懸念しているユーザーが使用する場合があります。</li></ul>|「アイテム保持ポリシーと保持ラベルについて」の [説明に従ってアイテム保持ポリシーを適用します](/microsoft-365/compliance/retention-policies)。 サービスまたはクライアント ソフトウェアの障害は、フェーズ 4 / 9 より前に行われない場合に発生する可能性があります。|


## <a name="dns-entries-for-custom-domains"></a>カスタム ドメインの DNS エントリ

<!-- before phase 9 -->

**適用対象**: カスタム _msoid_ CNAME を独自のユーザー設定で設定したDNS ドメインドメインを使用しているユーザー Exchange Online

構成されている場合 _、msoid_ CNAME は Office デスクトップ クライアント (Microsoft 365 Apps、Office 365 ProPlus、Office 2019、2016、..)を使用しているユーザーにのみ影響します。

所有する 1 つ以上の DNS 名前空間に _msoid_ という DNS CNAME を設定した場合は、最新のフェーズ 8 の終了まで CNAME を削除する必要があります。 フェーズ 8 の終了前にいつでも CNAME _msoid_ を削除できます。

DNS 名前空間で CNAME を設定した場合に確認するには、以下の手順に従い、contoso.com を独自 _のドメイン名_ に置き換える必要があります。

```console
nslookup -querytype=CNAME msoid.contoso.com
```

コマンド ラインが DNS レコードを返す場合は、ドメインから _msoid_ CNAME を削除します。

> [!NOTE]
> カスタム ドメインを使用している場合Exchange Online DNS ホスティング プロバイダーにアクセスする必要があります。 DNS 設定にアクセスして編集できる場合は、移行中に DNS レコードを変更します。

## <a name="office-apps"></a>Officeアプリ

**適用対象**: アプリを使用しているOffice、特にクライアントWindowsします。 <br>
**適用時**: フェーズ 9 が開始される前の任意の時間

Office 365 地域 "ドイツ" に移行するテナントでは、テナント移行がフェーズ 9 に達した後、すべての Office デスクトップ アプリケーション (Word、Excel、PowerPoint、Outlook など) および OneDrive for Business クライアントを閉じて、Office 365 からサインアウトし、戻す必要があります。 サインアウトしてサインインすると、Officeサービスは、グローバル Azure AD サービスから新しい認証トークンをADできます。

これは、すべてのクライアントに必要です。 スムーズな移行エクスペリエンスを実現するには、影響を受けるすべてのユーザーに、この今後のアクティビティについて事前に、また早期に通知し、指示を行う必要があります。

管理されたクライアントを使用Windowsは、Windows クライアント カットOffice [(OCCT)](https://github.com/microsoft/OCCT)を使用してコンピューターを準備できます。 OCCT は、テナントが移行のフェーズ 9 に達するまで、Windowsクライアントで定期的に実行するように設計されています。 フェーズ 9 に達すると、OCCT はユーザーの操作なしで自動的にコンピューター上で必要なすべての変更を実行します。

OCCT は、フェーズ 9 の前Windowsクライアントに展開できます。 OCCT が移行エクスペリエンスをサポートする場合は、できるだけ早く展開を開始し、最大数のクライアントを装備することをお勧めします。

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory フェデレーション サービス (AD FS)

**適用対象**: オンプレミスの FS ADを使用して、ユーザーに接続するユーザーを認証Microsoft Office 365<br>
**適用時**: フェーズ 2 が開始される前の任意の時間

[ADFS 移行手順の読み取りと適用](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

**適用対象 :** 2013 SharePointオンプレミスを使用しているお客様<br>
**適用時**: フェーズ 4 が開始される前の任意の時間

<br>

****

|Step(s)|Description|影響|
|---|---|---|
|2013 SharePointを制限し、オンライン移行のSharePoint使用します。|2013 SharePointを削減し、移行前にインフライト ワークフローを完了します。|不作為により、ユーザーの混乱やヘルプ デスクの呼び出しが発生する可能性があります。| 
変更SharePoint場合は、検索構成をエクスポートします。 |検索SharePoint構成は移行されません。 検索に変更がSharePoint場合は、変更に注意し、検索構成をエクスポートしてください。 設定は、移行が完了した後SharePointインポートする必要があります。|変更された検索スキーマに基づくカスタム ソリューションは、検索の変更が再適用されるまで使用できません。|


## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**適用対象**: Exchange Online顧客<br>
**適用時**: フェーズ 9 の終了前の任意の時間

<br>

****

|Step(s)|Description|影響|
|---|---|---|
|今後のサービスへの移行を外部パートナーに通知Office 365します。|お客様は、予定表と空き時間情報の共有を有効にしたパートナーに通知する必要があります (空き時間情報の共有を許可Office 365。 可用性の構成は、移行が完了したら、Office 365[の](/microsoft-365/enterprise/urls-and-ip-address-ranges)エンドポイントを使用Exchange Online移行する必要があります。|そうしない場合は、お客様の移行の後のフェーズでサービスまたはクライアントの障害が発生する可能性があります。|
|必要な IMAP4/POP3/SMTP クライアントの変更をユーザーに通知します。|クライアント プロトコル IMAP4、POP3、SMTP の Microsoft Cloud Deutschland エンドポイントへのデバイス接続を持つユーザーは、クライアント デバイスを手動で更新して、Exchange Online サーバー名に切[り](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes)替える必要があります。|この依存関係をこれらのプロトコルのユーザーに事前に伝え、この移行中にモバイルまたはOutlookを使用Outlook on the web切り替えます。 クライアント エンドポイントの更新に失敗すると、ユーザー メールボックスの移行時に Microsoft Cloud Deutschland に対するクライアント接続エラーが発生します。|


### <a name="exchange-online-hybrid-customers"></a>Exchange Onlineハイブリッドのお客様

**適用対象:** オンプレミスのサーバーでアクティブExchangeハイブリッド構成Exchange使用しているすべてのお客様<br>
**適用時**: フェーズ 5 が開始される前の任意の時間

Enterprise Exchange Online とオンプレミス Exchange Server のハイブリッド展開を使用しているお客様は、ハイブリッド構成ウィザード (HCW) と AAD Connect を実行して、ハイブリッドセットアップを維持および確立します。
Exchange Onlineハイブリッド管理者は、**この移行の一環としてハイブリッド構成ウィザード (HCW)** を複数回実行する必要があります。
Microsoft Cloud Deutschland から Office 365 ドイツ地域に移行する場合、管理者は Exchange 移行 (フェーズ 5) を開始する前に、"Office 365 Germany" モードで HCW の最新ビルドを再実行する必要があります。 次に、フェーズ 5 の完了時に "Office 365 Worldwide" モードでもう一度 HCW を実行し、Office 365ドイツ地域の設定でオンプレミス展開を終了します。 HCW の実行はフェーズ 5 の間は実行しない必要があります。フェーズ 5 が終了するまで HCW を実行することが重要です。
ディレクトリ属性は、Office 365 Azure AD AAD を介してオンプレミス展開と同期Connect。

<br>

**

|Step(s)|Description|影響|
|---|---|---|
|ドイツの設定を使用して HCW Office 365実行する <p> _テナントの移行が開始されたというメッセージ センター通知を受け取った直後に、このOffice 365を開始できます (フェーズ 1)。_|フェーズ 5 より前から HCW (17.0.5378.0 以上) をアンインストールおよび再実行すると、Microsoft Cloud Deutschland ユーザーと Office 365 ドイツ地域に移行されたユーザーの両方との間で、オンプレミス構成でメールの送受信を行う準備が完了します。 <https://aka.ms/hybridwizard> <p> HCW で、[自分の組織がホストOffice 365 **下** のリスト ボックスで、[ドイツ] をOffice 365 **します。**|フェーズ 5 [Exchange 移行] が開始する前にこのタスクを完了できなかった場合、オンプレミスの展開と Office 365 の間でメールの NDRs がルーティングされるExchange可能性があります。|
|共有メールボックスの設定を保持する|ハイブリッドのお客様の中には、クラウド ユーザー メールボックスを、ユーザー コマンドを使用して 「共有」 Exchange Onlineしています。 このクラウド メールボックス構成はメールボックスとローカル Exchange Online ディレクトリに書き込まれますが、AAD サーバー経由で顧客の Active Directory に同期Connect。 その結果、メールボックス RemoteRecipientType 値と RemoteDisplayType 値の Active Directory 表記と、メールボックスを共有として定義Exchange Onlineの違いがあります。 <p> お客様は、すべての共有メールボックスが 、、またはを使用して適切にプロビジョニング `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` されていることを確認する責任があります `Set-RemoteMailbox -Shared` 。 ハイブリッド環境でユーザーのメールボックスを変換する方法については、 [このリファレンスを参照してください](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox)。|フェーズ 5 [Exchange Online 移行] より前にこのタスクを完了できなかった場合、共有メールボックスの NDR が発生し、ライセンスのないメールボックスに戻り、影響を受けるメールボックスの共有アクセスが失われる可能性があります。 [Exchange](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)ハイブリッド展開でディレクトリ同期を実行した後、共有メールボックスは予期せずユーザー メールボックスに変換され、移行が完了する前にこの問題に対処しない場合のExchange Online概要を示します。|


## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**適用対象 :** Skype For Business Online のお客様<br>
**適用時**: フェーズ 7 が開始される前の任意の時間

<br>

****

|Step(s)|Description|影響|
|---|---|---|
|ドイツTeamsユーザー向けデスクトップ クライアントSkype for Business展開します。|移行は、Skype for Business、通話、Microsoft Teamsのユーザーに移動します。 いずれかの方法で、Microsoft Teamsデスクトップ クライアントを展開するか、サポートされているブラウザーを使用できます。|不作為により、コラボレーション サービスMicrosoft Teams利用できなくなる。|
|移行関連の DNS 変更の確認と準備を行います。|オンラインのユーザーが所有する DNS ゾーンSkype for Business変更します。|<ul><li>顧客が所有するドメイン DNS レコードのタイム to ライブ (TTL) を 5 分に更新して、DNS レコードの更新を迅速に行う方法をお勧めします。 ただし、この DNS 変更に関連付けられた Microsoft が管理するカットオーバーは、指定された 24 時間の変更ウィンドウ内でいつでも発生する可能性があります。</li><li>サービスの中断は、将来可能です。 ユーザーはアプリにログインできないSkype for Business、移行されたTeamsエクスペリエンスにOffice 365されます。</li></ul>|
|エンド ユーザーと管理のトレーニングと準備を行い、エンド ユーザーへの移行をMicrosoft Teams。|ユーザーのコミュニケーションと準備を計画することで、SkypeからTeamsへの移行に成功します。|<ul><li>クライアントは、新しいサービスと、サービスが新しいサービスに移行された後の使い方Office 365必要があります。</li><li>顧客のバニティ ドメインと初期ドメインの両方で DNS の変更が行われた後、ユーザーは Skype for Business にサインインし、Teams に移行されるのを確認します。 これにより、バックグラウンドでデスクトップ クライアントTeamsダウンロードされます。</li></ul>|


## <a name="mobile-device-management"></a>モバイル デバイス管理

<!-- before phase 5 -->
**適用対象:** サードパーティのモバイル デバイス管理 (MDM) ソリューションを使用しているお客様<br>
**適用時**: フェーズ 5 が開始される前の任意の時間

<br>

****

|Step(s)|Description|適用対象|影響|
|---|---|---|---|
|iOS および Android 向け Microsoft Outlookアカウントを削除および再追加するユーザーに関するエンド ユーザートレーニングと管理トレーニングを準備します。|新Outlook Office 365 サービス構成を適切に同期するには、Microsoft Cloud Deutschland のメールボックスで構成された iOS アカウントと Android アカウント用の Microsoft Outlook を削除し、Outlook に再度追加する必要があります。|Microsoft Outlook iOS および Android のお客様向けサービス|Outlook Microsoft Cloud Deutschland 用に以前に構成されたメールボックスでは、Office 365 Services の新しい構成を取得できない可能性があります。その他のユーザー エクスペリエンスのエラーやパフォーマンスの低下につながります。 移行後にメールのサインインまたは同期に関する問題が発生した場合、IT 管理者は、iOS および Android 用の Microsoft Outlook のアカウントを削除して再追加するようユーザーに事前に指示するドキュメントを提供するようお勧めしています。|
|移行後に再構成が必要かどうかを判断します。|モバイル デバイス管理 (MDM) ソリューションはエンドポイントを `outlook.de` 対象とします。 このサービスへの移行Office 365、クライアント プロファイルはサービス URL に更新Office 365必要があります `outlook.office365.com` 。|Exchange Online MDM のお客様|クライアントは、エンドポイントにアクセスできる間も引き続き機能しますが、Microsoft Cloud Deutschland エンドポイントが使用できなくなった場合は失敗 `outlook.de` します。|


## <a name="line-of-business-apps"></a>Line-of-business アプリ

**適用対象:** Microsoft Cloud Deutschland が提供するエンドポイントを使用して、業務ライン (LOB) アプリを使用しているお客様<br>
**適用時**: フェーズ 2 の完了後とフェーズ 9 の終了前

Office 365 と統合されたサード パーティのサービスまたは業務ライン (LOB) アプリを使用している場合は、Microsoft Cloud Deutschland インスタンスによって提供されるエンドポイントへの依存関係を解決する必要があります。 たとえば、LOB アプリが接続している場合は、 `https://graph.microsoft.de/` エンドポイントをに変更する必要があります `https://graph.microsoft.com/` 。 フェーズ 2 の後Microsoft Office 365グローバル サービスのエンドポイントがテナントで利用できます。

移行中に、組織がフェーズ 2 とフェーズ 9 の間である間は、サードパーティ製のマルチテナント アプリケーション (MTA) を組織に追加することはできません。 移行がフェーズ 9 を完了すると、組織の MTA アプリケーションの追加または同意を再開できます。


| Step(s) | Description | 影響 |
|:-------|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | Microsoft Cloud Deutschland IP アドレスと URL を期待するために、Office 365と統合するサード パーティのサービスとアプリケーションがコード化される場合があります。 | 必須のアクション。 不作為により、サービスまたはクライアント ソフトウェアの障害が発生する可能性があります。 |


|Step(s)|Description|影響|
|---|---|---|
|移行後に再構成が必要かどうかを判断します。|Microsoft Cloud Deutschland IP アドレスと URL を期待するために、Office 365と統合するサード パーティのサービスとアプリケーションがコード化される場合があります。|必須のアクション。 不作為により、サービスまたはクライアント ソフトウェアの障害が発生する可能性があります。|


## <a name="dynamics-365"></a>Dynamics 365

**適用対象**: Microsoft Dynamics 365 を使用しているお客様

<br>

****

|Step(s)|Description|影響|
|---|---|---|
|Dynamics 365 サンドボックス サブスクリプションの場合は、必ず Microsoft Cloud Deutschland の Dynamics 365 サブスクリプションから Dynamics SQL インスタンスの実稼働環境をダウンロードしてください。 サンドボックスの移行前に、最新の実稼働バックアップをサンドボックスに復元する必要があります。|Dynamics 365 の移行では、サンドボックス環境が最新の実稼働データベースで更新される必要があります。|FastTrack チームは、8.x から 9.1.x へのバージョン アップグレードを検証するために、ドライ ランの実行をお客様に支援します。|


## <a name="power-bi"></a>Power BI

**適用対象**: お客様がサービスを利用Power BI

<br>

****

|Step(s)|Description|影響|
|---|---|---|
|Microsoft Cloud Deutschland Power BIサービスに移行されないサブスクリプションからオブジェクトPower BI削除Office 365します。|サービスの移行Power BI、データセットやダッシュボードなど、特定の成果物を削除するために顧客の操作が必要になります。|管理者は、サブスクリプションから次のアイテムを削除する必要があります。 <ul><li>Real-Timeデータセット (ストリーミング データセットやプッシュ データセットなど)</li><li>Power BIオンプレミスのデータ ゲートウェイ構成とデータ ソース </li></ul>|


## <a name="microsoft-azure"></a>Microsoft Azure

Microsoft Cloud Deutschland インスタンスで Office 365 と Microsoft Azure に同じ Azure Active Directory ID パーティションを使用している場合は、Microsoft Azure サービスの顧客による移行の準備を行っている必要があります。

> [!NOTE]
> Office 365 テナントが移行フェーズ 9 に達する前に、Microsoft Azure サービスの移行が開始されない場合があります。移行フェーズ 10 が開始される前に完了する必要があります。

Office 365 Azure リソース (ネットワーク、コンピューティング、ストレージなど) を使用しているお客様は、リソースの Office 365 サービス インスタンスへの移行を実行します。 この移行は、お客様の責任です。 メッセージ センターの投稿は開始を示します。 移行は、Azure ADサービス環境でOffice 365する必要があります。 Azure 移行については、「Azure 移行プレイブック」、「Azure Germany の移行 [ガイダンスの概要」を参照してください](/azure/germany/germany-migration-main)。

<br>

****

|Step(s)|Description|影響|
|---|---|---|
|パートナーと連携して、使用している Azure サービスを特定し、ドイツから Office 365 サービス テナントへの将来の移行に備えます。 Azure 移行プレイブックで説明されている [手順に従います](/azure/germany/germany-migration-main)。|<ul><li>Azure リソースの移行は顧客の責任であり、所定の手順に従って手動で作業する必要があります。 組織でどのサービスが使用されているのかを理解すると、Azure サービスの正常な移行の鍵になります。</li><li>Office 365同じ ID パーティション (組織) の下に Azure サブスクリプションを持つドイツのお客様は、サブスクリプションとサービスの移行を開始できる場合、Microsoft が定める順序に従う必要があります。</li></ul>|<ul><li>お客様は、インフラストラクチャ、サービス、およびプラットフォーム コンポーネントを含む複数の Azure サブスクリプション、各サブスクリプションを持つ場合があります。</li><li>管理者は、この移行イベントの一環として、迅速な移行と検証が可能なサブスクリプションと関係者を特定する必要があります。</li><li>所定のタイムライン内でこれらのサブスクリプションと Azure コンポーネントの移行を正常に完了できないと、Office サービスと Azure AD Office 365 サービスへの移行が完了し、データが失われる可能性があります。</li><li>メッセージ センター通知は、顧客主導の移行を開始できるポイントを通知します。</li></ul>|


<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services.

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:**

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components.
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>詳細

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

切り替えの移動:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移行プログラム情報](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams へのアップグレードを開始する](/microsoftteams/upgrade-start-here)
