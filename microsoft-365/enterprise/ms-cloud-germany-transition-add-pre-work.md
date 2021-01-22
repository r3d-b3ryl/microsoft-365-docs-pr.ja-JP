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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスに移行する場合の作業前作業。'
ms.openlocfilehash: cd32ce21e18b16660c4292c98ebcc0f7cb982173
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921568"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Microsoft Cloud Deutschland からの移行の事前作業


以下のリンクを使用して、組織に関連する作業前の手順にアクセスします。

- すべてのサブスクリプションについて、次の手順 [を実行します](#applies-to-everyone)。
- Exchange Online または Exchange ハイブリッドを使用している場合は、この手順 [を実行します](#exchange-online)。
- SharePoint Online を使用している場合は、この手順 [を実行します](#sharepoint-online)。
- サード パーティ製のモバイル デバイス管理 (MDM) ソリューションを使用している場合は、この手順 [を実行します](#mobile)。
- Office 365 と統合されたサード パーティ製のサービスまたは LOB (Line-of-Business) アプリを使用している場合は、この手順を [実行します](#line-of-business-apps)。
- Office 365 サブスクリプションに含まれているサービス以外の Azure サービスも使用している場合は、この手順 [を実行します](#azure)。
- Dynamics 365 も使用している場合は、この手順 [を実行します](#dynamics365)。
- Power BI も使用している場合は、この手順 [を実行します](#power-bi)。
- DNS の変更の場合は、この [手順を実行します](#dns)。
- フェデレーション ID を使用している場合は、次の手順 [を実行します](#federated-identity)。

## <a name="applies-to-everyone"></a>すべてのユーザーに適用されます

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 365 サービスの URL Office IP アドレスへの [ネットワーク接続を確認します](https://aka.ms/o365urls)。 | Office 365 サービスへのアクセスに使用される顧客がホストするクライアントとサービスはすべて、Office 365 サービス エンドポイントにアクセスできる必要があります。 | 移行中のすべてのお客様、およびネットワーク アクセスが Microsoft Cloud Deutschland に制限されているお客様。 | 必要なアクション。 不反応により、サービスまたはクライアント ソフトウェアの障害が発生する可能性があります。 |
| 移行に関連する DNS の変更を確認し、準備します。 | お客様は、Exchange Online および Exchange Online Protection (MX レコードなど) の DNS エントリを準備します。 | Exchange Online のお客様 | これは推奨されるアクションです。 移行したお客様のメールは、Microsoft Cloud Deutschland サービスが無効になるまで、Microsoft Cloud Deutschland を経由してルーティングされる可能性があるというアクションはありません。 |
| 移行に関連する DNS の変更を確認し、準備します。 | Skype for Business Online の顧客が所有する DNS ゾーンの変更。 | Skype For Business Online のお客様 | - 顧客が所有するドメイン DNS レコードの TTL (Time-to-Live) を 5 分に更新して、DNS レコードの更新を迅速に実行することをお勧めします。 ただし、この DNS 変更に関連する Microsoft が管理するカットオーバーは、指定された 24 時間の変更ウィンドウ内でいつでも発生する可能性があります。 <br><br> - サービスの中断は、将来発生する可能性があります。 ユーザーは Skype for Business にログインできないので、Office 365 サービスで移行された Teams エクスペリエンスにリダイレクトされます。 |
| エンド ユーザーと管理のトレーニングを準備し、Microsoft Teams に移行する準備をします。 | ユーザーのコミュニケーションと準備を計画することで、Skype から Teams への移行に成功します。 | Skype For Business Online のお客様 | - クライアントは、新しいサービスと、そのサービスが Office 365 サービスに移行された後の使用方法を認識する必要があります。 <br><br> - 顧客バニティ ドメインと初期ドメインの両方に対して DNS の変更が行われた後、ユーザーは Skype for Business にサインインして、Teams に移行されたのを確認します。 これにより、Teams のデスクトップ クライアントもバックグラウンドでダウンロードされます。 |
| iOS および Android 用の Microsoft Outlook にアカウントを削除して再追加するユーザーに関するエンド ユーザーおよび管理トレーニングを準備します。 | Microsoft Cloud Deutschland のメールボックスで構成された iOS および Android 用の Microsoft Outlook アカウントは、新しい Office 365 サービス構成を適切に同期するために、削除して Outlook にもう一度追加する必要があります。 | iOS および Android 用 Microsoft Outlook のお客様 | 以前に Microsoft Cloud Deutschland 用に構成された Outlook メールボックスでは、新しい Office 365 サービス構成が取得されない場合があります。その場合、エラーが発生し、他のユーザー エクスペリエンスのパフォーマンスが低下する可能性があります。 IT 管理者は、移行後にメールのサインインまたは同期に問題が発生した場合に、ユーザーにアカウントを削除して iOS および Android 用の Microsoft Outlook に再追加するよう事前に指示するドキュメントを提供するようお勧めしています。 |
| 移行後のクライアントの再起動とサインイン/サインアウトについてユーザーに通知する準備をします。 | Officeクライアント ライセンスは、移行時に Microsoft Cloud Deutschland から Office 365 サービスに移行されます。 クライアントは、他のクライアントからサインアウトしてサインインした後、新しい有効なライセンスOffice取得します。 | Microsoft 365 Apps のお客様 |  ユーザーの製品Office、365 サービスからライセンスOffice更新する必要があります。 ライセンスが更新されない場合、ライセンスOffice検証エラーが発生する可能性があります。 |
| 試用版サブスクリプションをキャンセルします。 | 試用版サブスクリプションは移行されません。また、有料サブスクリプションの移行はブロックされます。 | すべてのお客様 | ユーザーが取り消し後にアクセスすると、試用版サービスの有効期限が切れ、機能しません。 |
| ドイツの Skype for Business にアクセスするユーザー向け Teams デスクトップ クライアントを展開します。 | 移行では、共同作業、通話、チャットのためにユーザーを Teams に移動します。 Teams デスクトップ クライアントを展開するか、サポートされているブラウザーが使用可能なブラウザーを確認します。 | Skype for Business のお客様 | 不作為により、Teams のコラボレーション サービスが利用できなくなる可能性があります。 |
| Microsoft Cloud Deutschland と Office 365 サービスのライセンス機能の違いを分析します。 | Office 365 サービスには、現在の Microsoft Cloud Deutschland では利用できない追加の機能とサービスが含まれます。 サブスクリプションの転送中に、新しい機能がユーザーに提供されます。 | すべてのお客様 | - Microsoft Cloud Deutschland と Office 365 サービスのライセンスによって提供されるさまざまな機能を分析します。 [Office 365 プラットフォームのサービスの説明から始める](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 <br><br> - Office 365 サービスの新機能を最初に無効にし、ユーザーまたはユーザー変更管理への影響を制限し、必要に応じてユーザー ライセンス割り当てを変更する必要があるかどうかを決定します。 <br><br> - 365 サービスによって提供される新しいサービスと機能に対して、ユーザーとヘルプ デスクOffice準備します。 |
| 移行中にコンテンツ [が不](https://docs.microsoft.com/microsoft-365/compliance/retention) 注意で削除されるのを回避するために、組織全体のアイテム保持ポリシーを作成します。  | - 移行中にエンド ユーザーによってコンテンツが誤って削除されるのを回避するために、お客様は組織全体のアイテム保持ポリシーを有効にすることもできます。 <br><br> - 保持は必要ありませんが、移行中に保持がいつでも期待通り動作する必要があるから、アイテム保持ポリシーを持つことはバックアップの安全メカニズムです。 同時に、アイテム保持ポリシーは、すべてのお客様、特に保持の過ぎを懸念しているお客様が使用するとは限りない場合があります。 | Officeのお客様 | アイテム保持ポリシーと保持ラベルの [詳細の説明に従って、アイテム保持ポリシーを適用します](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)。 |
| [障害復旧シナリオ用の Active Directory フェデレーション サービス (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) ファームのバックアップ。 | お客様は、グローバル & Germany エンドポイントへの証明書利用者信頼をドメインの発行者 URI に触れることなく復元できるよう、AD FS ファームを適切にバックアップする必要があります。 必要に応じて、ADのバックアップに FS の迅速な復元を使用し、それぞれの復元を行う方法をお勧めします。 | フェデレーション認証組織 | 必須アクション。 お客様の FS ファームの移行に失敗した場合、ADサービスへの影響が生じ、 |


## <a name="exchange-online"></a>Exchange Online

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 365 サービスへの今後の移行についてOfficeパートナーに通知します。 | 空き時間情報アドレス スペースの構成では、空き時間情報を 365 Officeできます。 | 予定表と空き時間情報のアドレススペースの共有を有効にしている Exchange Online のお客様。 | 必要なアクション。  そうしない場合、お客様の移行の後のフェーズでサービスまたはクライアントの障害が発生する可能性があります。 |
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

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 以前のバージョンのハイブリッド構成ウィザード (HCW) をアンインストールし、最新バージョン 17.0.5378.0 をインストールして実行します [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 。 | HCW の最新バージョンには、Microsoft Cloud Deutschland から Office 365 サービスに移行しているお客様をサポートするために必要な更新プログラムが含まれています。 <br><br> 更新プログラムには、送信コネクタと受信コネクタのオンプレミス証明書設定の変更が含まれます。 | ハイブリッド展開を実行している Exchange Online のお客様 | 必要なアクション。 失敗すると、サービスまたはクライアントの障害が発生する可能性があります。 |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

SharePoint 2013 を使用している場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint Online の移行中に使用する SharePoint 2013 ワークフローを制限します。 | SharePoint 2013 ワークフローを削減し、移行前にインフライト ワークフローを完了します。 | SharePoint Online Customers | 不作為により、ユーザーが混乱し、ヘルプ デスクに電話をかける可能性があります。 |
|||||

## <a name="mobile"></a>モバイル

サード パーティ製のモバイル デバイス管理 (MDM) ソリューションを使用している場合:

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | MDM ソリューションはエンドポイントを `outlook.de` 対象とする場合があります。 Office 365 サービスへの移行では、クライアント プロファイルが Office 365 サービスの URL に更新されます `outlook.office365.com` 。 | Exchange Online および MDM のお客様 | エンドポイントにアクセスできる間、クライアントは引き続き機能しますが、Microsoft Cloud Deutschland エンドポイントが使用できなくなった場合は `outlook.de` 失敗します。 |
|||||

## <a name="line-of-business-apps"></a>Line-of-Business アプリ

サード パーティ製のサービスまたは LOB (Line-of-Business) アプリを使用している場合は、次のOfficeします。 

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 移行後に再構成が必要かどうかを判断します。 | Office 365 と統合するサード パーティのサービスおよびアプリケーションは、Microsoft Cloud Deutschland の IP アドレスと URL を期待してコード化される場合があります。 | すべてのお客様 | 必要なアクション。 不反応により、サービスまたはクライアント ソフトウェアの障害が発生する可能性があります。 |
|||||

## <a name="azure"></a>Azure 

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| 使用している Azure サービスを決定し、パートナーと協力してドイツから Office 365 サービス テナントへの将来の移行に備えます。 Azure 移行プレイブックで説明されている [手順に従います](https://docs.microsoft.com/azure/germany/germany-migration-main)。 | Azure リソースの移行は顧客の責任であり、定める手順に従って手動で作業する必要があります。 Azure サービスを正常に移行するには、組織で使用されているサービスについて理解する必要があります。 <br><br> Office ID パーティション (組織) の下に Azure サブスクリプションを持つ 365 Germany のお客様は、サブスクリプションとサービスの移行を開始する際に、Microsoft が定める命令に従う必要があります。 | Azure Customers | - お客様は複数の Azure サブスクリプションを持つ場合があります。各サブスクリプションには、インフラストラクチャ、サービス、およびプラットフォーム コンポーネントが含まれている必要があります。 <br><br> - 管理者は、この移行イベントの一部として迅速な移行と検証が可能な場合に、サブスクリプションと関係者を特定する必要があります。 <br><br> 所定のタイムライン内でこれらのサブスクリプションと Azure コンポーネントの移行を正常に完了できなかった場合、Office および Azure AD が Office 365 サービスに移行すると、データが失われる可能性があります。  <br><br> - メッセージ センターの通知は、顧客主導の移行を開始できるポイントを示します。 |
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

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Dynamics 365 サンドボックス サブスクリプションの場合は、Dynamics SQL インスタンスの実稼働環境を Microsoft Cloud Deutschland の Dynamics 365 サブスクリプションからダウンロードしてください。 サンドボックスの移行前に、最新の実稼働バックアップをサンドボックスに復元する必要があります。 | Dynamics 365 の移行では、サンドボックス環境が最新の実稼働データベースで更新される必要があります。 | Microsoft Dynamics のお客様 | FastTrack チームは、お客様がドライ ランを実行して、8.x から 9.1.x へのバージョン アップグレードを検証するサポートを行います。 |
|||||

## <a name="power-bi"></a>Power BI

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Power BI Microsoft Cloud Deutschland から 365 サービスに移行されない Power BI サブスクリプションOffice削除します。 | Power BI サービスを移行するには、データセットやダッシュボードなど、特定の成果物を削除する顧客のアクションが必要です。 | Power BI のお客様 | 管理者は、サブスクリプションから次のアイテムを削除する必要があります。 <br> - Real-Time データセット (ストリーミング データセットやプッシュ データセットなど) <br> - Power BI オンプレミスのデータ ゲートウェイの構成とデータ ソース |
|||||

## <a name="dns"></a>DNS

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| Azure がカットオーバーする前に存在する場合は、顧客が所有する DNS から MSOID、CName AD削除します。 TTL を 5 分に設定すると、変更をすぐに有効にできます。 | 顧客が所有する DNS ゾーンの変更 | Officeサービスのお客様 | 
|||||

## <a name="federated-identity"></a>フェデレーション ID

| 手順 | 説明 | 適用対象 | 影響 |
|:-------|:-----|:-------|:-------|
| シングル サインオン (SSO) の識別子を既存の証明書利用者信頼に追加し、AD FS メタデータの自動更新を無効にします。 | 移行を開始する前に、FS 証明書利用者信頼AD ID を追加する必要があります。 証明書利用者識別子が誤って削除されないようにするには、メタデータ更新の自動更新を無効にします。 <br><br> FS サーバー上で次のコマンドAD実行します。 <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | フェデレーション認証組織 | 必須アクション。 不作為により、移行中にサービスに影響が生じします。  |
| グローバル Azure クライアント エンドポイントの証明書利用者信頼AD生成します。 | お客様は、グローバル エンドポイントへの証明書利用者信頼 (RPT) を手動で [作成する](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 必要があります。 これを行うのは、グローバル フェデレーション メタデータ URL を利用し [、Azure AD RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) 要求規則 (AD FS ヘルプ) を使用して要求規則を生成し、RPT にインポートすることで、GUI を介して新しい RPT を追加します。 | フェデレーション認証組織 | 必須アクション。 不作為により、移行中にサービスに影響が生じします。 |
|||||

## <a name="more-information"></a>詳細

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

移行を進む:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-add-devices.md)[デバイス](ms-cloud-germany-transition-azure-ad.md)、[エクスペリエンス、および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
