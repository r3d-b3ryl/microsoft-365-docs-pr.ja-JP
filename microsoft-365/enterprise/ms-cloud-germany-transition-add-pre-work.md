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
ms.openlocfilehash: 37fde0119dfc84cbe9120cf922cbac469a0a50f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923840"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行の事前作業

組織に関連する作業前の手順にアクセスするには、次のリンクを使用します。

- Microsoft Cloud Deutschland で Office 365 を使用しているすべてのお客様に対して、次の手順を [実行します](#applies-to-everyone)。
- Exchange Online または Exchange ハイブリッドを使用している場合は、この手順 [を実行します](#exchange-online)。
- SharePoint Online を使用している場合は、この手順 [を実行します](#sharepoint-online)。
- サードパーティのモバイル デバイス管理 (MDM) ソリューションを使用している場合は、この手順 [を実行します](#mobile)。
- サード パーティのサービスまたは 365 と統合された LOB (line-of-business) アプリを使用している場合Office手順を [実行します](#line-of-business-apps)。
- 365 サブスクリプションに含まれる Azure サービス以外の Azure サービスOffice場合は、この手順を [実行します](#microsoft-azure)。
- Dynamics 365 も使用している場合は、この手順 [を実行します](#dynamics365)。
- Power BI も使用している場合は、この手順 [を実行します](#power-bi)。
- DNS の変更については、この [手順を実行します](#dns)。
- フェデレーション ID を使用している場合は、次の手順 [を実行します](#federated-identity)。

## <a name="applies-to-everyone"></a>すべてのユーザーに適用されます

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 移行後にクライアントの再起動とサインインおよびクライアントへのサインインについてユーザーに通知する準備をします。 | Officeクライアント ライセンスは、移行時に Microsoft Cloud Deutschland から Office 365 サービスに移行します。 クライアントは、クライアントからサインインおよびサインインした後、新しい有効なライセンスOffice取得します。 | ユーザーの製品Office 365 サービスからライセンスを更新Office必要があります。 ライセンスが更新されない場合、ライセンスOffice検証エラーが発生する可能性があります。 |
| 365 サービス URL Office IP アドレスへのネットワーク [接続を確認します](./urls-and-ip-address-ranges.md)。 | Office 365 サービスへのアクセスに使用される顧客がホストするクライアントとサービスはすべて、Office 365 グローバル サービス エンドポイントにアクセスできる必要があります。 <br>[この場合、Office 365](./urls-and-ip-address-ranges.md)サービス URL および IP アドレスに記載されている URL と IP アドレスへのアクセスを妨げるファイアウォール ルールが設定されている場合、Office 365 Global Service エンドポイントへのアクセスを許可するファイアウォール ルールを変更する必要があります。| サービスまたはクライアント ソフトウェアの障害は、フェーズ 4 より前に実行されていない場合に発生する可能性があります。  |
| 試用版サブスクリプションをキャンセルします。 | 試用版サブスクリプションは移行されません。有料サブスクリプションの移行はブロックされます。 | キャンセル後にユーザーがアクセスした場合、試用版サービスは期限切れであり、機能しません。 |
| Microsoft Cloud Deutschland と 365 Services のライセンス機能Office分析します。 | Office 365 サービスには、現在の Microsoft Cloud Deutschland では利用できない追加の機能とサービスが含まれます。 サブスクリプションの転送中に、新しい機能をユーザーが利用できます。 | <ul><li> Microsoft Cloud Deutschland および 365 Services のライセンスによって提供されるさまざまなOffice分析します。 最初に [、Office 365 プラットフォームのサービスの説明を参照してください](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 </li><li> Office 365 サービスの新機能を最初に無効にし、ユーザーまたはユーザーの変更管理への影響を制限し、必要に応じてユーザー ライセンスの割り当てを変更する必要があるかどうかを判断します。 </li><li>365 サービスによって提供される新しいサービスと機能について、ユーザーとヘルプ デスク スタッフOffice準備します。 |
| 移行中にコンテンツ [が](../compliance/retention.md) 不注意で削除されるのを回避するために、組織全体の保持ポリシーを作成します。  |<ul><li>移行中にエンド ユーザーによってコンテンツが誤って削除されるのを回避するために、組織全体の保持ポリシーを有効にすることもできます。 </li><li>保持は必要ありませんが、移行中はいつでも保持が期待通り動作する必要があります。保持ポリシーを持つことはバックアップの安全メカニズムです。 同時に、保持ポリシーは、すべての顧客、特に保存過多を懸念しているユーザーが使用する場合があります。</li></ul>| 「アイテム保持ポリシーと保持ラベルについて」の [説明に従ってアイテム保持ポリシーを適用します](../compliance/retention.md)。 サービスまたはクライアント ソフトウェアの障害は、フェーズ 4 / 9 より前に行われない場合に発生する可能性があります。 </li></ul>|
| ライセンスの過大使用を修正する | 特定の状況では、お客様は購入されたサービスよりも多くのサービスを利用できる場合があります。 この条件は、ライセンスの過剰使用と呼ばれる。 Microsoft は、ライセンス過剰使用条件の顧客を Microsoft Cloud Deutschland からドイツのデータセンター地域に移行することはできません。 サービスとデータに継続的にアクセスするには、割り当てられたすべてのユーザーにライセンスが必要です。 | すべてのお客様 | お客様は、追加のライセンスの購入またはユーザーからのライセンスの割り当てを解除して、ライセンスの過剰使用条件を評価および解決する必要があります。 |
|||||

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory フェデレーション サービス (AD FS)

**適用対象**: オンプレミスの FS ADを使用して、365 に接続するユーザー Microsoft Officeします。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| [障害復旧シナリオ用の Active Directory](ms-cloud-germany-transition-add-adfs.md#backup) フェデレーション サービス (AD FS) ファームのバックアップ。 | AD FS ファームを適切にバックアップして、証明書利用者の信頼をグローバル & ドイツのエンドポイントに確実に復元するには、ドメインの発行者 URI に触れることなく復元する必要があります。 必要に応じて、ADのバックアップに FS Rapid Restore を使用し、それぞれの復元を使用してください。 | 必須アクション。 顧客の FS ファームに障害が発生した場合、移行中にサービスAD影響が発生します。 詳細については [、「ADFS 移行手順」を参照してください。](./ms-cloud-germany-transition-add-adfs.md) |
||||

## <a name="exchange-online"></a>Exchange Online

**適用対象 :** 共有予定表と可用性アドレス空間を有効にしている Exchange Online のお客様。

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 365 サービスへの今後の移行を外部Office通知します。 | 可用性アドレス空間の構成では、空き時間情報を 365 Officeできます。 | そうしない場合は、お客様の移行の後のフェーズでサービスまたはクライアントの障害が発生する可能性があります。 |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online ハイブリッド構成

**適用対象**: Exchange ハイブリッド構成がアクティブな Exchange Online のお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| テナントが移行ステージ 5 に入る前に、いつでもハイブリッド構成ウィザード (HCW) の最新バージョンに更新します。 このアクティビティは、365 テナントの移行が開始されたというメッセージ センター Officeすぐに開始できます。<br><br> Microsoft Cloud Deutschland ハイブリッド Exchange Online のお客様は、以前のバージョンの HCW をアンインストールしてから、最新バージョン (17.0.5378.0 以降) をインストールして実行する必要があります [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 。 |<ul><li>HCW の最新バージョンには、Microsoft Cloud Deutschland から 365 Services に移行する顧客をサポートするために必要な更新Office含まれています。</li><li> 更新プログラムには、送信コネクタと受信コネクタのオンプレミス証明書設定の変更が含まれます。</li><li> Exchange 管理者は、フェーズ 5 of 9 (Exchange 移行) が開始する前に、いつでも HCW を再インストールする必要があります。<br>フェーズ 5 の前に HCW を実行する場合は、my Office 365 組織の下のリスト ボックスで Office _365 Exchange Online_ の下の HCW の 2nd ページで "Office _365_ Germany" を選択します。</li><li>**注**: Office 365 テナントの移行が完了すると、HCW の 2nd ページにある "Office 365 Worldwide" 設定を使用して、Exchange Online グローバル サービスを使用してハイブリッドセットアップを完了します。</li></ul>|フェーズ 5 (Exchange 移行) の前に HCW を実行すると、サービスまたはクライアントの障害が発生する可能性があります。 |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**適用対象**: オンプレミスで SharePoint 2013 を使用しているお客様


| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| SharePoint 2013 ワークフローを制限し、SharePoint Online の移行中に使用します。 | SharePoint 2013 ワークフローを削減し、移行前にインフライト ワークフローを完了します。 | 不作為により、ユーザーの混乱やヘルプ デスクの呼び出しが発生する可能性があります。 |
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

**適用対象**: Skype For Business Online のお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| ドイツの Skype for Business にアクセスするユーザー向け Teams デスクトップ クライアントを展開します。 | 移行では、Skype for Business ユーザーを Microsoft Teams に移動して、コラボレーション、通話、チャットを行います。 Microsoft Teams デスクトップ クライアントを展開するか、サポートされているブラウザーが使用可能か確認します。 | 不作為により、Microsoft Teams のコラボレーション サービスが利用できなくなる。 |
| 移行関連の DNS 変更の確認と準備を行います。 | Skype for Business Online の顧客所有の DNS ゾーンの変更。 |<ul><li>顧客が所有するドメイン DNS レコードのタイム to ライブ (TTL) を 5 分に更新して、DNS レコードの更新を迅速に行う方法をお勧めします。 ただし、この DNS 変更に関連付けられた Microsoft が管理するカットオーバーは、指定された 24 時間の変更ウィンドウ内でいつでも発生する可能性があります。 </li><li>サービスの中断は、将来可能です。 ユーザーは Skype for Business にログインできないので、365 サービスの移行済み Teams エクスペリエンスOfficeされます。 </li></ul>|
| Microsoft Teams への移行に向けて、エンド ユーザーと管理のトレーニングと準備を準備します。 | ユーザーとのコミュニケーションと準備を計画することで、Skype から Teams への移行に成功します。 | <ul><li>クライアントは、新しいサービスと、サービスが 365 サービスに移行された後の使用Office必要があります。 </li><li>顧客のバニティ ドメインと初期ドメインの両方に対して DNS の変更が行われた後、ユーザーは Skype for Business にサインインし、Teams に移行されるのを確認します。 これにより、バックグラウンドで Teams 用のデスクトップ クライアントもダウンロードされます。 </li></ul>|
||||

## <a name="mobile"></a>モバイル

サードパーティのモバイル デバイス管理 (MDM) ソリューションを使用している場合:

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| iOS および Android 用 Microsoft Outlook に自分のアカウントを削除して再追加するユーザーに関するエンド ユーザートレーニングと管理トレーニングを準備します。 | 新しい Office 365 サービス構成を適切に同期するには、Microsoft Cloud Deutschland のメールボックスで構成された Microsoft Outlook for iOS アカウントと Android アカウントを削除し、Outlook に再度追加する必要があります。 | Microsoft Outlook for iOS および Android のお客様 | 以前に Microsoft Cloud Deutschland 用に構成された Outlook メールボックスは、新しい Office 365 Services 構成を取得できない可能性があります。その他のユーザー エクスペリエンスのエラーやパフォーマンスの低下につながります。 移行後にメールのサインインまたは同期に関する問題が発生した場合、IT 管理者は、アカウントを削除して Microsoft Outlook for iOS および Android に再追加するようユーザーに事前に指示するドキュメントを提供するようお勧めしています。 |
| 移行後に再構成が必要かどうかを判断します。 | モバイル デバイス管理 (MDM) ソリューションはエンドポイントを `outlook.de` 対象とします。 この 365 サービスへのOffice、クライアント プロファイルは 365 サービスの URL に更新Officeする必要があります `outlook.office365.com` 。 | Exchange Online および MDM のお客様 | クライアントは、エンドポイントにアクセスできる間も引き続き機能しますが、Microsoft Cloud Deutschland エンドポイントが使用できなくなった場合は失敗 `outlook.de` します。 |
|||||

## <a name="line-of-business-apps"></a>Line-of-business アプリ

サード パーティのサービスまたは 365 と統合された LOB (line-of-business) アプリを使用している場合は、次Officeします。 

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | Microsoft Cloud Deutschland IP アドレスと URL を期待するために、Office 365 と統合するサード パーティのサービスとアプリケーションがコード化される場合があります。 | 必須のアクション。 不作為により、サービスまたはクライアント ソフトウェアの障害が発生する可能性があります。 |
||||

## <a name="dynamics-365"></a>Dynamics 365

**適用対象**: Microsoft Dynamics を使用しているお客様

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Dynamics 365 サンドボックス サブスクリプションの場合は、必ず Microsoft Cloud Deutschland の Dynamics 365 サブスクリプションから Dynamics SQL インスタンスの実稼働環境をダウンロードしてください。 サンドボックスの移行前に、最新の実稼働バックアップをサンドボックスに復元する必要があります。 | Dynamics 365 の移行では、サンドボックス環境が最新の実稼働データベースで更新される必要があります。 | FastTrack チームは、8.x から 9.1.x へのバージョン アップグレードを検証するために、ドライ ランの実行をお客様に支援します。 |
||||

## <a name="power-bi"></a>Power BI

**適用対象**: Power BI のお客様 

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| Power BI Microsoft Cloud Deutschland から 365 サービスに移行されない Power BI サブスクリプションOffice削除します。 | Power BI サービスの移行では、データセットやダッシュボードなど、特定の成果物を削除するために顧客の操作が必要になります。 | <ul><li>管理者は、サブスクリプションから次のアイテムを削除する必要があります。 </li><li>Real-Timeデータセット (ストリーミング データセットやプッシュ データセットなど) </li><li>Power BI オンプレミスのデータ ゲートウェイの構成とデータ ソース </li></ul>|
||||

## <a name="dns"></a>DNS

**適用** 対象 : Office デスクトップ クライアントを使用しているお客様 (Microsoft 365 Apps、Office 365 ProPlus、Office 2019、2016、..)<br>
Azure Active Directory (AD Azure Active Directory ) のカットオーバーの前にいつでも存在する場合は、顧客が所有する DNS から MSOID、CName を削除します。 変更を迅速に有効にできるよう、5 分の TTL を設定できます。

## <a name="federated-identity"></a>フェデレーション ID

| Step(s) | 説明 | 影響 |
|:-------|:-------|:-------|
| シングル サインオン (SSO) の識別子を既存の証明書利用者信頼に追加し、FS メタデータの自動更新AD無効にします。 | 移行を開始する前に、FS 証明書利用者ADに ID を追加する必要があります。 証明書利用者識別子が誤って削除されないようにするには、メタデータ更新の自動更新を無効にします。 <br><br> 次のコマンドを FS サーバー上の 1 つのコマンド ラインAD実行します。 <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| フェデレーション認証組織 | 必須アクション。 フェーズ 4 / 9 (SharePoint) の前の不作為は、移行中にサービスに影響を与えます。  |
| グローバル Azure クライアント エンドポイントに対する証明書利用者AD生成します。 | 顧客は、グローバル エンドポイントへの証明書利用者信頼 (RPT) を手動で [作成する](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 必要があります。 これは、グローバル フェデレーション メタデータ URL を活用し [、Azure AD RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) クレーム ルール (AD FS ヘルプ) を使用してクレーム ルールを生成し、RPT にインポートすることで、GUI を介して新しい RPT を追加します。 | フェデレーション認証組織 | 必須アクション。 不作為は、移行中にサービスに影響を与えます。 |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

microsoft Cloud Deutschland インスタンスで Office 365 と Microsoft Azure に同じ Azure Active Directory ID パーティションを使用している場合は、お客様が Microsoft Azure サービスを移行する準備を行っている必要があります。
Office 365 テナントが移行フェーズ 3 に達する前に Microsoft Azure サービスの移行を開始し、移行フェーズ 8 が完了する前に完了する必要があります。

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

## <a name="more-information"></a>詳細

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