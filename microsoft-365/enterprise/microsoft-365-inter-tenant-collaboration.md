---
title: Microsoft 365 テナント間のコラボレーション
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Microsoft 365 コラボレーションがテナントと組織の間でどのように動作するかについて説明します。これにより、さまざまな組織が安全に共同作業できる
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00eacfc21d3223b5b9a1ad420cd5d1d85bf4ea8e
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384829"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 テナント間のコラボレーション

Fabrikam と Contoso という2つの組織に Microsoft 365 for business テナントがあり、複数のプロジェクトで共同作業をするとします。一部のは限られた期間だけ実行され、その一部は継続しています。 Fabrikam および Contoso 社が、セキュリティで保護された方法で、さまざまな Microsoft 365 テナント間でより効果的に共同作業を行えるようになります。 Microsoft 365 と Azure Active Directory (Azure AD) B2B コラボレーションを組み合わせて使用すると、いくつかのオプションが提供されます。 この記事では、Fabrikam と Contoso が検討できるいくつかの重要なシナリオについて説明します。
  
Microsoft 365 のテナント間コラボレーションオプションには、ファイルと会話のための集中的な場所の使用、予定表の共有、IM の使用、通信用音声ビデオ通話、およびリソースとアプリケーションへのアクセスの保護があります。 次の表を使用して、解決策を選択し、詳細をご確認ください。
  
