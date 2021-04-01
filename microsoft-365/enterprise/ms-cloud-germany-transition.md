---
title: 新しいドイツのデータセンター地域Office 365 サービスへの Microsoft Cloud Deutschland からの移行
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
description: '概要: 新しいドイツのデータセンター リージョンで、Microsoft Cloud Germany (Microsoft Cloud Deutschland) から Office 365 サービスへの移行について理解します。'
ms.openlocfilehash: 7e170967e1670433a7d28753430f0cb15818039b
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476639"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター地域Office 365 サービスへの Microsoft Cloud Deutschland からの移行

> [!NOTE]
> この記事は、対象となる Microsoft Cloud Deutschland のお客様にのみ適用されます。

2018 年 8 月、Microsoft は、ドイツの新しいクラウド地域から完全な Microsoft クラウド (Azure、Office 365、Dynamics 365、Power Platform) を提供し、お客様のデジタル変換をより良く実現する意向を発表しました。 2019 年 8 月に、ドイツで新しいクラウド リージョンを開設する準備を進めていることを発表しました。 その後、Azure、Office 365、Dynamics 365、Power Platform の可用性を発表しました。

新しい地域は、柔軟性の高い、最新のインテリジェント クラウド サービス、Microsoft 365 サービス クラウド ネットワークへの完全な接続、およびドイツ内の顧客データ常駐により、ドイツのお客様の進化するニーズに対応するように設計されています。

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

- Skype for Business Online\*\*
- Office 365 グループ
- Dynamics 365 / Power Platform\*\*\*

\*\*Microsoft Cloud Deutschland からドイツのデータセンター地域への移行中に、既存の Skype for Business Online のお客様は Microsoft Teams に移行します。 詳細情報については、「[Microsoft Teams へのアップグレードを開始する](/microsoftteams/upgrade-start-here)」を参照してください。

\*\*\*これらのサービスの移行の前提条件と影響については [、「Dynamics 365 Customer engagement」の記事を参照](/dynamics365/get-started/migrate-data-german-region) してください。

