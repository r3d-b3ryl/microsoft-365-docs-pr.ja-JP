---
title: Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行
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
ms.openlocfilehash: d807637e9d5469131d3124d1ef8b6b1f874e81a1
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145417"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンOffice 365 サービスへの移行

> [!NOTE]
> この記事は、対象となる Microsoft Cloud Deutschland のお客様にのみ適用されます。

2018 年 8 月、Microsoft は、お客様のデジタル変換をより良く実現するために、ドイツの新しいクラウド地域から完全な Microsoft クラウド (Azure、Office 365、Dynamics 365、および Power Platform) を提供する意向を発表しました。 2019 年 8 月に、ドイツで新しいクラウド リージョンを開設する準備を進めていることを発表しました。 その後、Azure、Office 365、Dynamics 365、および Power Platform の利用が発表されました。

新しい地域は、ドイツのお客様の進化するニーズに柔軟に対応し、最新のインテリジェント クラウド サービス、Microsoft 365 サービス のクラウド ネットワークへの完全な接続、およびドイツ内の顧客データ常駐に対応するように設計されています。

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター リージョンに移行する方法

既存の Microsoft Cloud Deutschland のお客様は、Office 365、Dynamics 365 Customer Engagement、および Power Platform のお客様の移行を開始できます。 最初のステップは、新しいドイツのデータセンター リージョンへの [Microsoft 主導の移行にオプトインする](https://aka.ms/office365germanymoveoptin)ことです。

Microsoft によるアプローチにオプトインする組織の場合、移行は 2021 年初めに開始され、2021 年 10 月 29 日までに完了する予定です。 移行の結果、主要な顧客データおよびサブスクリプションは新しいドイツ リージョンへと移動します。

この記事では、移行に関する Microsoft によるアプローチの概要、移行中および移行後のユーザーと管理者の両方のエクスペリエンス、および利用するワークロードに基づいてお客様に必要になる可能性があるアクションについて説明します。

以下のサービスは、Microsoft 主導のアプローチの一部として移行されます。

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business

- Skype for Business Online\*\*
- Office 365 グループ
- Dynamics 365 / Power Platform\*\*\*

\*\*Microsoft Cloud Deutschland からドイツのデータセンター リージョンへの移行中に、既存の Skype for Business Online のお客様は Microsoft Teams に移行されます。 詳細情報については、「[Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)」を参照してください。

\*\*\*これらのサービスの移行の前提条件と影響については [、Dynamics 365 Customer Engagement の記事を参照](https://aka.ms/d365ceoptin) してください。

Office 365 ビデオは 2021 年 3 月 1 日に廃止されます。 Office 365 テナントを新しいドイツのデータセンター リージョンに移行することを選択した場合、SharePoint Online の移行が完了した後、Office 365 ビデオはサポートされません。 詳細については [、Microsoft Cloud Deutschland のタイムラインを参照してください](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="how-is-the-migration-organized"></a>移行の編成方法

この図は、新しいドイツのデータセンターへの移行の 9 つのフェーズを示しています。

![新しいドイツデータセンターへの移行の 9 つのフェーズ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

これらのフェーズは、移行 [にオプトインすると開始されます](https://aka.ms/office365germanymoveoptin)。 移行フェーズの大部分は、最小限のカスタマー操作でバック エンド サービス操作として実行され、次に 1 つのフェーズが実行されます。 追加の顧客主導のタスクと全体的な移行状態の開始は、移行プロセス中に Microsoft 365 管理センターのメッセージ センターを通じて伝達されます。 タスクの例としては、顧客管理の DNS 更新、Exchange ハイブリッド顧客のハイブリッド セットアップの再構成、Azure 移行があります。

オプトインが発生しても、移行はすぐには開始されません。 組織は、後で移行する予定のテナントの一覧に追加されます。 完了時に移行と使用を正常に行う上で重要な作業前フェーズを今すぐ開始できます。

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)

テナント移行が開始される 1 週間前に、メッセージ センター サービスに、すべての前提条件を完了する必要があるという最終警告として通知が表示されます。

移行によって、Azure AD テナントが、主権を持つドイツの Azure AD サービスから EU 地域の Azure AD の Office 365 サービス インスタンスに移行されます。

次のフェーズでは、テナントのサブスクリプション&#39;ユーザー ライセンスをドイツ固有の製品からグローバル製品に移行します。

顧客の Azure 移行を含むすべての手順が完了すると、テナントは Office 365 サービス サービスで最終決定され、移行は完了としてマークされます。 この時点で、メッセージ センターの最終的な更新プログラムが提供されます。 テナントは、365 組織Officeグローバルです。

メッセージ センターの投稿で移行の進行状況が通知されます。 投稿は特定のマイルストーンで行われるので、手順の進捗状況に関するガイダンスと、お客様がプロセス要件に基づいて行動する重要な情報を提供します。 メッセージ センターの通知は、次のマイルストーンで提供されます。

- 移行の開始 (Azure 移行が開始AD 5 営業日前)
- Azure AD移行の完了
- サブスクリプションとライセンスの移行の完了
- SharePoint 移行の完了
- Exchange 移行の完了
- Skype for Business の完了
- Dynamics complete
- Power BI の完了
- サービスの最終的なカットオーバーが完了しました

## <a name="moving-to-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター リージョンへの移行

既存の Microsoft Cloud Deutschland のお客様は、Office 365、Dynamics 365 Customer Engagement、および Power Platform サービスの移行を開始できます。 最初のステップは、新しいドイツのデータセンター リージョンへの [Microsoft 主導の移行にオプトインする](https://aka.ms/office365germanymoveoptin)ことです。 サブスクリプションを更新すると、Microsoft による移行が自動的にオプトインされます。 このような場合、Microsoft は顧客テナント管理者に電子メールと Microsoft 365 管理センターのメッセージ センターで通知します。 ただし、今すぐプロセスを開始する場合は、 [今すぐ](https://aka.ms/office365germanymoveoptin) Microsoft 365 管理センターで直接オプトインできます。 移行は 2021 年初めに開始される予定で、2021 年 10 月 29 日までに完了する予定です。 

移行の結果、主要な顧客データとサブスクリプションは新しいドイツのデータセンター リージョンに移動されます。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター リージョンでの Office 365 サービスへの移行を準備する方法

最初の手順は、サブスクリプションとデータを Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンの Office 365 サービスに移行するアクセス許可を Microsoft に付与することを Microsoft に通知することです。 手順については、 [オプトイン プロセス](https://aka.ms/office365germanymoveoptin) を参照し、次の点に注意してください。

- 移行を行うすべてのお客様は、新しいドイツのデータセンター リージョンを含む [Office 365 サービス Office 365 URL](urls-and-ip-address-ranges.md)と IP アドレスへの接続を確認する必要があります。 不作為により、サービスとクライアントの障害が発生する可能性があります。
- 作業前のアクティビティ [の一覧を確認](ms-cloud-germany-transition-add-pre-work.md) して、組織に通知し、変更に備えます。
- Office 365 プラットフォーム サービスの説明を確認して、ドイツリージョンへの移行後に組織で利用できる機能とサービスを把握する必要があります。
- 試用版サブスクリプションは移行されません。すべての有料サブスクリプションの移行がブロックされます。 移行を開始する前に、試用版をキャンセルするか、有料サブスクリプションに変換する必要があります。

## <a name="where-do-i-go-from-here"></a>ここから行く場所

次のよく寄せられる質問のセクションを確認します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="is-migration-required"></a>移行は必要ですか ?

Microsoft はOffice 365 テナントを Microsoft Cloud Deutschland から新しいドイツのデータセンター リージョンの Office 365 サービスに無料で移行します。 新しいドイツのデータセンター リージョンへの移行をオプトインすることを強く推奨しますが、Microsoft Cloud Deutschland リージョンには必要なセキュリティ更新プログラムが引き続き提供されます。

Officeのデータセンター リージョンに 365 のサービスを展開します。

- [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)、および [Power BI](https://powerbi.microsoft.com/pricing/) について、市場競争力のある価格を提供します。
- Microsoft&#39;のグローバル ネットワークに接続され、数百のネットワーク エッジ サイト、ピアリングの場所、エグレス ポイントを提供し、世界中のどこでも堅牢なユーザー エクスペリエンスを提供します。
- ドイツ国内での顧客データの常駐要件を満たすのに役立ちます。
- Microsoft 365 の Microsoft Teams や Multi-Geo などの最新バージョンのサービスと新機能を使用して、フル機能を備えたグローバル クラウド サービスOffice提供します。 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、[Office 365](o365-data-locations.md)、[Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) について、地域ごとに製品を比較します。
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

現在、新しいドイツのデータセンター リージョンには、Office 365 サービスの一部として 39 のサービスが利用可能です。 新しい機能とサービスは、グローバルな Office 365 サービスと一貫性を持つ形で継続的に利用可能になります。

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
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1、Intune、Rights Management Service)
29. Yammer Enterprise
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

Azure の顧客のみである場合は、Azure[](https://docs.microsoft.com/azure/germany/germany-migration-main)リソースの別の地域への移行を今すぐ開始できます。 

azure に Office 365、Dynamics 365、または Power BI がある場合は、移行プロセスに従って、AzureAD の移行を成功してから、Azure への移行を開始する必要があります。 AzureAD と 365 組織で Azure ワークロードを維持するには、サービス終了前に Azure Office完了する必要があります。

**Office 365**

今すぐ、Microsoft 主導の移行に[オプトイン](https://aka.ms/office365germanymoveoptin)してください。 移行を開始する準備ができたら、Microsoft 365 管理センターのメッセージ センターでお知らせします。

**Dynamics 365 および Power BI**

現在 [、Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) と Power BI の Microsoft による移行 [にオプトイン](https://aka.ms/PBIOptIn) します。 移行を開始する準備ができたら、Microsoft 365 管理センターのメッセージ センターからお知らせします。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>使用している 365 サービスOffice価格は変わりますか?

はい。 Microsoft&#39;(新しいデータセンター リージョンを含む) の価格は、一般的に低くなります。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>サブスクリプションの移行中に、組織とユーザーに適用される SKU とライセンスは何ですか?

Microsoft Cloud Deutschland から Office 365 サービスへの移行中、ドイツのサービス固有の SKU は、同じまたは同様の SKU のグローバル バージョンに置き換えられる。 ほとんどの場合、Office 365 サービスの SKU は同じですが、ドイツの SKU が Office 365 サービスで利用できなくなった代替機能は少数です。 移行の完了後に組織に割り当てられている SKU を更新する場合は、販売者に連絡して、割り当てられたサービスを追加または変更してください。

| Microsoft Cloud Deutschland - 製品 SKU (DE) | Microsoft Cloud Global - 製品 SKU (WW) |
| --- | --- |
| カスタマー ロックボックス \_ DE (LOCKBOX \_ DE) | カスタマー ロックボックス (LOCKBOX) |
| Dynamics 365 Enterprise Edition - その他のデータベース ストレージ \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition - 追加のデータベース ストレージ (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition - その他の非実稼働インスタンス \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition - 追加の非実稼働インスタンス (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE \_ DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ SALES \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS \_ DE) | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 プラン 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 プラン 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ プラン1) |
| ECAL サービス (EOA、EOP、DLP) \_ DE (ECAL \_ SERVICES \_ DE) | ECAL サービス (EOA、EOP、DLP) (ECAL \_ サービス) |
| Enterprise Mobility + Security E3 \_ DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (プラン 1) \_ DE (EXCHANGESTANDARD \_ DE) | Exchange Online (プラン 1) (EXCHANGESTANDARD) |
| Exchange Online (プラン 2) \_ DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (プラン 2) (EXCHANGEENTERPRISE) |
| Exchange Online Archiving for Exchange Online \_ DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Archiving for Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| Exchange Online Archiving for Exchange Server \_ DE (EXCHANGEARCHIVE \_ DE) | Exchange Online ArchivingのExchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| Exchange Online Kiosk \_ DE (EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online インスタンス \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online インスタンス (CRMINSTANCE) |
| Office 365 A1 for faculty \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 for faculty (STANDARDWOFFPACK \_ FACULTY) |
| Office DE \_ (STANDARDWOFFPACK \_ STUDENT \_ DE) 用の Office 365 A1 | Office 365 A1 for students (STANDARDWOFFPACK \_ STUDENT) |
| Office 365 Advanced Compliance \_ DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 コンプライアンス (情報 \_ 保護 \_ コンプライアンス) |
|Microsoft Defender for Office 365 (プラン 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender for Office 365 (プラン 1) (ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| Office 365 Business Premium \_ DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Office 365 Business \_ DE (O365 \_ BUSINESS \_ DE) | Microsoft 365 Apps for business (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 (ProPlus \_ DE なし) (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 (ProPlus なし) (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 Extra File Storage \_ DE (SHAREPOINTSTORAGE \_ DE) | Office 365 Extra File Storage (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus for Faculty \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus for Faculty (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus for Students \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus for Students (OFFICESUBSCRIPTION \_ STUDENT) |
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
| SharePoint Online (プラン 1) \_ DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (プラン 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (プラン 2) \_ DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (プラン 2) (SHAREPOINTENTERPRISE) |
| Skype for Business Online (プラン 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype for Business Online (プラン 1) \_ DE (MCOIMP \_ DE) | Skype for Business Online (プラン 1) (MCOIMP) |
| Skype for Business Online (プラン 2) \_ DE (MCOSTANDARD \_ DE) | Skype for Business Online (プラン 2) (MCOSTANDARD) |
| Skype for Business Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype for Business Plus CAL (MCOPLUSCAL) |
| Visio Online Plan 1 for faculty \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Online Plan 1 for faculty (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online プラン 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online プラン 1 (VISIOONLINE \_ PLAN1) |
| Visio Online Plan 2 for faculty \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Online Plan 2 for faculty (VISIOCLIENT \_ FACULTY) |
| Visio Online プラン 2 \_ DE (VISIOCLIENT \_ DE) | Visio Online プラン 2 (VISIOCLIENT) |
| Visio Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Plan 1 (VISIOONLINE \_ PLAN1) |
| Visio Plan 2 \_ DE (VISIOCLIENT \_ DE) | Visio プラン 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>新しいリージョンに移行したりサポートの質問に答えたりするために、Microsoft からヘルプを得るにはどうすればよいですか ?

ご質問がある場合は、お問い合わせ先またはパートナーにお問い合わせください。

- Azure の場合、Azure ポータルで[新しいサポート リクエスト](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)を送信できます。
- For Office 365, you may submit questions using the &quot; Need Help? &quot; link of the [Microsoft 365 admin center](https://portal.office.de/).
- Dynamics 365 Customer Engagement および Power BI のお客様で、Office 365 も持っている場合は &quot; &quot; [、Microsoft 365](https://portal.office.de/)管理センターの [ヘルプが必要ですか? ] リンクを使用して質問を送信できます。 Dynamics 365 Customer Engagement のサポート オプションは[こちら](https://docs.microsoft.com/dynamics365/get-started/support/)にあります。 Power BI のサポート オプションは[こちら](https://powerbi.microsoft.com/support/)にあります。

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>顧客は、Microsoft Cloud Deutschland テナントに加えて、グローバル Microsoft クラウドに M365 テナントを既に持っています。 移行の一環として、これら 2 つのテナントを 1 つのテナントにマージできますか。

いいえ、テナントのマージ機能はありません。 各テナントには独自の名前空間と一意の ID が設定されているので、テナントは独立した一意のままです。 Microsoft は、Microsoft Cloud Deutschland テナントを必要に応じてグローバル クラウドに移行します。それ以外の場合、お客様はキャンセルして破棄できます。


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>移行の一環として、ほとんどのエンド ユーザーが実行する必要があるアクションは何ですか。
移行は、エンド ユーザーや顧客への影響を最小限に抑える目的で設計されています。
- すべてのアプリケーションOffice最新バージョンを実行している必要があります。 
- Skype for Business を使用しているお客様は、移行の一環として Teams に移行され、デバイスに Teams をダウンロードして [インストールする](https://docs.microsoft.com/deployoffice/teams-install) 必要がある場合があります。
- エンド ユーザーは、移行が完了したら、Officeアプリケーションからログアウトし、もう一度ログインする必要があります。 
- OneDrive 同期クライアントを実行しているお客様は、ワークステーションからログアウトし、再度ログインして、OneDrive 同期クライアントがグローバル Azure Active Directory サービスにログインできる必要があります。
- 移行が完了したら、新しいグローバル URL (特に Outlook Web Access) に注意してください (例: outlook.office365.com)。 SharePoint Online クライアントは、既存の URL を使用して MCD 名前空間に引き続き正常に接続します (例: contoso.sharepoint.de)。


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Azure Active Directory の移行の影響を受けるお客様は何ですか? 

Office365 のすべてのお客様は、Microsoft がホストするサービスの運用に必要な重要なサービス コンポーネントを認証および保存するために Azure Active Directory に依存しています。 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Azure Active Directory 移行の影響

初期フェーズでの Azure Active Directory の初期移行は、カスタマー エクスペリエンスに影響を与える影響はありません。 移行の最終段階が完了すると、顧客テナントのすべてのサービスがグローバル サービスに完全に組み込み済みになります。 この最終段階の後、Microsoft Cloud Deutschland の Azure Active Directory サービスは、承認要求を受け入れなくなったり、サービスへのアクセス トークンOfficeがあります。


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>365 サービス URL と IP アドレスへのネットワークOffice接続を確保するには [、どのような意味がありますか](https://aka.ms/o365urls)。

この記事では、カスタマー エクスペリエンスを向上するためにグローバル サービスの適切な機能に必要な URL と IP アドレスについて説明します。 比較的まれに、トラフィック フローを最小限に抑えるための方法でネットワーク境界セキュリティを構成しようとし、Microsoft Cloud Deutschland サービスの IP 範囲の一部としてのみサービスへのアクセスを制限しているお客様もいます。


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Exchange Online の DNS 変更を管理して、メールがフローし続ける方法

Microsoft が管理する IP 範囲と DNS ゾーンは、グローバル サービスへの移行中および移行の一環として移行されます。 

カスタム ドメイン MX レコードなどの顧客管理 DNS ゾーンは、お客様の責任ですが、この移行を簡略化するために、お客様管理の MX レコードは office.de ゾーン内の Office 365 サービス エンドポイントをポイントし、Microsoft によってこのサービス エンドポイントの移行が自動的に管理されます。


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Skype for Business の DNS 変更を管理する方法 
 
すべての Skype For Business のお客様は、Microsoft Teams に移行されます。 Teams への移行では、お客様の Skype DNS ゾーンの移行は必要ありません。 お客様は、移行後すぐにすべての機能を使用して Teams にサインインできます。
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>iOS および Android 用の Outlook は移行後に機能しますか? 

はい。 Microsoft の推奨事項は、すべてのお客様が iOS および Android 用の Outlook クライアントを含む Officeクライアントの最新バージョンを実行する方法です。 Office 365 グローバル サービスへの移行が完了すると、すべての Office クライアントはログアウトしてログインし、グローバル サービスから新しい Azure Active Directory アクセス トークンを取得する必要があります。 



## <a name="next-step"></a>次の手順

[移行のオプトイン](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>詳細情報

はじめに:

- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](ms-cloud-germany-migration-opt-in.md)
- [移行中のカスタマー エクスペリエンス](ms-cloud-germany-transition-experience.md)

移行を進む:

- [移行フェーズのアクションと影響](ms-cloud-germany-transition-phases.md)
- [追加の作業前作業](ms-cloud-germany-transition-add-pre-work.md)
- [Azure](ms-cloud-germany-transition-azure-ad.md)AD、[デバイス、エクスペリエンス](ms-cloud-germany-transition-add-devices.md)、[および](ms-cloud-germany-transition-add-experience.md)AD FS[に関する追加情報](ms-cloud-germany-transition-add-adfs.md)。

クラウド アプリ:

- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
