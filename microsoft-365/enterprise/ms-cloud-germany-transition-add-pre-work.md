---
title: Microsoft Cloud Deutschland からの移行の事前作業
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
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
ms.openlocfilehash: 085630c498cebfea26fb3de975740af17cb73921
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454421"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行の事前作業


組織に関連する作業前の手順にアクセスするには、次のリンクを使用します。

- すべてのサブスクリプションについて、次の手順 [を実行します](#applies-to-everyone)。
- Exchange Online または Exchange ハイブリッドを使用している場合は、この手順 [を実行します](#exchange-online)。
- SharePoint Online を使用している場合は、この手順 [を実行します](#sharepoint-online)。
- サードパーティのモバイル デバイス管理 (MDM) ソリューションを使用している場合は、この手順 [を実行します](#mobile)。
- サード パーティのサービスまたは 365 と統合された LOB (line-of-business) アプリを使用している場合Office手順を [実行します](#line-of-business-apps)。
- 365 サブスクリプションに含まれる Azure サービス以外の Azure サービスOffice場合は、この手順を [実行します](#azure)。
- Dynamics 365 も使用している場合は、この手順 [を実行します](#dynamics365)。
- Power BI も使用している場合は、この手順 [を実行します](#power-bi)。
- DNS の変更については、この [手順を実行します](#dns)。
- フェデレーション ID を使用している場合は、次の手順 [を実行します](#federated-identity)。

## <a name="applies-to-everyone"></a>すべてのユーザーに適用されます

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 365 サービス URL Office IP アドレスへのネットワーク [接続を確認します](https://aka.ms/o365urls)。 | 365 サービスへのアクセスに使用される顧客によってホストOfficeサービスは、Office 365 サービス エンドポイントにアクセスできる必要があります。 | 移行中のすべてのお客様、およびネットワーク アクセスが Microsoft Cloud Deutschland に制限されているお客様。 | 必須のアクション。 サービスまたはクライアント ソフトウェアの障害は、フェーズ 4 / 9 より前に行われない場合に発生する可能性があります。 |
| 移行関連の DNS 変更の確認と準備を行います。 | Skype for Business Online の顧客所有の DNS ゾーンの変更。 | Skype For Business Online のお客様 | - 顧客が所有するドメイン DNS レコードのタイム to ライブ (TTL) を 5 分に更新して、DNS レコードの更新を迅速に行う方法をお勧めします。 ただし、この DNS 変更に関連付けられた Microsoft が管理するカットオーバーは、指定された 24 時間の変更ウィンドウ内でいつでも発生する可能性があります。 <br><br> - サービスの中断は、将来可能です。 ユーザーは Skype for Business にログインできないので、365 サービスの移行済み Teams エクスペリエンスOfficeされます。 |
| Microsoft Teams への移行に向けて、エンド ユーザーと管理のトレーニングと準備を準備します。 | ユーザーとのコミュニケーションと準備を計画することで、Skype から Teams への移行に成功します。 | Skype For Business Online のお客様 | - クライアントは、新しいサービスと、サービスが 365 サービスに移行された後の使用Office必要があります。 <br><br> - 顧客のバニティ ドメインと初期ドメインの両方に対して DNS の変更が行われた後、ユーザーは Skype for Business にサインインし、Teams に移行されるのを確認します。 これにより、バックグラウンドで Teams 用のデスクトップ クライアントもダウンロードされます。 |
| iOS および Android 用 Microsoft Outlook に自分のアカウントを削除して再追加するユーザーに関するエンド ユーザートレーニングと管理トレーニングを準備します。 | 新しい Office 365 サービス構成を適切に同期するには、Microsoft Cloud Deutschland のメールボックスで構成された Microsoft Outlook for iOS アカウントと Android アカウントを削除し、Outlook に再度追加する必要があります。 | Microsoft Outlook for iOS および Android のお客様 | 以前に Microsoft Cloud Deutschland 用に構成された Outlook メールボックスは、新しい Office 365 Services 構成を取得できない可能性があります。その他のユーザー エクスペリエンスのエラーやパフォーマンスの低下につながります。 移行後にメールのサインインまたは同期に関する問題が発生した場合、IT 管理者は、アカウントを削除して Microsoft Outlook for iOS および Android に再追加するようユーザーに事前に指示するドキュメントを提供するようお勧めしています。 |
| 移行後にクライアントの再起動とサインインおよびクライアントへのサインインについてユーザーに通知する準備をします。 | Officeクライアント ライセンスは、移行時に Microsoft Cloud Deutschland から Office 365 サービスに移行します。 クライアントは、クライアントからサインインおよびサインインした後、新しい有効なライセンスOffice取得します。 | Microsoft 365 Apps のお客様 |  ユーザーの製品Office 365 サービスからライセンスを更新Office必要があります。 ライセンスが更新されない場合、ライセンスOffice検証エラーが発生する可能性があります。 |
| 試用版サブスクリプションをキャンセルします。 | 試用版サブスクリプションは移行されません。有料サブスクリプションの移行はブロックされます。 | すべてのお客様 | キャンセル後にユーザーがアクセスした場合、試用版サービスは期限切れであり、機能しません。 |
| ドイツの Skype for Business にアクセスするユーザー向け Teams デスクトップ クライアントを展開します。 | 移行では、共同作業、通話、チャットのためにユーザーを Teams に移動します。 Teams デスクトップ クライアントを展開するか、サポートされているブラウザーが使用可能か確認します。 | Skype for Business のお客様 | 不作為により、Teams コラボレーション サービスが利用できなくなる。 |
| Microsoft Cloud Deutschland と 365 Services のライセンス機能Office分析します。 | Office 365 サービスには、現在の Microsoft Cloud Deutschland では利用できない追加の機能とサービスが含まれます。 サブスクリプションの転送中に、新しい機能をユーザーが利用できます。 | すべてのお客様 | - Microsoft Cloud Deutschland および 365 Services のライセンスによって提供されるOffice分析します。 最初に [、Office 365 プラットフォームのサービスの説明を参照してください](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 <br><br> - Office 365 サービスの新機能を最初に無効にし、ユーザーまたはユーザー変更管理への影響を制限し、必要に応じてユーザー ライセンスの割り当てを変更する必要があるかどうかを判断します。 <br><br> - 365 サービスによって提供される新しいサービスと機能について、ユーザーとヘルプ デスク スタッフOffice準備します。 |
| 移行中にコンテンツ [が](https://docs.microsoft.com/microsoft-365/compliance/retention) 不注意で削除されるのを回避するために、組織全体の保持ポリシーを作成します。  | - 移行中にエンド ユーザーによってコンテンツが誤って削除されるのを回避するために、組織全体のアイテム保持ポリシーを有効にすることもできます。 <br><br> - 保持は必要ありませんが、移行中にいつでも保持が期待通り動作する必要があります。保持ポリシーを持つことはバックアップの安全メカニズムです。 同時に、保持ポリシーは、すべての顧客、特に保存過多を懸念しているユーザーが使用する場合があります。 | Office顧客 | 「アイテム保持ポリシーと保持ラベルについて」の [説明に従ってアイテム保持ポリシーを適用します](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)。 サービスまたはクライアント ソフトウェアの障害は、フェーズ 4 / 9 より前に行われない場合に発生する可能性があります。  |
| [障害復旧シナリオ用の Active Directory](ms-cloud-germany-transition-add-adfs.md#backup) フェデレーション サービス (AD FS) ファームのバックアップ。 | AD FS ファームを適切にバックアップして、証明書利用者の信頼をグローバル & ドイツのエンドポイントに確実に復元するには、ドメインの発行者 URI に触れることなく復元する必要があります。 必要に応じて、ADのバックアップに FS Rapid Restore を使用し、それぞれの復元を使用してください。 | フェデレーション認証組織 | 必須アクション。 顧客の FS ファームに障害が発生した場合、移行中にサービスAD影響が発生します。 詳細については、「ADFS 移行手順」を参照してください(https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |


## <a name="exchange-online"></a>Exchange Online

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 365 サービスへの今後の移行を外部Office通知します。 | 可用性アドレス空間の構成では、空き時間情報を 365 Officeできます。 | 予定表と空き時間情報の共有アドレススペースを有効にしている Exchange Online のお客様。 | 必須のアクション。  そうしない場合は、お客様の移行の後のフェーズでサービスまたはクライアントの障害が発生する可能性があります。 |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>ハイブリッド Exchange の場合

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行前にハイブリッド構成ウィザード (HCW) の最新バージョンに更新します。 <br><br> Microsoft Cloud Deutschland ハイブリッド Exchange Online のお客様は、以前のバージョンの HCW をアンインストールしてから、最新バージョン (17.0.5378.0 以降) をインストールして実行する必要があります [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 。 | HCW の最新バージョンには、Microsoft Cloud Deutschland から 365 Services に移行する顧客をサポートするために必要な更新Office含まれています。 <br><br> 更新プログラムには、送信コネクタと受信コネクタのオンプレミス証明書設定の変更が含まれます。 <br><br> フェーズ 5 of 9 (Exchange 移行) が開始Office前に、365 ドイツの設定を使用して再インストールする必要があります。 <br><br> 注: Office 365 サービスへの移行が完了すると、OFFICE 365 Worldwide 設定を使用してグローバル サービスを使用してハイブリッドセットアップを完了するために、HCW を再度削除して再インストールします。 | ハイブリッド展開を実行している Exchange Online のお客様 | 必須のアクション。 フェーズ 5 of 9 (Exchange 移行) の前に失敗すると、サービスまたはクライアントの障害が発生する可能性があります。 |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

SharePoint 2013 がある場合:

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint 2013 ワークフローを制限し、SharePoint Online の移行中に使用します。 | SharePoint 2013 ワークフローを削減し、移行前にインフライト ワークフローを完了します。 | SharePoint Online のお客様 | 不作為により、ユーザーの混乱やヘルプ デスクの呼び出しが発生する可能性があります。 |
|||||

## <a name="mobile"></a>モバイル

サードパーティのモバイル デバイス管理 (MDM) ソリューションを使用している場合:

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | MDM ソリューションはエンドポイントを `outlook.de` ターゲットにしている場合があります。 この 365 サービスへのOffice、クライアント プロファイルは 365 サービスの URL に更新Officeする必要があります `outlook.office365.com` 。 | Exchange Online および MDM のお客様 | クライアントは、エンドポイントにアクセスできる間も引き続き機能しますが、Microsoft Cloud Deutschland エンドポイントが使用できなくなった場合は失敗 `outlook.de` します。 |
|||||

## <a name="line-of-business-apps"></a>Line-of-business アプリ

サード パーティのサービスまたは 365 と統合された LOB (line-of-business) アプリを使用している場合は、次Officeします。 

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | Microsoft Cloud Deutschland IP アドレスと URL を期待するために、Office 365 と統合するサード パーティのサービスとアプリケーションがコード化される場合があります。 | すべてのお客様 | 必須のアクション。 不作為により、サービスまたはクライアント ソフトウェアの障害が発生する可能性があります。 |
|||||

## <a name="azure"></a>Azure 

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| パートナーと協力して、使用している Azure サービスを特定し、ドイツから Office 365 サービス テナントへの将来の移行に備えます。 Azure 移行プレイブックで説明されている [手順に従います](https://docs.microsoft.com/azure/germany/germany-migration-main)。 | Azure リソースの移行は顧客の責任であり、所定の手順に従って手動で作業する必要があります。 組織でどのサービスが使用されているのかを理解すると、Azure サービスの正常な移行の鍵になります。 <br><br> Office ID パーティション (組織) の下に Azure サブスクリプションを持つ 365 人のドイツのお客様は、サブスクリプションとサービスの移行を開始できる場合、Microsoft が定める順序に従う必要があります。 | Azure のお客様 | - お客様は、インフラストラクチャ、サービス、およびプラットフォーム コンポーネントを含む複数の Azure サブスクリプション、各サブスクリプションを持つ場合があります。 <br><br> - 管理者は、この移行イベントの一部として迅速な移行と検証が可能な場合に、サブスクリプションと関係者を特定する必要があります。 <br><br> 所定のタイムライン内でこれらのサブスクリプションと Azure コンポーネントの移行を正常に完了できないと、Office および Azure AD が Office 365 サービスに移行し、データが失われる可能性があります。  <br><br> - メッセージ センター通知は、顧客主導の移行を開始できるポイントを通知します。 |
|||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="dynamics-365"></a>Dynamics 365

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Dynamics 365 サンドボックス サブスクリプションの場合は、必ず Microsoft Cloud Deutschland の Dynamics 365 サブスクリプションから Dynamics SQL インスタンスの実稼働環境をダウンロードしてください。 サンドボックスの移行前に、最新の実稼働バックアップをサンドボックスに復元する必要があります。 | Dynamics 365 の移行では、サンドボックス環境が最新の実稼働データベースで更新される必要があります。 | Microsoft Dynamics のお客様 | FastTrack チームは、8.x から 9.1.x へのバージョン アップグレードを検証するために、ドライ ランの実行をお客様に支援します。 |
|||||

## <a name="power-bi"></a>Power BI

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Power BI Microsoft Cloud Deutschland から 365 サービスに移行されない Power BI サブスクリプションOffice削除します。 | Power BI サービスの移行では、データセットやダッシュボードなど、特定の成果物を削除するために顧客の操作が必要になります。 | Power BI のお客様 | 管理者は、サブスクリプションから次のアイテムを削除する必要があります。 <br> - Real-Timeデータセット (ストリーミング データセットやプッシュ データセットなど) <br> - Power BI オンプレミスのデータ ゲートウェイの構成とデータ ソース |
|||||

## <a name="dns"></a>DNS

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Azure がカットオーバーする前にいつでも存在する場合は、顧客所有の DNS から MSOID、CName を削除AD削除します。 変更を迅速に有効にできるよう、5 分の TTL を設定できます。 | 顧客が所有する DNS ゾーンの変更 | Officeサービスのお客様 | 
|||||

## <a name="federated-identity"></a>フェデレーション ID

| Step(s) | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| シングル サインオン (SSO) の識別子を既存の証明書利用者信頼に追加し、FS メタデータの自動更新AD無効にします。 | 移行を開始する前に、FS 証明書利用者ADに ID を追加する必要があります。 証明書利用者識別子が誤って削除されないようにするには、メタデータ更新の自動更新を無効にします。 <br><br> FS サーバーで次のコマンドAD実行します。 <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | フェデレーション認証組織 | 必須アクション。 フェーズ 4 / 9 (SharePoint) の前の不作為は、移行中にサービスに影響を与えます。  |
| グローバル Azure クライアント エンドポイントに対する証明書利用者AD生成します。 | 顧客は、グローバル エンドポイントへの証明書利用者信頼 (RPT) を手動で [作成する](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 必要があります。 これは、グローバル フェデレーション メタデータ URL を活用し [、Azure AD RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) クレーム ルール (AD FS ヘルプ) を使用してクレーム ルールを生成し、RPT にインポートすることで、GUI を介して新しい RPT を追加します。 | フェデレーション認証組織 | 必須アクション。 不作為は、移行中にサービスに影響を与えます。 |
|||||

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

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