Office 365 ビデオは 2021 年 3 月 1 日に廃止されます。 Office 365 テナントを新しいドイツのデータセンター リージョンに移行することを選択した場合、SharePoint Online の移行が完了した後、Office 365 ビデオはサポートされません。 詳細については [、「Microsoft Cloud Deutschland タイムライン」を参照してください](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="how-is-the-migration-organized"></a>移行の整理方法

この図は、新しいドイツのデータセンターへの移行の 10 フェーズを示しています。

![新しいドイツのデータセンターへの移行の 10 フェーズ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

移行をオプトイン [すると、これらのフェーズが開始されます](./ms-cloud-germany-migration-opt-in.md)。 移行フェーズの大部分は、最小限の顧客とのやり取りが必要なバック エンド サービス操作として実行され、その後に 1 つのフェーズが実行されます。 追加の顧客主導のタスクと全体的な移行状態の開始は、移行プロセス中に Microsoft 365 管理センターのメッセージ センターを通じて伝達されます。 タスクの例としては、お客様が管理する DNS 更新プログラム、Exchange ハイブリッド顧客のハイブリッド セットアップの再構成、Azure 移行が含まれます。

オプトインが発生しても、移行はすぐには開始されません。 組織は、後で移行する予定のテナントの一覧に追加されます。 正常な移行と完了時の使用を確実に行う上で重要な作業前フェーズを開始できます。

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [その他の作業前](ms-cloud-germany-transition-add-pre-work.md)

テナント移行が開始される 1 週間前に、すべての前提条件が完了する必要があるという最終警告として、メッセージ センター サービスに通知が届きます。

移行は、Azure AD テナントを主権ドイツの Azure AD サービスから EU 地域の Azure AD の Office 365 サービス インスタンスに移動します。

次のフェーズは、テナントのサブスクリプション&#39;ユーザー ライセンスをドイツ固有の製品からグローバル製品に移行します。

顧客の Azure 移行を含むすべての手順が完了すると、テナントは Office 365 サービス サービスで終了し、移行は完了とマークされます。 この時点で、メッセージ センターへの最終更新プログラムが提供されます。 テナントは現在、365 組織Officeグローバルです。

メッセージ センターの投稿で移行の進行状況が通知されます。 投稿は特定のマイルストーンで実行され、ステップの進捗状況に関するガイダンスと、プロセス要件に基づいて顧客が行動する重要な情報を提供します。 メッセージ センター通知は、次のマイルストーンで提供されます。

- 移行の開始 (Azure の移行が開始AD 5 営業日前)
- Azure AD移行が完了しました
- サブスクリプションとライセンスの移行の完了
- SharePoint の移行が完了しました
- Exchange の移行が完了しました
- Skype for Business の完了
- Dynamics complete
- Power BI の完了
- サービスの最終的なカットオーバーが完了しました

Azure ADがワールドワイド サービスに切り替わると、すべてのクライアントとアプリケーションが適切なエンドポイントを使用するように完全に移行される必要があります。 最終的なカットオーバーの後に 30 日間のウィンドウが表示されます。Microsoft Cloud Deutschland サービスから Azure AD トークンを引き続き取得できます。 30 日間の期間が経過すると、クライアントとアプリケーションは Microsoft Cloud Deutschland の Azure ADエンドポイントにアクセスできなくなりました。 アプリケーションまたはユーザー アクセスは、この時点から失敗します。 このタイム ウィンドウが閉じる前に、すべてのユーザーとアプリケーションが正しいエンドポイントに移行されていることを確認する必要があります。 

## <a name="moving-to-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター地域への移行

既存の Microsoft Cloud Deutschland のお客様は、365、Dynamics 365 Customer Engagement、および Power Platform サービスOffice移行を開始できます。 最初のステップは、新しいドイツのデータセンター リージョンへの [Microsoft 主導の移行にオプトインする](./ms-cloud-germany-migration-opt-in.md)ことです。 サブスクリプションを更新すると、Microsoft が支援する移行を自動的にオプトインします。 この問題が発生した場合、Microsoft は顧客テナント管理者に電子メールと Microsoft 365 管理センターのメッセージ センターで通知します。 ただし、今すぐプロセスを開始する場合は、今日[](./ms-cloud-germany-migration-opt-in.md)Microsoft 365 管理センターで直接オプトインできます。 移行は 2021 年初めに開始され、2021 年 10 月 29 日までに完了する予定です。 

移行の結果、主要な顧客データとサブスクリプションは新しいドイツのデータセンター地域に移動されます。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター リージョンでの Office 365 サービスへの移行を準備する方法

最初の手順は、Microsoft Cloud Deutschland から新しいドイツのデータセンター地域の Office 365 サービスにサブスクリプションとデータを移行するアクセス許可が付与された状態で Microsoft に通知することです。 手順については、 [オプトイン プロセス](./ms-cloud-germany-migration-opt-in.md) を参照し、次の点に注意してください。

- 移行しているすべてのお客様は、Office 365 Services [Office 365 URL](urls-and-ip-address-ranges.md)と IP アドレス (新しいドイツのデータセンター地域を含む) への接続を確認する必要があります。 不作為により、サービスとクライアントの障害が発生する可能性があります。
- 作業前のアクティビティ [の一覧を確認](ms-cloud-germany-transition-add-pre-work.md) して、組織に変更に関する情報と準備を確認します。
- ドイツ地域への移行後Office 365 プラットフォーム サービスの説明を確認して、組織で利用できる機能とサービスを把握する必要があります。
- 試用版サブスクリプションは移行されるのではなく、すべての有料サブスクリプションの移行をブロックします。 移行を開始する前に、試用版をキャンセルするか、有料サブスクリプションに変換する必要があります。

## <a name="where-do-i-go-from-here"></a>ここからどこに行くのですか?

次の [よく寄せられる質問] セクションを確認します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="is-migration-required"></a>移行は必要ですか ?

Microsoft はOfficeドイツの新しいデータセンター地域で、Microsoft Cloud Deutschland から Office 365 サービスへの 365 テナントの移行を無料で提供しています。 新しいドイツのデータセンター地域への移行をオプトインすることを強く推奨しますが、Microsoft Cloud Deutschland 地域に必要なセキュリティ更新プログラムを引き続き提供します。

Officeドイツのデータセンター地域で 365 のサービスを提供します。

- [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)、および [Power BI](https://powerbi.microsoft.com/pricing/) について、市場競争力のある価格を提供します。
- Microsoft&#39;のグローバル ネットワークに接続され、何百ものネットワーク エッジ サイト、ピアリングの場所、および出力ポイントを提供し、世界中のどこからでも堅牢なユーザー エクスペリエンスを提供します。
- ドイツ国内での顧客データの常駐要件を満たすのに役立ちます。
- Microsoft Teams や Multi-Geo などの最新バージョンのサービスと新しい機能を使用して、フル機能のグローバル クラウド サービスを提供Office 365. [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、[Office 365](o365-data-locations.md)、[Dynamics 365](/dynamics365/get-started/availability) について、地域ごとに製品を比較します。
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

現在、ドイツの新しいデータセンター地域には、Office 365 サービスの一部として 39 のサービスが提供されています。 新しい機能とサービスは、グローバルな Office 365 サービスと一貫性を持つ形で継続的に利用可能になります。

1. Exchange Online
2. Exchange Online のカスタマー ロックボックス
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
14. SharePoint Online のカスタマー ロックボックス
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (移行中に Microsoft Teams に移行されます)
18. クラウド PBX
19. PSTN 会議
20. PSTN 通話
21. Microsoft Teams
22. 管理者レポート/利用状況レポート
23. Webアプリ上の Office
24. Planner
25. Sway
26. Microsoft 365 アプリ
27. Outlook モバイル
28. Enterprise Mobility + Security (EMS) E3 (Azure AD プレミアム P1、Intune、および Rights Management Service)
29. Yammer エンタープライズ
30. Microsoft Forms
31. Power Automate for Office 365
32. Power Virtual Agents for Office 365
33. PowerApps for Office 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. リスト

### <a name="when-will-migration-happen"></a>移行はいつ行われますか ?

**Azure**

Azure のお客様のみである場合は、Azure[](/azure/germany/germany-migration-main)リソースの別の地域への移行を今日から開始できます。 

azure に Office 365、Dynamics 365、または Power BI がある場合は、移行プロセスに従って、AzureAD の移行を成功に向け、その前に AzureAD の自動移行を開始する必要があります。 AzureAD と 365 組織で Azure ワークロードを維持するには、サービスの終了前に Azure 移行をOffice必要があります。

**Office 365**

今すぐ、Microsoft 主導の移行に[オプトイン](./ms-cloud-germany-migration-opt-in.md)してください。 移行を開始する準備ができたら、Microsoft 365 管理センターのメッセージ センターから通知します。

**Dynamics 365 および Power BI**

Dynamics [365 Customer Engagement](/dynamics365/get-started/migrate-data-german-region) と Power BI の Microsoft による移行を今すぐ [オプトイン](/power-bi/admin/service-admin-migrate-data-germany) します。 移行を開始する準備ができたら、Microsoft 365 管理センターのメッセージ センターからお知らせします。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>使用している 365 サービスOffice価格は変わりますか?

はい。 Microsoft&#39;のグローバル クラウド地域 (新しいデータセンター地域を含む) の価格は、一般に低くなります。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>サブスクリプションの移行中に、組織とユーザーに適用される SKU とライセンス

Microsoft Cloud Deutschland から Office 365 サービスへの移行中に、ドイツのサービス固有の SKU は、同じ SKU または類似の SKU のグローバル バージョンに置き換えられる。 ほとんどの場合、Office 365 サービスの SKU は同じですが、ドイツの SKU が Office 365 サービスで使用できなくなった代替品は少なからず存在します。 移行が完了した後に組織に割り当てられた SKU を更新する場合は、販売者に問い合わせ、割り当てられたサービスを追加または変更してください。

| Microsoft Cloud Deutschland - 製品 SKU (DE) | Microsoft Cloud Global - 製品 SKU (WW) |
| --- | --- |
| Customer Lockbox \_ DE (LOCKBOX \_ DE) | Customer Lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition - 追加のデータベース ストレージ \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition - その他のデータベース ストレージ (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition - 追加の非実稼働インスタンス \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition - 追加の非実稼働インスタンス (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE \_ DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ SALES \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS \_ DE) | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1) |
| ECAL サービス (EOA、EOP、DLP) \_ DE (ECAL \_ SERVICES \_ DE) | ECAL サービス (EOA、EOP、DLP) (ECAL \_ SERVICES) |
| エンタープライズ モビリティ + セキュリティ E3 \_ DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (プラン 1) DE \_ (EXCHANGESTANDARD \_ DE) | Exchange Online (プラン 1) (EXCHANGESTANDARD) |
| Exchange Online (プラン 2) \_ DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (プラン 2) (EXCHANGEENTERPRISE) |
| Exchange Online Archiving for Exchange Online \_ DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Archiving for Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| Exchange Online Archiving for Exchange Server \_ DE (EXCHANGEARCHIVE \_ DE) | Exchange Online ArchivingのExchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| Exchange Online Kiosk \_ DE (EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online インスタンス \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online インスタンス (CRMINSTANCE) |
| Office 365 A1 for faculty \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 for faculty (STANDARDWOFFPACK \_ FACULTY) |
| Office 365 A1 for students \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 for students (STANDARDWOFFPACK \_ STUDENT) |
| Office 365 Advanced Compliance \_ DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 コンプライアンス (情報 \_ 保護 \_ コンプライアンス) |
|Microsoft Defender for Office 365 (プラン 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender for Office 365 (プラン 1) (ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| Office 365 Business Premium \_ DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Office 365 Business \_ DE (O365 \_ BUSINESS \_ DE) | Microsoft 365 Apps for business (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 ProPlus \_ DE なし (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 ProPlus なし (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 Extra File Storage \_ DE (SHAREPOINTSTORAGE \_ DE) | Office 365 Extra File Storage (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus for Faculty \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus for Faculty (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus for Students \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus for Student (OFFICESUBSCRIPTION \_ STUDENT) |
| Office 365 ProPlus \_ DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive for Business (プラン 1) \_ DE (WACONEDRIVESTANDARD \_ DE) | OneDrive for Business (プラン 1) (WACONEDRIVESTANDARD) |
| OneDrive for Business (プラン 2) \_ DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive for Business (プラン 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro for faculty \_ DE (POWER \_ BI \_ PRO \_ FACULTY \_ DE) | Power BI Pro for faculty (POWER \_ BI \_ PRO \_ FACULTY) |
| Power BI Pro \_ DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| Project Online Essentials \_ DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ DE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| Project Plan 3 \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Plan 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (プラン 1) DE \_ (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (プラン 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (プラン 2) \_ DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (プラン 2) (SHAREPOINTENTERPRISE) |
| Skype for Business Online (プラン 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype for Business Online (プラン 1) \_ DE (MCOIMP \_ DE) | Skype for Business Online (プラン 1) (MCOIMP) |
| Skype for Business Online (プラン 2) \_ DE (MCOSTANDARD \_ DE) | Skype for Business Online (プラン 2) (MCOSTANDARD) |
| Skype for Business Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype for Business Plus CAL (MCOPLUSCAL) |
| Visio Online Plan 1 for faculty \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Online Plan 1 for faculty (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online プラン 1 (VISIOONLINE \_ PLAN1) |
| Visio Online Plan 2 for faculty \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Online Plan 2 for faculty (VISIOCLIENT \_ FACULTY) |
| Visio Online Plan 2 \_ DE (VISIOCLIENT \_ DE) | Visio Online Plan 2 (VISIOCLIENT) |
| Visio Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Plan 1 (VISIOONLINE \_ PLAN1) |
| Visio Plan 2 \_ DE (VISIOCLIENT \_ DE) | Visio Plan 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>新しいリージョンに移行したりサポートの質問に答えたりするために、Microsoft からヘルプを得るにはどうすればよいですか ?

ご質問がある場合は、お問い合わせまたはパートナーにお問い合わせください。

- Azure の場合、Azure ポータルで[新しいサポート リクエスト](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)を送信できます。
- 365 Office、Microsoft 365 管理センターの [ヘルプが必要ですか] リンクを使用して質問 &quot; &quot; [を送信できます](https://portal.office.de/)。
- Dynamics 365 Customer Engagement および Power BI のお客様で、Office 365 も持っている場合は &quot; &quot; [、Microsoft 365](https://portal.office.de/)管理センターの [ヘルプが必要ですか] リンクを使用して質問を送信できます。 Dynamics 365 Customer Engagement のサポート オプションは[こちら](/dynamics365/get-started/support/)にあります。 Power BI のサポート オプションは[こちら](https://powerbi.microsoft.com/support/)にあります。

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>お客様は、Microsoft Cloud Deutschland テナントに加えて、グローバル Microsoft クラウドに M365 テナントを既に持っています。 移行の一環として、これら 2 つのテナントを 1 にマージできますか?

いいえ、テナントのマージ機能はありません。 テナントは、各テナントに独自の名前空間と一意の ID を持つので、独立した一意の状態を維持します。 Microsoft は、必要に応じて Microsoft Cloud Deutschland テナントをグローバル クラウドに移行するか、それ以外の場合はキャンセルして破棄できます。


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>移行の一環として、ほとんどのエンド ユーザーが実行する必要があるアクションは何ですか?
移行は、エンド ユーザー/顧客への影響を最小限に抑える目的で設計されています。
- すべてのアプリケーションOffice最新バージョンが実行されている必要があります。 
- Skype for Business を使用しているお客様は、移行の一環として Teams に移行し、デバイスに Teams をダウンロードして [インストールする](/deployoffice/teams-install) 必要がある場合があります。
- エンド ユーザーは、移行が完了したら、Officeアプリケーションからログアウトし、ログインし戻す必要がある場合があります。 
- OneDrive Sync クライアントを実行しているお客様は、ワークステーションからログアウトし、再度ログインして、OneDrive Sync クライアントがグローバル Azure Active Directory サービスにログインできる必要があります。
- 移行が完了したら、新しいグローバル URL (特に Outlook Web Access) に注意してください (例: outlook.office365.com)。 SharePoint Online クライアントは、既存の URL を使用して MCD 名前空間に引き続き正常に接続します (例: contoso.sharepoint.de)。


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Azure Active Directory 移行の影響を受けるお客様 

Office365 のすべてのお客様は、Microsoft ホスト型サービスの運用に必要な重要なサービス コンポーネントを認証および保存するために Azure Active Directory に依存しています。 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Azure Active Directory 移行の影響は何ですか?

初期フェーズでの Azure Active Directory の初期移行は、カスタマー エクスペリエンスに影響を与える影響はありません。 移行の最終段階が終わると、顧客テナントのすべてのサービスがグローバル サービスに完全に適用されます。 この最終段階の後、Microsoft Cloud Deutschland の Azure Active Directory サービスは、承認要求を受け入れなくなったり、サービスにアクセス トークンOfficeがあります。


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>[365](./urls-and-ip-address-ranges.md)サービス URL と IP アドレスへのネットワーク接続Officeとはどういう意味ですか?

この記事では、優れたカスタマー エクスペリエンスを確保するためにグローバル サービスの適切な機能に必要な URL と IP アドレスについて説明します。 比較的まれなケースでは、一部のお客様は、トラフィック フローを最小限に抑えるためにネットワーク境界セキュリティを構成しようと試み、Microsoft Cloud Deutschland サービス IP 範囲の一部としてのみサービスへのアクセスを制限しています。


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>メールが引き続き流れるので、Exchange Online の DNS 変更を管理する方法

Microsoft が管理する IP 範囲と DNS ゾーンは、グローバル サービスへの移行中および移行の一環として移行されます。 

カスタム ドメイン MX レコードなどの顧客管理 DNS ゾーンは顧客の責任ですが、この移行を簡素化するために、顧客管理 MX レコードは office.de ゾーンの Office 365 サービス エンドポイントをポイントし、Microsoft は自動的にこのサービス エンドポイントの移行を管理します。


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Skype for Business の DNS 変更を管理する方法 
 
すべての Skype For Business のお客様は、Microsoft Teams に移行します。 Teams への移行では、顧客の Skype DNS ゾーンの移行は必要ありません。 移行後、すべての機能を使用して Teams にすぐにサインインできます。
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>移行後、Outlook for iOS と Android は動作しますか? 

はい。 Microsoft の推奨事項は、すべてのお客様が、Outlook for iOS および Android クライアントを含むOfficeの最新バージョンのクライアントを実行する方法です。 Office 365 グローバル サービスへの移行が完了すると、すべての Office クライアントがログアウトしてログインし、グローバル サービスから新しい Azure Active Directory アクセス トークンを取得する必要があります。 



## <a name="next-step"></a>次の手順

[移行のオプトイン](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>詳細情報

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