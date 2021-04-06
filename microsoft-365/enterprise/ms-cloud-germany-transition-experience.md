---
title: 新しいドイツのデータセンター地域Office 365 サービスへの移行後の変更点
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター地域の Office 365 サービスへの移行に関する変更点について説明します。'
ms.openlocfilehash: 74ad9a662d3ea7a68ef1f82961864eb4468f6098
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591782"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター地域Office 365 サービスへの移行後の変更点

テナントの移行は、管理者とユーザーに対する影響を最小限に抑える設計です。 ただし、各ワークロードごとに考慮事項があります。 ワークロードの移行エクスペリエンスについて理解を深めるには、次のセクションを参照してください。

新しいドイツのデータセンター地域における Microsoft Cloud Deutschland と Office 365 サービスの主な違いは次のとおりです。

| カテゴリ | Microsoft Cloud Germany (Microsoft Cloud Deutschland) | 新しいドイツのデータセンター リージョンでの Office 365 サービス |
|:-------|:-----|:-------|
| 1 つの Office 365 テナントのみでサブスクリプションに利用可能な Microsoft 365 サービス | 15 サービス | 29 サービス <br><br> 詳細については [、「365](ms-cloud-germany-transition.md#serv-avail)クラウド サービスの異なるサービス間のOfficeとは」を参照してください。 |
| 新機能 | 新しい機能は利用できません。 | 新しい機能は、365 サービスOffice利用できます。 |
| データ トラスティ | はい | いいえ |
| グローバルな Office 365 テナントでのテナント間コラボレーション | いいえ | はい |
| 顧客データの常駐 | 顧客データはドイツのデータ センター内にのみ保存されます。 | Microsoft は、ドイツ内で次の顧客データを保存します。 <ul><li> ExchangeOnline メールボックスのコンテンツ (メール本文、予定表のエントリ、メール添付ファイルのコンテンツ) </li><li> SharePoint Online サイトのコンテンツと、そのサイト内に保存されているファイル、および OneDrive for Business にアップロードされたファイル </li></ul> |
| 該当する条件 | [この補足を含む](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) オンライン サービス [の利用規約](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [オンライン サービスの使用条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

変更されていないもの:

- テナント ID (GUID) とカスタム ドメインを持つテナントの初期ドメイン (など) は、移行後 `contoso.onmicrosoft.de` も保持されます。 

- 365 サービスに移行されるリソースOffice認証要求は、Office 365 サービス Azure 認証サービス ( ) によって付与されます `login.microsoftonline.com` 。 移行中、365 ドイツの 365 に残っているOfficeは、既存のドイツ Azure サービス () によって認証されます `login.microsoftonline.de` 。

注意すべき考慮事項:

- 管理ドメイン アカウントの場合、最初の Azure Active Directory (Azure AD) テナントのコピーが完了した後 (これは、Azure AD Office の azure AD サービスへの移行の最初の手順です)、パスワードの変更、セルフサービス パスワードリセット (SSPR) の変更、管理者によるパスワードリセットは、Office 365 サービス ポータルから行う必要があります。 この時点では、Azure AD Office テナントが 365 サービスに移行されたため、ドイツ のサービスからパスワードを更新する要求は成功しません。 フェデレーション ドメイン パスワードのリセットは、オンプレミス ディレクトリで完了しますので、影響を受け取る必要はありません。

- Azure サインインは、ユーザーがアクセスを試みるポータルに表示されます。 監査ログは、移行後Office 365 サービス エンドポイントからのみ利用できます。 移行が完了する前に、サインインログと監査ログを Microsoft Cloud Deutschland ポータルから保存する必要があります。

- 管理組織 (Active Directory フェデレーション サービスを使用していない) の管理者によるパスワードのリセット、パスワードの変更、パスワードのリセットは、Office 365 サービス ポータルを介して実行する必要があります。 Microsoft Cloud Deutschland ポータルにアクセスしてパスワードをリセットするユーザーによる試行は失敗します。

- 一般データ保護規則 (GDPR) データ主体要求 (DSR) は、将来の要求に対して Office 365 サービス Azure 管理ポータルから実行されます。 Microsoft Cloud Deutschland に常駐している従来の診断データまたは顧客以外の診断データは、30 日以内に削除されます。

## <a name="subscriptions--licenses"></a>サブスクリプション&ライセンス

- Office 365 サブスクリプションと Microsoft Cloud Deutschland からの Dynamics サブスクリプションは、Azure の移行に伴いドイツADされます。 その後、組織は新しい 365 サービス Office反映するように更新されます。 短いサブスクリプション転送プロセス中に、サブスクリプションへの変更はブロックされます。

- テナントが Office 365 サービスに移行すると、ドイツ固有のサブスクリプションとライセンスは、新しい Office 365 サービスサービスと標準化されます。 365 Officeに対応するサブスクリプションは、転送されたドイツのサブスクリプションに対して購入されます。 ドイツのライセンスを持つユーザーには、365 Officeライセンスが割り当てられます。 完了すると、従来のドイツのサブスクリプションが取り消され、現在の 365 サービス Officeから削除されます。

- 個々のワークロードの移行後、新しい Office 365 サービス サブスクリプションのために、Office 365 サービス (Microsoft Planner や Microsoft Flow など) を通じて追加の機能が利用できます。 組織に適した場合、テナントまたはライセンス管理者は、新しいサービスを導入する変更管理を計画している間、新しいサービス プランを無効にできます。 ユーザーのライセンスに割り当てられているサービス プランを無効にする方法のガイダンスについては、「ユーザー ライセンスの割り当て中に [Microsoft 365](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)サービスへのアクセスを無効にする」を参照してください。

## <a name="exchange-online"></a>Exchange Online

- Exchange リソース URL は、移行後に従来のドイツ `outlook.office.de` のエンドポイントから Office 365 サービス エンドポイント `outlook.office365.com` に移行します。 移行が完了するまで、ユーザーは従来の URL を使用して移行されたメールボックスにアクセスできます。 お客様は、ドイツ環境の削除に影響を与えかねない Exchange 移行が開始された後、できるだけ早くユーザーを新しい URL に移行する必要があります。 Outlook Office 365 サービス URL は、Exchange の移行が開始された後にのみ利用できます。

- メールボックスはバックエンド プロセスとして移行されます。 組織内のユーザーは、移行中に Microsoft Cloud Deutschland またはドイツ地域にいて、同じ Exchange 組織の一部 (同じグローバル アドレス一覧に含む) に含む場合があります。

- メールボックスが存在Outlook Web App URL を使用してサービスにアクセスするユーザーには、追加の認証プロンプトが表示されます。 たとえば、ユーザーのメールボックスが Office 365 サービス内にいて、ユーザーの Outlook Web App 接続がレガシ エンドポイントを使用している場合、ユーザーは最初に認証を行い、次ににを使用します `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` 。 移行が完了すると、ユーザーは新しい URL ( ) にアクセスし、予想される 1 つのサインイン要求 `https://outlook.office365.com` のみを表示します。 

## <a name="office-services"></a>Office サービス

Office移行前と移行中にオンライン `office.de` サービスにアクセスできます。 ユーザーのメールボックスが 365 サービスの Officeに移行された後、ユーザーは 365 サービス URL のOffice開始する必要があります。 以降のワークロードが 365 サービスOffice移行すると、そのサービスのインターフェイスが office.com 動作し始める。

Office で最も最近使用された (MRU) サービスは、移行ではなく、Microsoft Cloud Deutschland から Office 365 Global サービスへの切り替えです。 365 Global services 側Office MRU リンクだけが、ポータルから移行した後 Office.com されます。 Microsoft Cloud Deutschland からの MRU リンクは、365 グローバル サービスの MRU Office表示されません。 365 Officeグローバル サービスでは、MRU リンクにアクセスできるのは、テナントの移行がフェーズ 9 に達した後のみです。

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Exchange Online Protection (EOP) のバック エンド機能は、新しいドイツ地域にコピーされます。
- Office 365 セキュリティ とコンプライアンス センターのユーザーは、移行の一環として、グローバル URL の使用 `https://protection.office.com` に移行する必要があります。

## <a name="skype-for-business-online"></a>Skype for Business Online

既存の Skype for Business Online の顧客は Microsoft Teams へと移行されます。 詳細については、「」 を参照してください [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) 。

## <a name="office-365-video"></a>Office 365 ビデオ

Office 365 ビデオは 2021 年 3 月 1 日に廃止され、Office 365 ビデオは SharePoint Online の新しいドイツのデータセンター地域への移行が完了した後はサポートされません。 365 Officeコンテンツは、SharePoint Online の移行の一環として移行されます。 ただし、Office 365 ビデオのビデオは、SharePoint の移行後に Office 365 ビデオ UI で再生されません。 Microsoft Stream (クラシック) への 365 ビデオOffice移行のタイムラインの詳細については [、「概要」を参照してください](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="next-step"></a>次の手順

[移行フェーズのアクションと影響について理解する](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツのデータセンター地域Office 365 サービスへの Microsoft Cloud Deutschland からの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)

切り替えの移動:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、デバイス](ms-cloud-germany-transition-add-devices.md)[、](ms-cloud-germany-transition-azure-ad.md)[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、および FS のAD[情報](ms-cloud-germany-transition-add-adfs.md)です。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移行プログラム情報](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams へのアップグレードを開始する](/microsoftteams/upgrade-start-here)
