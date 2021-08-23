---
title: Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行
ms.author: andyber
author: andybergen
manager: laurawi
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
description: '概要: 新しいドイツのデータセンター リージョンで、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から Office 365 サービスへの移行について理解します。'
ms.openlocfilehash: e301f58c3a194c6af8989f4081e733c50a4c104e
ms.sourcegitcommit: 9469d16c6bbd29442a6787beaf7d84fb7699c5e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58400333"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Microsoft Cloud Deutschland から新しいドイツのデータセンター地域Office 365サービスへの移行

> [!NOTE]
> この記事は、対象となる Microsoft Cloud Deutschland のお客様にのみ適用されます。

2018 年 8 月、Microsoft は、お客様のデジタル変換をより良く実現するために、ドイツの新しいクラウド地域から完全な Microsoft クラウド (Azure、Office 365、Dynamics 365、Power Platform) を提供する意向を発表しました。 2019 年 8 月に、ドイツで新しいクラウド リージョンを開設する準備を進めていることを発表しました。 その後、Azure、Office 365、Dynamics 365、および Power プラットフォームの可用性を発表しました。

新しい地域は、より柔軟に、最新のインテリジェント クラウド サービス、Microsoft 365 サービス クラウド ネットワークへの完全な接続、およびドイツ内の顧客データ常駐により、ドイツのお客様の進化するニーズに対応するように設計されています。

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター地域に移行する方法

既存の Microsoft Cloud Deutschland のお客様は、Office 365、Dynamics 365 Customer Engagement、および Power Platform のお客様の移行を開始できます。 最初のステップは、新しいドイツのデータセンター リージョンへの [Microsoft 主導の移行にオプトインする](./ms-cloud-germany-migration-opt-in.md)ことです。

Microsoft によるアプローチにオプトインする組織では、移行は 2021 年初めに開始され、2021 年 10 月 29 日までに完了する予定です。 移行の結果、主要な顧客データおよびサブスクリプションは新しいドイツ リージョンへと移動します。

この記事では、移行に関する Microsoft によるアプローチの概要、移行中および移行後のユーザーと管理者の両方のエクスペリエンス、および使用するワークロードに基づいてユーザーに必要になる可能性があるアクションについて明確に説明します。

以下のサービスは、Microsoft 主導のアプローチの一部として移行されます。

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business
- Skype for Businessオンライン\*\*
- Office 365 グループ
- Dynamics 365 / Power Platform\*\*\*

\*\*Microsoft Cloud Deutschland からドイツのデータセンター地域への移行中に、既存の Skype for Business Online のお客様は、Microsoft Teams に移行します。 詳細情報については、「[Microsoft Teams へのアップグレードを開始する](/microsoftteams/upgrade-start-here)」を参照してください。

\*\*\*これらのサービスの移行の前提条件と影響については [、「Dynamics 365 Customer engagement」の記事を参照](/dynamics365/get-started/migrate-data-german-region) してください。

Office 365 ビデオは 2021 年 3 月 1 日に廃止されます。 Office 365 テナントを新しいドイツのデータセンター リージョンに移行することを選択した場合、SharePoint Online の移行が完了した後、Office 365 ビデオはサポートされません。 詳細については [、「Microsoft Cloud Deutschland タイムライン」を参照してください](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="how-is-the-migration-organized"></a>移行の整理方法

この図は、新しいドイツのデータセンターへの移行の 10 フェーズを示しています。

:::image type="content" alt-text="新しいドイツのデータセンターへの移行の 10 フェーズ" source="../media/ms-cloud-germany-migration-opt-in/migration-organization.png" lightbox="../media/ms-cloud-germany-migration-opt-in/migration-organization.png":::

移行をオプトイン [すると、これらのフェーズが開始されます](./ms-cloud-germany-migration-opt-in.md)。 移行フェーズの大部分は、最小限の顧客とのやり取りが必要なバック エンド サービス操作として実行され、その後に 1 つのフェーズが実行されます。 追加の顧客主導のタスクと全体的な移行状態の開始は、移行プロセス中に、Microsoft 365 管理センターメッセージ センターを通じて伝達されます。 タスクの例としては、顧客が管理する DNS 更新プログラム、ハイブリッド顧客向けハイブリッド セットアップの再構成、Exchange Azure 移行などがあります。

オプトインが発生しても、移行はすぐには開始されません。 組織は、後で移行する予定のテナントの一覧に追加されます。 正常な移行と完了時の使用を確実に行う上で重要な作業前フェーズを開始できます。

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)

