---
title: 新しいドイツのデータセンター リージョンOffice 365 サービスへの移行に関する変更点
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
description: '概要: Microsoft Cloud Germany (Microsoft Cloud Deutschland) から新しいドイツデータセンター リージョンの Office 365 サービスへの移行に関して何が変更されたのかを理解します。'
ms.openlocfilehash: 0415f7b95cb9a9f2625798311946dac0f1f7c2c0
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688624"
---
# <a name="what-has-changed-for-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター リージョンOffice 365 サービスへの移行に関する変更点

テナントの移行は、管理者とユーザーへの影響を最小限に抑える目的で設計されています。 ただし、各ワークロードごとに考慮事項があります。 ワークロードの移行エクスペリエンスをより深く理解するには、以下のセクションを参照してください。

新しいドイツのデータセンター リージョンにおける Microsoft Cloud Deutschland と Office 365 サービスの主な違いを次に示します。

| カテゴリ | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | 新しいドイツのデータセンター リージョンでの Office 365 サービス |
|:-------|:-----|:-------|
| 1 つの Office 365 テナントのみでサブスクリプションに利用可能な Microsoft 365 サービス | 15 サービス | 29 サービス <br><br> 詳細については [、「365](ms-cloud-germany-transition.md#serv-avail)クラウド サービスの異なるサービスの可用性Officeを参照してください。 |
| 新機能 | 利用可能な新機能はありません。 | 新しい機能は、365 の Officeと一致します。 |
| データ トラスティ | はい | いいえ |
| グローバルな Office 365 テナントでのテナント間コラボレーション | いいえ | はい |
| 顧客データの常駐 | 顧客データはドイツのデータ センター内にのみ保存されます。 | Microsoft は、ドイツ内で次の顧客データを排他的に保存します。 <ul><li> Exchange Online メールボックスの内容 (電子メールの本文、予定表のエントリ、および電子メールの添付ファイルの内容) </li><li> SharePoint Online サイトのコンテンツと、そのサイト内に保存されているファイル、および OneDrive for Business にアップロードされたファイル </li></ul> |
| 該当する条件 | [この補足を含むオンライン](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) サービスの [使用条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [オンライン サービスの使用条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

変更されていないもの:

- テナント ID (GUID) とカスタム ドメインを持つテナント初期ドメイン (GUID など) は、移行後 `contoso.onmicrosoft.de` も保持されます。 

- Office 365 サービスに移行されるリソースの認証要求は、Office 365 サービス Azure 認証サービス ( ) によって付与されます `login.microsoftonline.com` 。 移行中、365 Germany Officeに残っているリソースは、既存のドイツの Azure サービス ( ) によって認証されます `login.microsoftonline.de` 。

次の点に注意してください。

- 管理ドメイン アカウントの場合、最初の Azure Active Directory (Azure AD) テナントのコピーが完了した後 (Azure AD から Office 365 サービス Azure AD サービスへの移行の最初の手順)、パスワードの変更、セルフサービス によるパスワードのリセット (SSPR) の変更、および管理者によるパスワードのリセットは、Office 365 サービス ポータルから行う必要があります。 この時点では、Azure AD テナントが Office 365 サービスに移行されたため、ドイツ サービスからのパスワードの更新要求は成功しません。 フェデレーション ドメイン パスワードのリセットは、オンプレミスのディレクトリで完了するから影響を受け取らない。

- Azure サインインは、ユーザーがアクセスを試みるポータルに表示されます。 監査ログは、移行後、Office 365 サービス エンドポイントからのみ利用できます。 移行が完了する前に、Microsoft Cloud Deutschland ポータルからサインインと監査ログを保存する必要があります。

- 管理された組織 (Active Directory フェデレーション サービスを使用していない) の管理者によるパスワードのリセット、パスワードの変更、パスワードのリセットは、Office 365 サービス ポータルを介して実行する必要があります。 Microsoft Cloud Deutschland ポータルにアクセスしてパスワードをリセットするユーザーによる試行は失敗します。

- 一般データ保護規則 (GDPR) データ主体要求 (DSR) は、今後の要求に対して Office 365 サービス Azure 管理ポータルから実行されます。 Microsoft Cloud Deutschland に常駐している従来の診断データまたは顧客以外の診断データは、30 日以内に削除されます。

## <a name="subscriptions--licenses"></a>Subscriptions & Licenses

- Office 365 サブスクリプションと Microsoft Cloud Deutschland からの Dynamics サブスクリプションは、Azure を再配置してドイツリージョンADされます。 その後、組織は更新され、新しい Office 365 サービス サブスクリプションが反映されます。 サブスクリプションの簡単な転送プロセス中に、サブスクリプションへの変更はブロックされます。

- テナントが Office 365 サービスに移行すると、ドイツ固有のサブスクリプションとライセンスは、新しい Office 365 サービス製品で標準化されます。 対応Office 365 サービス サブスクリプションは、移行されたドイツのサブスクリプションに対して購入されます。 ドイツのライセンスを持つユーザーには、365 Officeライセンスが割り当てられます。 完了すると、従来のドイツのサブスクリプションがキャンセルされ、現在の Office 365 サービス テナントから削除されます。

- 個々のワークロードの移行後、新しい Office 365 サービス サブスクリプションにより、Office 365 サービス (Microsoft Planner や Microsoft Flow など) を通じて追加の機能が利用できます。 組織に適した場合、テナント管理者またはライセンス管理者は、新しいサービスを導入する変更管理を計画する場合に、新しいサービス プランを無効にできます。 ユーザーのライセンスに割り当てられているサービス プランを無効にする方法については、「ユーザー ライセンスの割り当て中に [Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)サービスへのアクセスを無効にする」を参照してください。

## <a name="exchange-online"></a>Exchange Online

- Exchange リソース URL は、移行後に従来のドイツ のエンドポイントから `outlook.office.de` Office 365 サービス エンドポイント `outlook.office365.com` に移行します。 移行が完了するまで、ユーザーは従来の URL を使用して移行したメールボックスにアクセスできます。 お客様は、ドイツ環境のサポートが完了しないように、Exchange の移行が開始された後、できるだけ早くユーザーを新しい URL に移行する必要があります。 Outlook Office 365 サービス URL は、Exchange の移行が開始された後にのみ使用できます。

- メールボックスはバックエンド プロセスとして移行されます。 組織内のユーザーは、移行中に Microsoft Cloud Deutschland またはドイツの地域にいて、同じ Exchange 組織の一部である場合があります (同じグローバル アドレス一覧に含む)。

- メールボックスが存在Outlook Web App URL を使用してサービスにアクセスするユーザーには、追加の認証プロンプトが表示されます。 たとえば、ユーザーのメールボックスが Office 365 サービス内にいて、ユーザーの Outlook Web App 接続がレガシ エンドポイントを使用している場合、ユーザーは最初に認証を受け、次に次に行います `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` 。 移行が完了すると、ユーザーは新しい URL ( ) にアクセスできます。ユーザーには、想定される 1 つのサインイン要求だけが `https://outlook.office365.com` 表示されます。 

## <a name="office-services"></a>Office サービス

Office、移行前と移行中にオンライン `office.de` サービスにアクセスできます。 ユーザーのメールボックスが Office 365 サービスに移行された後、ユーザーは Office 365 サービス URL の使用を開始する必要があります。 以降のワークロードが Office 365 サービスに移行すると、office.comポータルからのインターフェイスが機能し始める予定です。

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Exchange Online Protection (EOP) のバック エンド機能は、新しいドイツ地域にコピーされます。
- Office 365 セキュリティ/コンプライアンス センターのユーザーは、移行の一環としてグローバル URL の使用 `https://protection.office.com` に移行する必要があります。

## <a name="skype-for-business-online"></a>Skype for Business Online

既存の Skype for Business Online の顧客は Microsoft Teams へと移行されます。 詳細については、以下を参照してください [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) 。

## <a name="office-365-video"></a>Office 365 ビデオ

Office 365 Video is being retired on March 1, 2021, and Office 365 Video won't be supported after migration of SharePoint Online to the new German datacenter regions is completed. Office 365 ビデオのコンテンツは、SharePoint Online の移行の一環として移行されます。 ただし、Office 365 Video のビデオは、SharePoint の移行後に Office 365 ビデオ UI で再生されません。 Office [365 Video transition to Microsoft Stream (classic) overview の](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)移行タイムラインについて説明します。

## <a name="next-step"></a>次の手順

[移行フェーズのアクションと影響について理解する](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>詳細

はじめに:

- [Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)

移行を進む:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-add-devices.md)[デバイス](ms-cloud-germany-transition-azure-ad.md)、[エクスペリエンス、および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
