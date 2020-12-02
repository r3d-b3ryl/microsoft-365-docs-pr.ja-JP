---
title: 新しいドイツのデータセンター リージョンの Office 365 サービスへの移行中のカスタマー エクスペリエンス
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: '概要: 新しいドイツ語のデータセンターリージョンで、Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸陸地) から Office 365 サービスへの移行の実績を理解します。'
ms.openlocfilehash: a44fbe504a9a710856deeb3baf258feb124ce7ae
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551697"
---
# <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター リージョンの Office 365 サービスへの移行中のカスタマー エクスペリエンス

テナントの移行は、管理者およびユーザーへの影響が最小限になるように設計されています。 ただし、各ワークロードごとに考慮事項があります。 以下のセクションを確認して、ワークロードの移行環境をより深く理解してください。

以下は、新しいドイツデータセンターリージョンにおける Microsoft Cloud Deut上陸陸と Office 365 サービスの主な違いを示しています。

| カテゴリ | Microsoft Cloud Deut上陸陸 (Microsoft Cloud Deut上陸陸) | 新しいドイツのデータセンター リージョンでの Office 365 サービス |
|:-------|:-----|:-------|
| 1 つの Office 365 テナントのみでサブスクリプションに利用可能な Microsoft 365 サービス | 15個のサービス | 29サービス <br><br> 詳細については、「 [Office 365 クラウドサービスの各オファーリング間のサービスの可用性](ms-cloud-germany-transition.md#serv-avail)について」を参照してください。 |
| 新機能 | 利用可能な新機能はありません。 | 新機能は Office 365 サービスと一貫性のある状態で利用可能になります。 |
| データ トラスティ | はい | いいえ |
| グローバルな Office 365 テナントでのテナント間コラボレーション | いいえ | はい |
| 顧客データの常駐 | 顧客データは、ドイツのデータセンターのみに格納されます。 | Microsoft は、次の顧客データをドイツ内で排他的に保存します。 <ul><li> Exchange Online メールボックスのコンテンツ (電子メール本文、予定表のエントリ、電子メールの添付ファイルの内容) </li><li> SharePoint Online サイトのコンテンツと、そのサイト内に格納されているファイル、および OneDrive for Business にアップロードされたファイル </li></ul> |
| 該当する条件 | この[補足](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64)事項を含む[オンラインサービスの用語](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) | [オンライン サービスの使用条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

変更はありません。

- テナント ID (GUID) のテナントの初期ドメイン (など `contoso.onmicrosoft.de` ) とカスタムドメインは、移行後も保持されます。 

- Office 365 サービスに移行されるリソースに対する認証要求は、Office 365 services Azure authentication service () によって付与され `login.microsoftonline.com` ます。 移行中は、まだ Office 365 ドイツに残っているリソースは、既存のドイツ Azure サービス () によって認証され `login.microsoftonline.de` ます。

注意事項:

- 管理ドメインアカウントの場合は、最初の Azure Active Directory (Azure ad) テナントのコピーが完了した後 (azure ad migration の最初のステップは azure ad サービス365へ)、パスワードの変更、セルフサービスのパスワードリセット (SSPR) の変更、および管理者によるパスワードのリセットは、Office 365 サービスポータルから行う必要があります。 ドイツサービスからパスワードを更新する要求は、この時点では成功しません。これは、Azure AD テナントが Office 365 services に移行されているためです。 フェデレーションドメインパスワードのリセットは、オンプレミスディレクトリで完了するため、影響を受けません。

- Azure サインインは、ユーザーがアクセスを試みるポータルに表示されます。 監査ログは、移行後に Office 365 services エンドポイントからのみ利用可能です。 移行を完了する前に、Microsoft Cloud Deutschland ポータルから、サインインと監査ログを保存する必要があります。

- パスワードのリセット、パスワードの変更、管理者によるパスワードのリセット (Active Directory フェデレーションサービスを使用していない) は、Office 365 services ポータルを介して実行する必要があります。 Microsoft Cloud Deut上陸ランドポータルにアクセスしてパスワードをリセットするユーザーによる試行は失敗します。

- 一般的なデータ保護規則 (GDPR) データ主体要求 (DSRs) は、Office 365 services Azure 管理ポータルから今後の要求に対して実行されます。 Microsoft Cloud Deut上陸土地に含まれるレガシーまたはお客様以外の診断データは30日以上削除されます。

## <a name="subscriptions--licenses"></a>サブスクリプション & ライセンス

- Office 365 と Dynamics サブスクリプションは、Azure AD 再配置を使用して、ドイツ地域に移行されます。 その後、組織は新しい Office 365 サービスサブスクリプションを反映するように更新されます。 短時間のサブスクリプション転送プロセスでは、サブスクリプションへの変更がブロックされます。

- テナントが Office 365 services に移行されるにつれて、ドイツ固有のサブスクリプションとライセンスが新しい Office 365 サービス製品で標準化されます。 対応する Office 365 サービスサブスクリプションは、転送されるドイツのサブスクリプションに対して購入されます。 ドイツのライセンスを持つユーザーには、Office 365 サービスのライセンスが割り当てられます。 完了すると、従来のドイツのサブスクリプションがキャンセルされ、現在の Office 365 services テナントから削除されます。

- 個々のワークロードを移行した後は、新しい Office 365 サービスサブスクリプションのために、Office 365 サービス (Microsoft Planner や Microsoft Flow など) を通じて追加機能を利用できるようになります。 組織にとって適切な場合、テナントまたはライセンス管理者は新しいサービスを導入するために変更管理を計画する際に、新しいサービスプランを無効にすることができます。 ユーザーのライセンスに割り当てられているサービスプランを無効にする方法のガイダンスについては、「 [ユーザーライセンスの割り当て中に Microsoft 365 サービスへのアクセスを無効](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)にする」を参照してください。

## <a name="exchange-online"></a>Exchange Online

- 移行後に、従来のドイツエンドポイントから `outlook.office.de` Office 365 services エンドポイントに移行する Exchange リソース url。 `outlook.office365.com` 移行が完了するまで、ユーザーは従来の URL を使用して移行されたメールボックスにアクセスできます。 お客様は、Exchange の移行が開始されてから、ドイツ環境の廃棄に影響が出ないように、できるだけ早くユーザーを新しい URL に移行する必要があります。 Outlook サービスの Office 365 サービスの Url は、Exchange の移行が開始された後にのみ使用可能になります。

- メールボックスは、バックエンドプロセスとして移行されます。 組織内のユーザーは、移行時に Microsoft Cloud Deut上陸陸またはドイツ地域のいずれかに属しており、同じ Exchange 組織 (同じグローバルアドレス一覧) に含まれている場合があります。

- メールボックスが存在しない URL を使用してサービスにアクセスする Outlook Web App のユーザーには、その他の認証プロンプトが表示されます。 たとえば、ユーザーのメールボックスが Office 365 サービス内にあり、ユーザーの Outlook Web App 接続が従来のエンドポイントを使用している場合、 `outlook.office.de` ユーザーは最初にを認証して `login.microsoftonline.de` からになり `login.microsoftonline.com` ます。 移行が完了すると、ユーザーは新しい URL () にアクセスできるようになります。これには、 `https://outlook.office365.com` 1 つの予期されるサインイン要求のみが表示されます。 

## <a name="office-services"></a>Office サービス

Office Online サービスには `office.de` 、移行の前と移行時からアクセスできます。 ユーザーのメールボックスが Office 365 サービスに移行した後、ユーザーは Office 365 サービス Url の使用を開始する必要があります。 その後のワークロードが Office 365 サービスに移行すると、office.com ポータルからのインターフェイスが機能し始めます。

## <a name="exchange-online-protection"></a>Exchange Online Protection

- バックエンド Exchange Online Protection (EOP) の機能は、新しいドイツ地域にコピーされます。
- Office 365 セキュリティ/コンプライアンスセンターのユーザーは、 `https://protection.office.com` 移行の一環として、グローバル url を使用するように移行する必要があります。

## <a name="skype-for-business-online"></a>Skype for Business Online

既存の Skype for Business Online の顧客は Microsoft Teams へと移行されます。 詳細については、「」を参照してください [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) 。

## <a name="office-365-video"></a>Office 365 ビデオ

Office 365 のビデオは、2021年3月1日に廃止されました。 SharePoint Online を新しいドイツ語のデータセンターリージョンに移行した後は、Office 365 のビデオはサポートされません。 Office 365 ビデオのコンテンツは、SharePoint Online の移行の一環として移行されます。 ただし、Office 365 のビデオは、SharePoint の移行後に Office 365 Video UI では再生されません。 Office 365 の移行タイムラインの詳細については、 [「Microsoft Stream (クラシック) に移行する」を](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)参照してください。

## <a name="next-step"></a>次のステップ

[移行フェーズのアクションと影響について理解する](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>詳細情報

はじめに:

- [新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)

遷移を移動します。

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の準備作業](ms-cloud-germany-transition-add-pre-work.md)
- [サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。

クラウドアプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