テナント移行が開始される 1 週間前に、すべての前提条件が完了する必要があるという最終警告として、メッセージ センター サービスに通知が届きます。

移行は、Azure AD テナントを主権ドイツの Azure AD サービスから EU 地域の Azure AD の Office 365 サービス インスタンスに移動します。

次のフェーズは、テナントのサブスクリプション&#39;ユーザー ライセンスをドイツ固有の製品からグローバル製品に移行します。

お客様の Azure 移行を含むすべての手順が完了すると、テナントは Office 365 サービスで終了し、移行は完了とマークされます。 この時点で、メッセージ センターへの最終更新プログラムが提供されます。 テナントは現在、組織の完全Office 365です。

メッセージ センターの投稿で移行の進行状況が通知されます。 投稿は特定のマイルストーンで実行され、ステップの進捗状況に関するガイダンスと、プロセス要件に基づいて顧客が行動する重要な情報を提供します。 メッセージ センター通知は、次のマイルストーンで提供されます。

- 移行の開始 (Azure の移行が開始AD 5 営業日前)
- Azure AD移行が完了しました
- サブスクリプションとライセンスの移行の完了
- SharePoint移行が完了しました
- Exchange移行が完了しました
- Skype for Business完了
- Dynamics complete
- Power BI完了
- サービスの最終的なカットオーバーが完了しました

Azure ADがワールドワイド サービスに切り替わると、すべてのクライアントとアプリケーションが適切なエンドポイントを使用するように完全に移行される必要があります。 最終的なカットオーバーの後に 30 日間のウィンドウが表示されます。Microsoft Cloud Deutschland サービスから Azure AD トークンを引き続き取得できます。 30 日間の期間が経過すると、クライアントとアプリケーションは Microsoft Cloud Deutschland の Azure ADエンドポイントにアクセスできなくなりました。 アプリケーションまたはユーザー アクセスは、この時点から失敗します。 このタイム ウィンドウが閉じる前に、すべてのユーザーとアプリケーションが正しいエンドポイントに移行されていることを確認する必要があります。 

## <a name="moving-to-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター地域への移行

既存の Microsoft Cloud Deutschland のお客様は、Office 365 Dynamics 365 Customer Engagement、および Power Platform サービスの移行を開始できます。 最初のステップは、新しいドイツのデータセンター リージョンへの [Microsoft 主導の移行にオプトインする](./ms-cloud-germany-migration-opt-in.md)ことです。 サブスクリプションを更新すると、Microsoft が支援する移行を自動的にオプトインします。 Microsoft は、お客様のテナント管理者に電子メールと、この問題が発生した場合、Microsoft 365 管理センターメッセージ センターに通知します。 ただし、今すぐプロセスを開始する場合は、今日から[](./ms-cloud-germany-migration-opt-in.md)直接オプトインMicrosoft 365 管理センターできます。 移行は 2021 年初めに開始され、2021 年 10 月 29 日までに完了する予定です。 

移行の結果、主要な顧客データとサブスクリプションは新しいドイツのデータセンター地域に移動されます。

> [!NOTE]
> この記事には、サービスの移行に関するガイダンスOffice 365含まれています。 Microsoft Cloud Deutschland で追加の Azure ワークロードを実行している場合は [、「Azure Germany の移行ガイダンス」を参照してください](/azure/germany/germany-migration-main)。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター リージョンでの Office 365 サービスへの移行を準備する方法

最初の手順は、サブスクリプションとデータを Microsoft Cloud Deutschland から新しいドイツのデータセンター地域の Office 365 サービスに移行する権限を持つ Microsoft に通知することです。 手順については、 [オプトイン プロセス](./ms-cloud-germany-migration-opt-in.md) を参照し、次の点に注意してください。

