---
title: Microsoft Cloud Deutschland からの移行の事前作業
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスに移行する場合の事前作業。'
ms.openlocfilehash: fb352c17d9868cf5c42034e198be63b6e0543dbb
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445604"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行の事前作業

組織に関連する作業前の手順にアクセスするには、次のリンクを使用します。

- Microsoft Cloud Deutschland で **Office** 365 を使用しているすべてのお客様に対して、次の手順を [実行します](#general-tenant-migration-considerations)。
- **DNS の変更については、** この [手順を実行します](#dns)。
- オンプレミスで Active **Directory フェデレーション サービスを使用している場合は** 、次の手順 [を実行します](#active-directory-federation-services-ad-fs)。
- SharePoint Online を使用 **している場合は、** この手順 [を実行します](#sharepoint-online)。
- Exchange Online または Exchange ハイブリッド **を使用** している場合 **は、** この手順 [を実行します](#exchange-online)。
- Skype for Business Online を **使用している場合は、** この手順 [を実行します。](#skype-for-business-online)
- サードパーティのモバイル デバイス管理 (MDM) ソリューションを使用している場合は、この手順 [を実行します](#mobile-device-management)。
- サード パーティのサービスまたは 365 と統合されている業務ライン **(LOB)** アプリを使用している場合Office手順を [実行します](#line-of-business-apps)。
- **Dynamics 365** も使用している場合は、この手順 [を実行します](#dynamics365)。
- Power BI も使用している **場合は、** この手順 [を実行します](#power-bi)。
- Azure サービスを 365 サブスクリプションと一緒にOffice場合は、この手順を[実行します](#microsoft-azure)。 

## <a name="general-tenant-migration-considerations"></a>テナントの移行に関する一般的な考慮事項

**適用対象:** Microsoft Deutschland Cloud インスタンスOffice 365 を使用しているすべてのお客様

Office 365 テナントとユーザー識別子は移行中に保持されます。 Azure ADサービス呼び出しは、Microsoft Cloud Deutschland から Office 365 グローバル サービスにリダイレクトされ、365 サービスにOfficeされません。

- 一般的なデータ保護規則 (GDPR) データ主体要求 (DSR) は、Azure Admin ポータルから今後の要求のために実行されます。 Microsoft Cloud Deutschland に常駐している従来の診断データまたは顧客以外の診断データは、30 日以上経過した時点で削除されます。
- Microsoft Authenticator を使用する多要素認証 (MFA) 要求はユーザー ObjectID (A GUID) として表示され、テナントは 365 サービスにコピー Officeされます。 MFA 要求は、この表示動作にもかかわらず期待通り実行されます。  365 サービス エンドポイントを使用してOfficeされた Microsoft Authenticator アカウントには、ユーザー プリンシパル名 (UPN) が表示されます。  Microsoft Cloud Deutschland エンドポイントを使用して追加されたアカウントは、ユーザー ObjectID を表示しますが、Microsoft Cloud Deutschland と Office 365 サービス エンドポイントの両方で動作します。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 移行後にクライアントの再起動とサインインおよびクライアントへのサインインについてユーザーに通知する準備をします。 | Officeクライアント ライセンスは、移行時に Microsoft Cloud Deutschland から Office 365 サービスに移行します。 クライアントは、クライアントからサインインおよびサインインした後、新しい有効なライセンスOffice取得します。 | ユーザーの製品Office 365 サービスからライセンスを更新Office必要があります。 ライセンスが更新されない場合、ライセンスOffice検証エラーが発生する可能性があります。 |
| 365 サービス URL Office IP アドレスへのネットワーク [接続を確認します](https://aka.ms/o365urls)。 | Office 365 サービスへのアクセスに使用される顧客がホストするクライアントとサービスはすべて、Office 365 グローバル サービス エンドポイントにアクセスできる必要があります。 <br>Office 365 サービス URL および IP アドレスに記載されている URL と IP アドレスへのアクセスを妨げるファイアウォール ルールが設定されている場合は [、Office 365](https://aka.ms/o365urls) グローバル サービス エンドポイントへのアクセスを許可するファイアウォールルールを変更する必要があります。| サービスまたはクライアント ソフトウェアの障害は、フェーズ 4 より前に実行されていない場合に発生する可能性があります。  |
| 試用版サブスクリプションをキャンセルします。 | 試用版サブスクリプションは移行されません。有料サブスクリプションの移行はブロックされます。 | キャンセル後にユーザーがアクセスした場合、試用版サービスは期限切れであり、機能しません。 |
| Microsoft Cloud Deutschland と 365 Global Services Officeの違いを分析します。 | Office 365 サービスには、現在の Microsoft Cloud Deutschland では利用できない追加の機能とサービスが含まれます。 サブスクリプションの転送中に、新しい機能をユーザーが利用できます。 | <ul><li> Microsoft Cloud Deutschland および 365 Global Services のライセンスによって提供されるOfficeを分析します。 最初に [、Office 365 プラットフォームのサービスの説明を参照してください](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 </li><li> Office 365 サービスの新機能を最初に無効にし、ユーザーまたはユーザーの変更管理への影響を制限し、必要に応じてユーザー ライセンスの割り当てを変更する必要があるかどうかを判断します。 </li><li>365 サービスによって提供される新しいサービスと機能について、ユーザーとヘルプ デスク スタッフOffice準備します。 |
| 移行中にコンテンツ [が](https://docs.microsoft.com/microsoft-365/compliance/retention) 不注意で削除されるのを回避するために、組織全体の保持ポリシーを作成します。  |<ul><li>移行中にエンド ユーザーによってコンテンツが誤って削除されるのを回避するために、組織全体の保持ポリシーを有効にすることもできます。 </li><li>保持は必要ありませんが、移行中はいつでも保持が期待通り動作する必要があります。保持ポリシーを持つことはバックアップの安全メカニズムです。 同時に、保持ポリシーは、すべての顧客、特に保存過多を懸念しているユーザーが使用する場合があります。</li></ul>| 「アイテム保持ポリシーと保持ラベルについて」の [説明に従ってアイテム保持ポリシーを適用します](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)。 サービスまたはクライアント ソフトウェアの障害は、フェーズ 4 / 9 より前に行われない場合に発生する可能性があります。 </li></ul>|
|||||

## <a name="dns"></a>DNS

<!-- before phase 9 -->

**適用対象**: カスタム _msoid_ CNAME を独自のユーザー設定で設定したDNS ドメイン

構成されている場合 _、msoid_ CNAME は Office デスクトップ クライアント (Microsoft 365 Apps、Office 365 ProPlus、Office 2019、2016、..) を使用しているお客様にのみ影響します。

所有する 1 つ以上の DNS 名前空間に _msoid_ という DNS CNAME を設定した場合は、最新のフェーズ 8 の終了まで CNAME を削除する必要があります。 フェーズ 8 の終了前にいつでも CNAME _msoid_ を削除できます。

DNS 名前空間で CNAME を設定した場合に確認するには、以下の手順に従い、contoso.com を独自 _のドメイン名_ に置き換える必要があります。

```console
nslookup -querytype=CNMAE msoid.contoso.com
```

コマンド ラインが DNS レコードを返す場合は、ドメインから _msoid_ CNAME を削除します。

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory フェデレーション サービス (AD FS)

<!-- before phase 4 -->

**適用対象**: オンプレミスの FS ADを使用して、365 に接続するユーザー Microsoft Officeします。<br>
**適用時**: フェーズ 4 が開始される前の任意の時間

[ADFS 移行手順の読み取りと適用](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**適用対象**: SharePoint 2013 オンプレミスを使用しているお客様<br>
**適用時**: フェーズ 4 が開始される前の任意の時間

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| SharePoint 2013 ワークフローを制限し、SharePoint Online の移行中に使用します。 | SharePoint 2013 ワークフローを削減し、移行前にインフライト ワークフローを完了します。 | 不作為により、ユーザーの混乱やヘルプ デスクの呼び出しが発生する可能性があります。 |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**適用対象**: 共有予定表と可用性アドレス空間を有効にしている Exchange Online のお客様<br>
**適用時**: フェーズ 9 の終了前の任意の時間

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 365 サービスへの今後の移行を外部Office通知します。 | 可用性アドレス空間の構成では、空き時間情報を 365 Officeできます。 | そうしない場合は、お客様の移行の後のフェーズでサービスまたはクライアントの障害が発生する可能性があります。 |
||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online ハイブリッド構成

**適用対象:** オンプレミスの Exchange サーバーでアクティブな Exchange ハイブリッド構成を使用しているすべてのお客様<br>
**適用時**: フェーズ 5 が開始される前の任意の時間

Exchange Online とオンプレミス のハイブリッド展開を行うエンタープライズ顧客はExchange Serverハイブリッド構成ウィザード (HCW) を実行して、ハイブリッドセットアップを維持および確立します。 Microsoft Cloud Deutschland から Office 365 ドイツ地域に移行する場合、管理者は Exchange 移行 (フェーズ 5) を開始する前に、"Office 365 Germany" モードで HCW の最新ビルドを再実行する必要があります。 次に、フェーズ 5 の完了時に "Office 365 Worldwide" モードで HCW を再度実行し、Office 365 ドイツ地域の設定でオンプレミス展開を完了します。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| (Pre-Stage 5) - 365 ドイツの設定を使用して HCW をOffice実行する <br><br> <i>このアクティビティは、365 テナントの移行が開始されたというメッセージ センター Office受信した直後に開始できます (フェーズ 1)。</i>| ステージ 5 より前から HCW (17.0.5378.0 以上) をアンインストールおよび再実行すると [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 、Microsoft Cloud Deutschland ユーザーと Office 365 ドイツ地域に移行されたユーザーの両方とメールを送受信するオンプレミス構成が準備されます。 <p><li> HCW で、[My **Office 365** 組織がホストされている] の下のリスト ボックスで、[Office **365 ドイツ] を選択します。** | ステージ 5 [Exchange 移行] が開始する前にこのタスクを完了できなかった場合、オンプレミスの Exchange 展開と 365 の間でルーティングされるメールの NDRs Officeがあります。  
| (Post-Stage 5) - 365 ワールドワイド設定を使用して HCW をOffice実行する <br><br> <i>このアクティビティは、Exchange 移行が完了したというメッセージ センター通知を受け取った後に開始できます (フェーズ 5)。</i>| ステージ 5 以降から HCW をアンインストールして再実行すると、ハイブリッド構成のオンプレミス構成がリセットされ [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 、365 グローバルOfficeされます。 <p><li> [My Office **365** 組織がホストされている] の下のリスト ボックスで **、[365 ワールドワイド] Officeを選択します**。 | ステージ 9 [移行の完了] より前にこのタスクを完了できなかった場合、オンプレミスの Exchange 展開と 365 の間でルーティングされるメールの NDRs Officeがあります。  
| 認証のためのグローバル セキュリティ トークン サービス (STS) を指す AuthServer オンプレミスの確立 | これにより、ハイブリッドオンプレミス環境を対象とする移行状態のユーザーからの Exchange 可用性要求に対する認証要求が、オンプレミス サービスにアクセスするために認証されます。 同様に、これにより、オンプレミスから 365 のグローバル サービス エンドポイントへのOffice認証が保証されます。 | Azure AD移行 (フェーズ 2) が完了したら、オンプレミス Exchange (ハイブリッド) トポロジの管理者は、Office 365 グローバル サービス用の新しい認証サービス エンドポイントを追加する必要があります。 Exchange PowerShell のこのコマンドを使用して、Azure Active Directory の Azure portal にある組織のテナント `<TenantID>` ID に置き換える。<br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1`<br> このタスクを完了できないと、Microsoft Cloud Deutschland から Office 365 サービスに移行されたメールボックス ユーザーの情報をハイブリッド空き時間要求で提供できない場合があります。  |
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**適用対象**: Skype For Business Online のお客様<br>
**適用時**: フェーズ 7 が開始される前の任意の時間

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| ドイツの Skype for Business にアクセスするユーザー向け Teams デスクトップ クライアントを展開します。 | 移行では、Skype for Business ユーザーを Microsoft Teams に移動して、コラボレーション、通話、チャットを行います。 Microsoft Teams デスクトップ クライアントを展開するか、サポートされているブラウザーが使用可能か確認します。 | 不作為により、Microsoft Teams のコラボレーション サービスが利用できなくなる。 |
| 移行関連の DNS 変更の確認と準備を行います。 | Skype for Business Online の顧客所有の DNS ゾーンの変更。 |<ul><li>顧客が所有するドメイン DNS レコードのタイム to ライブ (TTL) を 5 分に更新して、DNS レコードの更新を迅速に行う方法をお勧めします。 ただし、この DNS 変更に関連付けられた Microsoft が管理するカットオーバーは、指定された 24 時間の変更ウィンドウ内でいつでも発生する可能性があります。 </li><li>サービスの中断は、将来可能です。 ユーザーは Skype for Business にログインできないので、365 サービスの移行済み Teams エクスペリエンスOfficeされます。 </li></ul>|
| Microsoft Teams への移行に向けて、エンド ユーザーと管理のトレーニングと準備を準備します。 | ユーザーとのコミュニケーションと準備を計画することで、Skype から Teams への移行に成功します。 | <ul><li>クライアントは、新しいサービスと、サービスが 365 サービスに移行された後の使用Office必要があります。 </li><li>顧客のバニティ ドメインと初期ドメインの両方に対して DNS の変更が行われた後、ユーザーは Skype for Business にサインインし、Teams に移行されるのを確認します。 これにより、バックグラウンドで Teams 用のデスクトップ クライアントもダウンロードされます。 </li></ul>|
||||

## <a name="mobile-device-management"></a>モバイル デバイスの管理

<!-- before phase 5 -->
**適用対象:** サードパーティのモバイル デバイス管理 (MDM) ソリューションを使用しているお客様<br>
**適用時**: フェーズ 5 が開始される前の任意の時間

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| iOS および Android 用 Microsoft Outlook に自分のアカウントを削除して再追加するユーザーに関するエンド ユーザートレーニングと管理トレーニングを準備します。 | 新しい Office 365 サービス構成を適切に同期するには、Microsoft Cloud Deutschland のメールボックスで構成された Microsoft Outlook for iOS アカウントと Android アカウントを削除し、Outlook に再度追加する必要があります。 | Microsoft Outlook for iOS および Android のお客様 | 以前に Microsoft Cloud Deutschland 用に構成された Outlook メールボックスは、新しい Office 365 Services 構成を取得できない可能性があります。その他のユーザー エクスペリエンスのエラーやパフォーマンスの低下につながります。 移行後にメールのサインインまたは同期に関する問題が発生した場合、IT 管理者は、アカウントを削除して Microsoft Outlook for iOS および Android に再追加するようユーザーに事前に指示するドキュメントを提供するようお勧めしています。 |
| 移行後に再構成が必要かどうかを判断します。 | モバイル デバイス管理 (MDM) ソリューションはエンドポイントを `outlook.de` 対象とします。 この 365 サービスへのOffice、クライアント プロファイルは 365 サービスの URL に更新Officeする必要があります `outlook.office365.com` 。 | Exchange Online および MDM のお客様 | クライアントは、エンドポイントにアクセスできる間も引き続き機能しますが、Microsoft Cloud Deutschland エンドポイントが使用できなくなった場合は失敗 `outlook.de` します。 |
|||||

## <a name="line-of-business-apps"></a>Line-of-business アプリ

**適用対象:** Microsoft Cloud Deutschland が提供するエンドポイントを使用して、業務ライン (LOB) アプリを使用しているお客様<br>
**適用時**: フェーズ 2 の完了後とフェーズ 9 の終了前

Office 365 と統合されたサード パーティ製のサービスまたは業務ライン (LOB) アプリを使用している場合は、Microsoft Cloud Deutschland インスタンスによって提供されるエンドポイントへの依存関係を解決する必要があります。 たとえば、LOB アプリが接続している場合は、 `https://graph.microsoft.de/` エンドポイントをに変更する必要があります `https://graph.microsoft.com/` 。 フェーズ 2 の後、Microsoft Office 365 Global サービスのエンドポイントがテナントで利用できます。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | Microsoft Cloud Deutschland IP アドレスと URL を期待するために、Office 365 と統合するサード パーティのサービスとアプリケーションがコード化される場合があります。 | 必須のアクション。 不作為により、サービスまたはクライアント ソフトウェアの障害が発生する可能性があります。 |
||||

## <a name="dynamics-365"></a>Dynamics 365

**適用対象**: Microsoft Dynamics 365 を使用しているお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Dynamics 365 サンドボックス サブスクリプションの場合は、必ず Microsoft Cloud Deutschland の Dynamics 365 サブスクリプションから Dynamics SQL インスタンスの実稼働環境をダウンロードしてください。 サンドボックスの移行前に、最新の実稼働バックアップをサンドボックスに復元する必要があります。 | Dynamics 365 の移行では、サンドボックス環境が最新の実稼働データベースで更新される必要があります。 | FastTrack チームは、8.x から 9.1.x へのバージョン アップグレードを検証するために、ドライ ランの実行をお客様に支援します。 |
||||

## <a name="power-bi"></a>Power BI

**適用対象**: Power BI を使用しているお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Power BI Microsoft Cloud Deutschland から 365 サービスに移行されない Power BI サブスクリプションOffice削除します。 | Power BI サービスの移行では、データセットやダッシュボードなど、特定の成果物を削除するために顧客の操作が必要になります。 | <ul><li>管理者は、サブスクリプションから次のアイテムを削除する必要があります。 </li><li>Real-Timeデータセット (ストリーミング データセットやプッシュ データセットなど) </li><li>Power BI オンプレミスのデータ ゲートウェイの構成とデータ ソース </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

microsoft Cloud Deutschland インスタンスで Office 365 と Microsoft Azure に同じ Azure Active Directory ID パーティションを使用している場合は、お客様が Microsoft Azure サービスを移行する準備を行っている必要があります。

> [!NOTE]
> Office 365 テナントが移行フェーズ 3 に達する前に Microsoft Azure サービスの移行を開始し、移行フェーズ 8 が完了する前に完了する必要があります。

Office 365 および Azure リソース (ネットワーク、コンピューティング、ストレージなど) を使用しているお客様は、Office 365 サービス インスタンスへのリソースの移行を実行します。 この移行は、お客様の責任です。 メッセージ センターの投稿は開始を示します。 365 サービス環境で Azure AD組織をOfficeする必要があります。 Azure 移行については、「Azure 移行プレイブック」、「Azure Germany の移行 [ガイダンスの概要」を参照してください](https://docs.microsoft.com/azure/germany/germany-migration-main)。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| パートナーと協力して、使用している Azure サービスを特定し、ドイツから Office 365 サービス テナントへの将来の移行に備えます。 Azure 移行プレイブックで説明されている [手順に従います](/azure/germany/germany-migration-main)。 |<ul><li>Azure リソースの移行は顧客の責任であり、所定の手順に従って手動で作業する必要があります。 組織でどのサービスが使用されているのかを理解すると、Azure サービスの正常な移行の鍵になります。 </li><li> Office ID パーティション (組織) の下に Azure サブスクリプションを持つ 365 人のドイツのお客様は、サブスクリプションとサービスの移行を開始できる場合、Microsoft が定める順序に従う必要があります。</li></ul>|<ul><li>お客様は、インフラストラクチャ、サービス、およびプラットフォーム コンポーネントを含む複数の Azure サブスクリプション、各サブスクリプションを持つ場合があります。 </li><li> 管理者は、この移行イベントの一環として、迅速な移行と検証が可能なサブスクリプションと関係者を特定する必要があります。 </li><li>所定のタイムライン内でこれらのサブスクリプションと Azure コンポーネントの移行を正常に完了できないと、Office および Azure AD が Office 365 サービスに移行し、データが失われる可能性があります。 </li><li> メッセージ センター通知は、顧客主導の移行を開始できるポイントを通知します。 </li></ul>|
||||

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

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツのデータセンター地域Office 365 サービスへの Microsoft Cloud Deutschland からの移行](ms-cloud-germany-transition.md)
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