## <a name="exchange-online-collaboration-options"></a>Exchange Online のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|他の Microsoft 365 組織と予定表を共有する |管理者は、Exchange Online でさまざまなレベルの予定表アクセスを設定して、企業が他の企業と共同作業したり、ユーザーが他のユーザーとスケジュール (空き時間情報) を共有したりできるようにすることができます。 | <ul><li>[共有](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) </li><li> [組織の関係](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) </li><li> [組織の関係の作成](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) </li><li> [組織の関係を変更する ](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) </li><li> [組織の関係の削除](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) </li><li> [予定表を外部ユーザーと共有する](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|ユーザーが組織外のユーザーと予定表を共有する方法を制御する | 管理者は、共有ポリシーをユーザーのメールボックスに適用して、共有できるユーザーと付与するアクセス レベルを制御します。 |  <ul><li> [共有ポリシー](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) </li><li> [共有ポリシーの作成](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) </li><li> [メールボックスに共有ポリシーを適用する](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) </li><li> [共有ポリシーの変更、無効化、削除](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) </li></ul> |
|セキュリティ保護されたメール チャネルを構成し、パートナー組織とのメール フローを制御する | 管理者は、パートナー組織またはサービス プロバイダーとのメール交換にセキュリティを適用するコネクタを作成します。 コネクタは、トランスポート層セキュリティ (TLS) による暗号化を適用するだけでなく、パートナーがメールを送信する際のドメイン名または IP アドレス範囲に対する制限を許可します。 |  <ul><li> [Exchange Online が TLS を使用して電子メール接続をセキュリティで保護する方法](https://technet.microsoft.com/library/mt163898.aspx) </li><li> [コネクタを使用してメール フローを構成する](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) </li><li> [リモート ドメイン](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) </li><li> [パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) </li><li> [メールフローのベストプラクティス (概要)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint Online と OneDrive for Business のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|外部ユーザーとサイトおよびドキュメントを共有する | 管理者は、認証された Microsoft アカウント、認証された職場または学校のアカウント、ゲスト アカウントのいずれかに対して、テナント レベルまたはサイト コレクション レベルでの共有を構成します。 |  <ul><li> [SharePoint Online 環境の外部共有を管理する](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) </li><li> [SharePoint Online を企業間 (B2B) エクストラネット ソリューションとして使用する](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|エンド ユーザーの外部共有を把握して制御する | OneDrive for Business ファイルの所有者および SharePoint Online エンド ユーザーは、サイト共有とドキュメント共有を構成し、共有を把握するための通知を確立します。 |  <ul><li> [OneDrive for Business の外部共有に対する通知をオンにする](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [SharePoint のファイルまたはフォルダーを共有する](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>Skype for Business のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Skype for Business Online - 他の Skype for Business ユーザーとの IM、通話、プレゼンス | 管理者は、Skype for Business Online ユーザーに対して、IM、音声ビデオ通話、および別の Microsoft 365 テナントのユーザーとのプレゼンスの表示を有効にすることができます。 | [ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|Skype for Business Online - Skype (コンシューマー) ユーザーとの IM、通話、プレゼンス | 管理者は、Skype for Business Online ユーザーが Skype (コンシューマー) ユーザーとの IM、オーディオ/ビデオ通話、プレゼンスの表示を行えるようにすることができます。 | [Skype for Business ユーザーが Skype の連絡先を追加できるようにする](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Azure AD B2B のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Azure AD B2B コラボレーション - 組織のディレクトリ内のグループに外部ユーザーを追加することによるコンテンツ共有 | 1つの Microsoft 365 テナントのグローバル管理者は、自分のディレクトリに参加するために別の Microsoft 365 テナント内のユーザーを招待したり、それらの外部ユーザーをグループに追加したり、そのグループの SharePoint サイトやライブラリなどのコンテンツへのアクセス権を付与したりすることができます。 |  <ul><li> [Azure AD B2B コラボレーション プレビューとは何か?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: 新しい更新で企業間のコラボレーションが簡単に](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [外部共有および Azure Active Directory B2B コラボレーション](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory の B2B コラボレーションの API とカスタマイズ](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD と ID の表示： Azure AD B2B コラボレーション (企業間)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 コラボレーションオプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Microsoft 365 グループ-電子メール、予定表、OneNote、および共有ファイルを中央に配置する | グループは、Business Essentials プラン、Business Premium プラン、Education プラン、Enterprise E1、E3、E5 プランでサポートされています。 1つの Microsoft 365 テナントのユーザーは、グループを作成し、ゲストユーザーとして別の Microsoft 365 テナント内のユーザーを招待することができます。 Dynamics CRM にも適用されます。 |  <ul><li> [Microsoft 365 グループについて](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [ゲストを Microsoft 365 グループに追加する](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Microsoft 365 グループを展開する](https://technet.microsoft.com/library/dn896591.aspx) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Yammer のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Yammer - エンタープライズ ソーシャル メディアを通じたコラボレーション | Yammer 管理者によって外部グループを作成する機能が無効にされていない限り、ユーザーは Yammer での会話によるコラボレーションを行うための外部グループを作成し、記事のいいね! 評価とフォロー、ファイルの共有、チャットをオンラインで行うことができます。 | [Yammer の外部グループを作成して管理する](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Teams のコラボレーション オプション

|共有の目的|管理操作|使い方に関する情報|
|:-----|:-----|:-----|
|組織外のユーザーと Teams でコラボレーションを行う | Microsoft 365 テナントへの招待のグローバル管理者は、Teams での外部コラボレーションを有効にする必要があります。 グローバル管理者とチームの所有者は、Teams でコラボレーションを行うために、メール アドレスを持つすべてのユーザーを招待できるようになります。  <br/> 管理者は、既にテナント内にいるゲストを管理して編集することもできます。 |  <ul><li> [ゲスト アクセスを認証する](https://docs.microsoft.com/microsoftteams/teams-dependencies) </li><li> [Teams でゲスト アクセスをオンまたはオフにする](https://docs.microsoft.com/microsoftteams/set-up-guests) </li><li> [PowerShell を使用してゲスト アクセスを制御する](https://docs.microsoft.com/microsoftteams/guest-access-powershell) </li><li> [ゲスト アクセスのチェックリスト](https://docs.microsoft.com/microsoftteams/guest-access-checklist) </li><li> [ゲスト ユーザーを表示する](https://docs.microsoft.com/microsoftteams/view-guests) </li><li> [ゲスト ユーザー情報を編集する](https://docs.microsoft.com/microsoftteams/edit-guests-information) </li></ul> |
|チームの所有者は、ゲストを招待し、ゲストがチーム内でコラボレーションを行う方法を管理することができる。  |チームの所有者は、自分のチーム内でゲストが実行できる操作をさらに制御することができます。 |  <ul><li> [ゲストを追加する](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [チームにゲストを追加する](https://docs.microsoft.com/microsoftteams/add-guests) </li><li> [Teams でのゲスト アクセスを管理する](https://docs.microsoft.com/microsoftteams/manage-guests) </li><li> [チームまたはチャネルにいるユーザーを確認する](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|他のテナントからのゲストは、Teams 内のコンテンツを表示し、他のメンバーとコラボレーションすることができる | なし。 | [ゲストのエクスペリエンスについて](https://docs.microsoft.com/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Power BI のコラボレーション オプション

| 共有の目的 | 管理操作 | 使い方に関する情報 |
|:-----|:-----|:-----|
|Power BI を使用すれば、外部ゲスト ユーザーはリンクを介して共有されたコンテンツを使用できます。 これにより、組織内のユーザーは、セキュリティで保護された方法で組織全体にコンテンツを配布できます。<br/> | Power BI 管理者は、ユーザーが組織内のコンテンツを表示するために外部ユーザーを招待できるかどうかを制御できます。| [Azure AD B2B で外部ゲスト ユーザーに Power BI コンテンツを配布する](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 テナント間のコラボレーションについて知っておくべきポイント

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>ユーザー アカウント、ライセンス、サブスクリプション、および記憶域の共有

各組織は、独自のユーザー アカウント、ID、セキュリティ グループ、サブスクリプション、ライセンス、および記憶域を保持しています。 ユーザーは Microsoft 365 のグループ作業機能を使用して、会社の資産の管理を維持しながら、必要な情報にアクセスできるようにすることができます。
  
- **ユーザーアカウント:** オンプレミスの Active Directory ドメインサービスのテナントまたはパーティション間でアカウントを共有または複製することはできません。 
    
- **ライセンス &amp; サブスクリプション:** microsoft 365 では、ライセンスプラン (Sku または Microsoft 365 プランとも呼ばれる) からのライセンスが、これらのプランに対して定義されている Microsoft 365 サービスにアクセスできるようにします。 
    
- **ストレージ:** Microsoft 365 のライセンスプランでは、ソフトウェアの境界および SharePoint Online の制限は、メールボックスの格納域の制限とは別に管理されます。 メールボックスの保存制限は、Exchange Online を使用して設定および管理されます。 どちらのシナリオでも、テナント間で記憶域を共有することはできません。 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Microsoft 365 テナント間でドメイン名前空間を共有できますか。

いいえ。 Fabrikam.com や tailspintoys.com などの組織のドメイン名は、1つの Microsoft 365 テナントでのみ関連付けおよび使用できます。 各テナントは独自の名前空間を持っている必要があります。 UPN、SMTP、および SIP の名前空間をテナント間で共有することはできません。
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>ハイブリッドコンポーネントと Microsoft 365 のテナント間のコラボレーションについて

Exchange 組織や Azure AD Connect などのオンプレミスのハイブリッド コンポーネントは、複数のテナント間で分割することはできません。
 