- 移行しているすべてのお客様は、新しいドイツのデータセンター地域を含む Office 365 サービス Office 365 URL と[IP](urls-and-ip-address-ranges.md)アドレスへの接続を確認する必要があります。 不作為により、サービスとクライアントの障害が発生する可能性があります。
- 作業前のアクティビティ [の一覧を確認](ms-cloud-germany-transition-add-pre-work.md) して、組織に変更に関する情報と準備を確認します。
- ドイツ地域への移行後Office 365利用できる機能とサービスを理解するには、プラットフォーム サービスの説明を確認する必要があります。
- 試用版サブスクリプションは移行されるのではなく、すべての有料サブスクリプションの移行をブロックします。 移行を開始する前に、試用版をキャンセルするか、有料サブスクリプションに変換する必要があります。

## <a name="where-do-i-go-from-here"></a>ここからどこに行くのですか?

次の [よく寄せられる質問] セクションを確認します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="is-migration-required"></a>移行は必要ですか ?

Microsoft は、Office 365ドイツの新しいデータセンター地域で、Microsoft Cloud Deutschland から Office 365 サービスへのテナント移行を無料で提供しました。 すべての対象となる Microsoft Cloud Germany (Microsoft Cloud Deutschland) のお客様が移行されました。 自動化されたプロセスを通じて、それ以上の顧客は移行されません。 残りの Microsoft Cloud Germany サブスクリプションとテナントは、サービスの終了アクティビティの一環として、2021 年 9 月に非アクティブ化およびプロビジョニング解除されます。

サービスが終了するまで、Microsoft Cloud Deutschland 地域に必要なセキュリティ更新プログラムを引き続き提供します。 

Office 365ドイツのデータセンター地域のサービスを次に示します。

- [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)、および [Power BI](https://powerbi.microsoft.com/pricing/) について、市場競争力のある価格を提供します。
- Microsoft&#39;のグローバル ネットワークに接続され、何百ものネットワーク エッジ サイト、ピアリングの場所、および出力ポイントを提供し、世界中のどこからでも堅牢なユーザー エクスペリエンスを提供します。
- ドイツ国内での顧客データの常駐要件を満たすのに役立ちます。
- 最新バージョンのサービスと、Microsoft Teams や Multi-Geo などの新機能を使用して、フル機能のグローバル クラウド サービスを提供Office 365。 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、[Office 365](o365-data-locations.md)、[Dynamics 365](/dynamics365/get-started/availability) について、地域ごとに製品を比較します。
- 完全な機能、エンタープライズグレードのセキュリティ、および包括的な機能を提供し、顧客がコンプライアンスおよび規制要件を満たすのを支援します。
- 既存のオンライン サービス契約を通じてアクセスできます。

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>さまざまな Office 365 クラウド サービス間のサービス可用性はどのくらいですか?
<h2 id="serv-avail"></h2>

Microsoft Cloud Deutschland クラウド サービスでは、次の 15 のサービスを利用できます。 Microsoft Cloud Deutschland に新しいサービスを追加しているのではありません。

1. Exchange Online
2. カスタマー ロックボックス (Exchange Online)
3. グループ (モダン グループ)
4. Delve プロファイル
5. Exchange Online Protection
6. Defender for Office 365
7. Advanced eDiscovery
8. 高度なデータ ガバナンス
9. SharePoint Online
10. カスタマー ロックボックス (SharePoint Online)
11. OneDrive for Business
12. Skype for Business Online
13. Word Online、Excel Online、PowerPoint、OneNote、Visio Online
14. Office 365 Pro Plus
15. Outlook モバイル

現在、ドイツの新しいデータセンター地域では、Office 365サービスの一部として 39 のサービスを利用できます。 新しい機能とサービスは、グローバルな Office 365 サービスと一貫性を持つ形で継続的に利用可能になります。

1. Exchange Online
2. 顧客ロックボックス (Exchange Online
3. Microsoft 365 グループ
4. Delve プロファイル
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender for Office 365
9. Advanced eDiscovery
10. Advanced Security Management
11. Office 365 の情報保護 
12. 高度なデータ ガバナンス
13. SharePoint Online
14. カスタマー ロックボックス for SharePoint オンライン
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (移行中にMicrosoft Teamsに移行されます)
18. クラウド PBX
19. PSTN 会議
20. PSTN 通話
21. Microsoft Teams
22. 管理者レポート/利用状況レポート
23. Web 用 Office
24. Planner
25. Sway
26. Microsoft 365 Apps
27. Outlook モバイル
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1、Intune、および Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Power AutomateのOffice 365
32. Power Virtual AgentsのOffice 365
33. Power AppsのOffice 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. リスト

### <a name="when-will-migration-happen"></a>移行はいつ行われますか ?

**Azure**

Azure のお客様のみである場合は、Azure[](/azure/germany/germany-migration-main)リソースの別の地域への移行を今日から開始できます。 

azure に Office 365、Dynamics 365、または Power BI がある場合は、まず Office 365 サービスの移行プロセスに従って、Azure AD の移行を成功に向け、その前に Azure AD の自動移行を開始する必要があります。 Azure の移行を完了してからテナント移行を完了し、Azure のワークロードを Azure AD組織Office 365があります。 詳細については [、「移行フェーズのアクションと Microsoft Cloud Deutschland](ms-cloud-germany-transition-phases.md) からの移行に対する影響」を参照してください。

**Office 365、Dynamics 365、および Power BI**

すべての対象となる Microsoft Cloud Germany (Microsoft Cloud Deutschland) のお客様が移行されました。 自動化されたプロセスを通じて、それ以上の顧客は移行されません。 残りの Microsoft Cloud Germany サブスクリプションとテナントは、サービスの終了アクティビティの一環として、2021 年 9 月に非アクティブ化およびプロビジョニング解除されます。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>使用しているサービスの価格Office 365変更されますか?

はい。 Microsoft&#39;のグローバル クラウド地域 (新しいデータセンター地域を含む) の価格は、一般に低くなります。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>サブスクリプションの移行中に、組織とユーザーに適用される SKU とライセンス

Microsoft Cloud Deutschland から Office 365 サービスへの移行中に、ドイツのサービス固有の SKU は、同じ SKU または類似の SKU のグローバル バージョンに置き換えられる。 ほとんどの場合、Office 365 サービスの SKU は同じですが、ドイツの SKU が Office 365 サービスで使用できなくなった代替品は少なからず存在します。 移行が完了した後に組織に割り当てられた SKU を更新する場合は、販売者に問い合わせ、割り当てられたサービスを追加または変更してください。

| Microsoft Cloud Deutschland - 製品 SKU (DE) | Microsoft Cloud Global - 製品 SKU (WW) |
| --- | --- |
| Customer Lockbox \_ DE (LOCKBOX \_ DE) | Customer Lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition - 追加のデータベース Storage \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition - 追加データベース Storage (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition - 追加の非実稼働インスタンス \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition - 追加の非実稼働インスタンス (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE SALES \_ \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1) |
| \_ECAL Services (EOA, EOP, DLP)DE (ECAL \_ SERVICES \_ DE) | ECAL Services (EOA, EOP, DLP) (ECAL \_ SERVICES) |
| \_Enterprise Mobility + Security E3DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| \_Exchange Online (プラン 1)DE (EXCHANGESTANDARD \_ DE) | Exchange Online (プラン 1) (EXCHANGESTANDARD) |
| \_Exchange Online (プラン 2)DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (プラン 2) (EXCHANGEENTERPRISE) |
| \_Exchange Online Archiving for Exchange OnlineDE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Archiving for Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| \_Exchange Online Archiving for Exchange ServerDE (EXCHANGEARCHIVE \_ DE) | Exchange Online Archiving for Exchange Server (EXCHANGEARCHIVE) |
| \_Exchange Online EssentialsDE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| \_Exchange Online KioskDE (EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| \_Exchange Online ProtectionDE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Onlineインスタンス \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Onlineインスタンス (CRMINSTANCE) |
| Office 365 A1 \_ DE (STANDARDWOFFPACK FACULTY \_ \_ DE) | Office 365 A1教員向け情報 (STANDARDWOFFPACK \_ FACULTY) |
| Office 365 A1 DE \_ (STANDARDWOFFPACK STUDENT \_ \_ DE) | Office 365 A1向け (STANDARDWOFFPACK \_ STUDENT) |
| \_Office 365 Advanced ComplianceDE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 Compliance (情報 \_ 保護 \_ コンプライアンス) |
|Microsoft Defender for Office 365 (プラン 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender for Office 365 (プラン 1) (ATP \_ ENTERPRISE) |
| \_Office 365 Business EssentialsDE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| \_Office 365 Business PremiumDE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| \_Office 365 BusinessDE (O365 \_ BUSINESS \_ DE) | Microsoft 365 Apps for business (O365 \_ BUSINESS) |
| \_Office 365 E1DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3なし \_ (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3なし (ENTERPRISEPACKWITHOUTPROPLUS) |
| \_Office 365 E3DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 EnterpriseE1 \_ DE (STANDARDPACK \_ DE) | Office 365 EnterpriseE1 (STANDARDPACK) |
| Office 365 EnterpriseE3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 EnterpriseE3 (ENTERPRISEPACK) |
| Office 365Extra File Storage \_ DE (SHAREPOINTSTORAGE \_ DE) | Office 365追加のファイル Storage (SHAREPOINTSTORAGE) |
| \_Office 365 F1DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus DE \_ (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus教員向け情報 (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus DE \_ (OFFICESUBSCRIPTION Student \_ \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION \_ Student) |
| \_Office 365 ProPlusDE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| \_OneDrive for Business (Plan 1)DE (WACONEDRIVESTANDARD \_ DE) | OneDrive for Business (Plan 1) (WACONEDRIVESTANDARD) |
| \_OneDrive for Business (Plan 2)DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive for Business (Plan 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro DE \_ (POWER \_ BI \_ PRO \_ FACULTY \_ DE) | Power BI Pro教員向け情報 (POWER \_ BI \_ PRO \_ FACULTY) |
| \_Power BI ProDE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| \_Project Online EssentialsDE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| \_Project Online PremiumDE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| \_Project Online ProfessionalDE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| \_Project Plan 3DE (PROJECTPROFESSIONAL \_ DE) | Project Plan 3 (PROJECTPROFESSIONAL) |
| Office 365E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| \_SharePoint Online (プラン 1)DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (プラン 1) (SHAREPOINTSTANDARD) |
| \_SharePoint Online (プラン 2)DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (プラン 2) (SHAREPOINTENTERPRISE) |
| Skype for Businessオンライン (プラン 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype for Businessオンライン (プラン 1) \_ DE (MCOIMP \_ DE) | Skype for Businessオンライン (プラン 1) (MCOIMP) |
| Skype for Businessオンライン (プラン 2) \_ DE (MCOSTANDARD \_ DE) | Skype for Businessオンライン (プラン 2) (MCOSTANDARD) |
| Skype for BusinessPlus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype for BusinessPlus CAL (MCOPLUSCAL) |
| Visioオンライン プラン 1 for faculty \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio教職員向けオンライン プラン 1 (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visioオンライン プラン 1 \_ DE (VISIOONLINE \_ \_ PLAN1 DE) | Visioオンライン プラン 1 (VISIOONLINE \_ PLAN1) |
| Visioオンライン プラン 2 for faculty \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio教職員向けオンライン プラン 2 (VISIOCLIENT \_ FACULTY) |
| Visioオンライン プラン 2 \_ DE (VISIOCLIENT \_ DE) | Visioオンライン プラン 2 (VISIOCLIENT) |
| \_Visio Plan 1DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Plan 1 (VISIOONLINE \_ PLAN1) |
| \_Visio Plan 2DE (VISIOCLIENT \_ DE) | Visio Plan 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>新しいリージョンに移行したりサポートの質問に答えたりするために、Microsoft からヘルプを得るにはどうすればよいですか ?

ご質問がある場合は、お問い合わせまたはパートナーにお問い合わせください。

- Azure の場合、Azure ポータルで[新しいサポート リクエスト](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)を送信できます。
- このOffice 365、ヘルプが必要ですか? リンクを使用して質問 &quot; &quot; を送信[Microsoft 365 管理センター。](https://portal.office.de/)
- Dynamics 365 Customer Engagement および Power BI のお客様で、Office 365 をお持ちのお客様は、Microsoft 365 管理センター の [ヘルプが必要ですか? ] リンク &quot; &quot; を使用して質問[を送信できます](https://portal.office.de/)。 Dynamics 365 Customer Engagement のサポート オプションは[こちら](/dynamics365/get-started/support/)にあります。 Power BI のサポート オプションは[こちら](https://powerbi.microsoft.com/support/)にあります。

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>お客様は、Microsoft Cloud Deutschland テナントに加えて、グローバル Microsoft クラウドに M365 テナントを既に持っています。 移行の一環として、これら 2 つのテナントを 1 にマージできますか?

いいえ、テナントのマージ機能はありません。 テナントは、各テナントに独自の名前空間と一意の ID を持つので、独立した一意の状態を維持します。 Microsoft は、必要に応じて Microsoft Cloud Deutschland テナントをグローバル クラウドに移行するか、それ以外の場合はキャンセルして破棄できます。


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>移行の一環として、ほとんどのエンド ユーザーが実行する必要があるアクションは何ですか?
移行は、エンド ユーザー/顧客への影響を最小限に抑える目的で設計されています。
- すべてのアプリケーションOffice最新バージョンが実行されている必要があります。 
- 移行をSkype for Businessお客様Teams移行の一環として移行し、デバイスにTeamsインストール[する](/deployoffice/teams-install)必要があります。
- エンド ユーザーは、移行が完了したら、Officeアプリケーションからログアウトし、ログインし戻す必要がある場合があります。 
- OneDrive同期クライアントを実行しているお客様は、ワークステーションからログアウトし、再度ログインして、OneDrive Sync クライアントがグローバル Azure Active Directory サービスにログインできる必要があります。
- 移行が完了したら、新しいグローバル URL (特に Web Access Outlook使用) に注意 outlook.office365.com。 SharePointオンライン クライアントは、既存の URL を使用して MCD 名前空間に引き続き正常に接続します (例: contoso.sharepoint.de)。


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>移行の影響を受けるお客様Azure Active Directoryですか? 

すべてのお客様Office 365、Microsoft ホストAzure Active Directory運用に必要な重要なサービス コンポーネントの認証と保存を行う必要があります。 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>移行の影響Azure Active Directory?

初期フェーズでのAzure Active Directory移行は、カスタマー エクスペリエンスに影響を与える影響はありません。 移行の最終段階が終わると、顧客テナントのすべてのサービスがグローバル サービスに完全に適用されます。 この最終段階の後、Microsoft Cloud Deutschland の Azure Active Directory サービスは、承認要求を受け入れなくなったり、サービスにアクセス トークンをOfficeがあります。


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>サービス URL と IP アドレスへのネットワーク接続をOffice 365[とはどういう意味ですか](./urls-and-ip-address-ranges.md)?

この記事では、優れたカスタマー エクスペリエンスを確保するためにグローバル サービスの適切な機能に必要な URL と IP アドレスについて説明します。 比較的まれなケースでは、一部のお客様は、トラフィック フローを最小限に抑えるためにネットワーク境界セキュリティを構成しようと試み、Microsoft Cloud Deutschland サービス IP 範囲の一部としてのみサービスへのアクセスを制限しています。


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>メールが引き続き流れExchange Online DNS の変更を管理する方法

Microsoft が管理する IP 範囲と DNS ゾーンは、グローバル サービスへの移行中および移行の一環として移行されます。 

カスタム ドメイン MX レコードなどの顧客管理 DNS ゾーンは、お客様の責任ですが、この移行を簡略化するために、顧客管理 MX レコードは office.de ゾーン内の Office 365 サービス エンドポイントをポイントし、Microsoft は自動的にこのサービス エンドポイントの移行を管理します。


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>サーバーの DNS 変更を管理するSkype for Business? 
 
For Business Skypeのすべてのユーザーは、ユーザーにMicrosoft Teams。 DNS ゾーンへの移行ではSkype DNS ゾーンの移行はTeams。 移行後、すべての機能を使用Teamsすぐにサインインできます。
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>移行Outlook iOS と Android 用のアプリは動作しますか? 

はい。 Microsoft の推奨事項は、すべてのお客様が、iOS および Android クライアントのOfficeを含む最新Outlookバージョンを実行する方法です。 Office 365 グローバル サービスへの移行が完了すると、すべての Office クライアントがログアウトしてログインし、グローバル サービスから新しい Azure Active Directory アクセス トークンを取得する必要があります。 



## <a name="next-step"></a>次の手順

[移行のオプトイン](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>詳細

はじめに:

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
