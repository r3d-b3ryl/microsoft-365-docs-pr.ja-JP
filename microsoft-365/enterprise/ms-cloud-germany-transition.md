---
title: 新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/30/2020
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
ms.openlocfilehash: a77dc43c4c30992d2e50aad94878f9269573db52
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327119"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行

> [!NOTE]
> この記事は、対象となる Microsoft Cloud Deut上陸お客様にのみ適用されます。

2018年8月に、Microsoft は、お客様のデジタル変換をさらに有効にするために、ドイツの新しいクラウド地域から、完全な Microsoft cloud-Azure、Office 365、Dynamics 365、および電源プラットフォームを提供することを目指して発表しました。 2019 年 8 月に、ドイツで新しいクラウド リージョンを開設する準備を進めていることを発表しました。 その後、Azure、Office 365、Dynamics 365、および電源プラットフォームの可用性について発表しました。

新しい地域は、ドイツのお客様のニーズに対応するように設計されており、ドイツのユーザーの柔軟性、最新のインテリジェントなクラウドサービス、およびドイツでのお客様のデータ常駐サービスへの完全な接続365にも対応しています。

## <a name="how-to-migrate-to-the-new-german-regions"></a>新しいドイツ地域に移行する方法

既存の Microsoft Cloud Deutお客様は、Office 365、Dynamics 365 顧客契約、および電源プラットフォームのお客様の移行を開始できます。 最初のステップは、新しいドイツのデータセンター リージョンへの [Microsoft 主導の移行にオプトインする](https://aka.ms/office365germanymoveoptin)ことです。

Microsoft による方法をオプトインしている組織の場合、移行は2021より前に開始される予定で、2021年10月29日に完了することが予想されます。 移行の結果、主要な顧客データおよびサブスクリプションは新しいドイツ リージョンへと移動します。

この記事では、移行のための Microsoft による手法の概要を示し、移行中および移行後のユーザーと管理者のエクスペリエンスを明確にします。また、使用するワークロードに基づいてお客様に必要な操作についても説明します。

以下のサービスは、Microsoft 主導のアプローチの一部として移行されます。

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business

- Skype for Business Online\*\*
- Office 365 グループ
- Dynamics 365/Power Platform\*\*\*

\*\*ドイツのデータセンターリージョンへの Microsoft クラウドの移行時に、既存の Skype for Business Online のお客様は Microsoft Teams に移行します。 詳細情報については、「[Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)」を参照してください。

\*\*\*これらのサービスの移行の前提条件と影響については、 [Dynamics 365 カスタマーエンゲージメント](https://aka.ms/d365ceoptin) の記事を参照してください。

Office 365 ビデオは 2021 年 3 月 1 日に廃止されます。 Office 365 テナントを新しいドイツのデータセンター リージョンに移行することを選択した場合、SharePoint Online の移行が完了した後、Office 365 ビデオはサポートされません。 詳細について [は、ここ](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline) をクリックしてください。

## <a name="how-is-the-migration-organized"></a>移行の整理方法

この図は、新しいドイツデータセンターへの移行における Office 365 と Dynamics 365 のさまざまなコンポーネントを表しています。

![新しいドイツデータセンターへの移行における Office 365 および Dynamics 365 のコンポーネント](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

移行は、 [移行のオプトイン](https://aka.ms/office365germanymoveoptin)時にすべて開始されるフェーズで実行されます。 移行フェーズのほとんどは、顧客との対話が最小限に抑えられたバックエンドサービスとして実行され、もう1つのフェーズの後で実行されます。 その他のお客様主導のタスクおよび全体的な移行状態は、移行プロセスの間に Microsoft 365 管理センターのメッセージセンターを通じて伝えられます。 タスクの例としては、お客様が管理する DNS の更新、Exchange ハイブリッドのお客様のためのハイブリッドセットアップの再構成、Azure の移行などがあります。

オプトインが発生しても、移行がすぐに開始されるわけではありません。 組織は、後で移行するようにスケジュールされているテナントの一覧に追加されます。 移行と使用が正常に完了したことを確実にするためには、これらのフェーズを開始することが重要です。

テナントの移行開始の1週間前に、すべての前提条件を満たす必要があることを示す最終警告として、メッセージセンターサービスで通知を受け取ります。

移行により、Azure ad テナントは、独立ドイツ Azure AD サービスから EU 地域の Azure AD の Office 365 services インスタンスに移動されます。

次のフェーズでは、ドイツ固有の製品からテナント&#39;のサブスクリプションとユーザーライセンスを移行します。

お客様の Azure 移行を含むすべての手順が完了すると、Office 365 services サービスでテナントがファイナライズされ、移行が完了としてマークされます。 この時点で、メッセージセンターの最終更新が提供されます。 これで、テナントは完全なグローバル Office 365 組織にはなりません。

移行の進行状況がメッセージセンターの投稿と一緒に通知されます。 投稿は特定のマイルストーンで行われ、手順の進行状況、および顧客がプロセスの要件に基づいて行動するための重要な情報についてのガイダンスを提供します。 メッセージセンターの通知は、次のマイルストーンで提供されます。

- 移行の開始 (Azure AD の移行が開始されるまでの5営業日)
- Azure AD の移行の完了
- サブスクリプションとライセンスの移行の完了
- SharePoint の移行の完了
- Exchange の移行の完了
- Skype for Business の完了
- ダイナミクスの完了
- Power BI の完了
- 最後のサービスのカットオーバーが完了

## <a name="moving-to-the-new-german-regions"></a>新しいドイツ リージョンへの移動

既存の Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸陸地) お客様は、Office 365、Dynamics 365 カスタマー契約、および電源プラットフォームのお客様の移行を開始できます。 最初のステップは、新しいドイツのデータセンター リージョンへの [Microsoft 主導の移行にオプトインする](https://aka.ms/office365germanymoveoptin)ことです。 サブスクリプションを更新すると、Microsoft がサポートする移行のオプトインが自動的に選択されます。 Microsoft は、この問題が発生した場合に、顧客のテナント管理者に電子メールを通知し、Microsoft 365 管理センターのメッセージセンターに通知します。 ただし、すぐにプロセスを開始する場合は、Microsoft 365 管理センターで直接 [オプトイン](https://aka.ms/office365germanymoveoptin) することができます。 移行は2021の初期段階で開始される予定であり、2021年10月29日までに完了します。 

移行の結果、主要な顧客データおよびサブスクリプションは新しいドイツ リージョンへと移動します。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>新しいドイツのデータセンター リージョンでの Office 365 サービスへの移行を準備する方法

最初の手順として、新しいドイツデータセンターリージョンの Microsoft Cloud Deut上陸陸から Office 365 サービスにサブスクリプションとデータを移行する権限があることを Microsoft に通知します。 手順については、「 [オプトインプロセス」](https://aka.ms/office365germanymoveoptin) を参照してください。次の点に注意してください。

- すべての移行お客様は、Office 365 Services [office 365 の url と IP アドレス](urls-and-ip-address-ranges.md)への接続を確認する必要があります。これには、新しいドイツ語のデータセンター地域が含まれます。 Inaction を実行すると、サービスとクライアントの障害が発生する可能性があります。
- ドイツ地域への移行によって、組織が使用できる機能とサービスについては、「Office 365 プラットフォームサービスの説明」を参照してください。
- 試用版サブスクリプションは移行されず、すべての有料サブスクリプションの移行がブロックされます。 移行を開始する前に、すべての試行をキャンセルするか、有料サブスクリプションに変換する必要があります。

## <a name="where-do-i-go-from-here"></a>ここから先に進むことができます。

次のよく寄せられる質問セクションを確認してください。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="is-migration-required"></a>移行は必要ですか ?

Microsoft は、新しいドイツ語のデータセンターリージョンにある Microsoft Cloud Deut上陸ランドから Office 365 サービスへの Office 365 テナント移行を追加料金なしで提供しています。 新しいドイツのデータセンターリージョンへの移行をオプトインすることを強くお勧めしますが、今後も Microsoft Cloud Deut/陸の地域に必要なセキュリティ更新プログラムを提供することをお勧めします。

新しいドイツ語のデータセンターリージョンの Office 365 サービス:

- [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/)、および [Power BI](https://powerbi.microsoft.com/pricing/) について、市場競争力のある価格を提供します。
- は Microsoft&#39;のグローバルネットワークに接続されており、何百ものネットワークエッジサイト、ピアリング場所、および出口を提供して、世界中のあらゆる場所で堅牢なユーザー環境を提供します。
- ドイツ国内での顧客データの常駐要件を満たすのに役立ちます。
- Microsoft が提供するサービスの最新バージョンと、Office 365 の Microsoft Teams と複数地域を含む新機能を備えた、完全な機能を備えたグローバルクラウド製品を提供します。 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、[Office 365](o365-data-locations.md)、[Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) について、地域ごとに製品を比較します。
- 完全な機能、エンタープライズグレードのセキュリティ、および包括的な機能を提供し、顧客がコンプライアンスおよび規制要件を満たすのを支援します。
- 既存のオンライン サービス契約を通じてアクセスできます。

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>さまざまな Office 365 クラウド サービス間のサービス可用性はどのくらいですか?

次の15個のサービスは、Microsoft Cloud Deut/陸 cloud service サービスで提供されています。 Microsoft Cloud Deut上陸陸に新しいサービスを追加していません。

1. Exchange Online
2. カスタマー ロックボックス (Exchange Online)
3. グループ (モダン グループ)
4. Delve プロファイル
5. Exchange Online Protection
6. Advanced Threat Protection (ATP)
7. Advanced eDiscovery
8. 高度なデータ ガバナンス
9. SharePoint Online
10. カスタマー ロックボックス (SharePoint Online)
11. OneDrive for Business
12. Skype for Business Online
13. Word Online、Excel Online、PowerPoint、OneNote、Visio Online
14. Office 365 Pro Plus
15. Outlook モバイル

現在、新しいドイツのデータセンター リージョンでの Office 365 サービスの一部として 29 のサービスを利用できます。 新しい機能とサービスは、グローバルな Office 365 サービスと一貫性を持つ形で継続的に利用可能になります。

1. Exchange Online
2. Exchange Online のカスタマーロックボックス
3. Microsoft 365 グループ
4. Delve プロファイル
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Advanced Threat Protection (ATP)
9. Advanced eDiscovery
10. Advanced Security Management
11. Information Rights Management
12. 高度なデータ ガバナンス
13. SharePoint Online
14. SharePoint Online のカスタマーロックボックス
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (移行中に Microsoft Teams に移行します)
18. クラウド PBX
19. PSTN 会議
20. PSTN 通話
21. Microsoft Teams
22. 管理者レポート/利用状況レポート
23. Word Online、Excel Online、PowerPoint、OneNote、およびVisio Online
24. Planner
25. Sway
26. Microsoft 365 アプリ
27. Outlook モバイル
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1、Intune、および Rights Management Service)
29. Yammer Online

### <a name="when-will-migration-happen"></a>移行はいつ行われますか ?

**Azure**

Azure お客様のみである場合は、Azure リソースの現在の [移行](https://docs.microsoft.com/azure/germany/germany-migration-main) を開始できます。 Office 365、Dynamics 365、または Power BI で Azure を使用している場合は、次の手順を実行してください。

**Office 365**

今すぐ、Microsoft 主導の移行に[オプトイン](https://aka.ms/office365germanymoveoptin)してください。 移行を開始する準備ができたら、Microsoft 365 管理センターのメッセージセンターで通知されます。

**Dynamics 365 および Power BI**

[Dynamics 365 のカスタマーエンゲージメント](https://aka.ms/D365ceOptIn)および[Power BI](https://aka.ms/PBIOptIn)の Microsoft による移行を選択します。 移行を開始する準備ができたら、Microsoft 365 管理センターのメッセージ センターからお知らせします。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>使用する Office 365 サービスの価格は変わりますか?

はい。 Microsoft&#39;のグローバルクラウド地域 (新しいデータセンターリージョンを含む) の価格設定は一般的に低くなります。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>サブスクリプションの移行中に、どの Sku およびライセンスが組織とユーザーに適用されますか。

Microsoft クラウドの統合によって Office 365 サービスに移行する際に、ドイツのサービス固有の Sku は同じまたは類似した SKU のグローバルバージョンに置き換えられます。 ほとんどの場合、Office 365 services の SKU は同じですが、ドイツの SKU が Office 365 サービスで利用できなくなった場合、置換はほとんどありません。 移行の完了後に組織に割り当てられている SKU を更新する場合は、販売者に連絡して、割り当てられたサービスを追加または変更してください。

| Microsoft Cloud Deut土地-製品 SKU (DE) | Microsoft クラウドグローバル-製品 SKU (WW) |
| --- | --- |
| 顧客ロックボックスの \_ 解除 (ロックボックスの \_ 解除) | 顧客ロックボックス (ロックボックス) |
| Dynamics 365 Enterprise Edition-追加のデータベースストレージ \_ DE (CRMSTORAGE \_ de) | Dynamics 365 Enterprise Edition-追加のデータベースストレージ (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition-追加の非運用インスタンスの \_ de (CRMTESTINSTANCE \_ de) | Dynamics 365 Enterprise Edition-追加の非運用インスタンス (CRMTESTINSTANCE) |
| Customer Service Enterprise Edition \_ de (DYN365 \_ enterprise \_ customer \_ service \_ de) の Dynamics 365 | Customer Service Enterprise Edition の Dynamics 365 (DYN365 \_ enterprise \_ Customer \_ service) |
| Dynamics 365 for Sales Enterprise Edition \_ de (DYN365 \_ enterprise \_ Sales \_ de) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ Enterprise \_ Sales) |
| Dynamics 365 for teams Members Enterprise Edition \_ de (DYN365 \_ enterprise \_ Team \_ members \_ de) | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ enterprise \_ Team \_ members) |
| Dynamics 365 プラン 1 Enterprise Edition \_ DE (DYN365 \_ Enterprise \_ PLAN1 \_ de) | Dynamics 365 プラン 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1) |
| ECAL サービス (EOA、EOP、DLP) \_ DE (ecal \_ services \_ de) | ECAL サービス (EOA、EOP、DLP) (ECAL \_ サービス) |
| Enterprise Mobility + Security E3 \_ de (EMS \_ de) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (プラン 1) \_ DE (EXCHANGESTANDARD \_ DE) | Exchange Online (プラン 1) (EXCHANGESTANDARD) |
| Exchange Online (プラン 2) \_ DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (プラン 2) (EXCHANGEENTERPRISE) |
| Exchange online の exchange online のアーカイブ \_ (EXCHANGEARCHIVE \_ ADDON \_ de) | Exchange online の exchange Online アーカイブ (EXCHANGEARCHIVE \_ アドオン) |
| Exchange Server DE の exchange Online アーカイブ \_ (EXCHANGEARCHIVE \_ DE) | Exchange Server 用の exchange Online アーカイブ (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ de (exchange \_ ! \_ essentials \_ de) | Exchange Online Essentials (EXCHANGE \_ ! \_ essentials) |
| Exchange Online Kiosk \_ de (exchangeている \_ ) | Exchange Online Kiosk (EXCHANGEを低) |
| Exchange Online Protection \_ de (EOP \_ ENTERPRISE \_ de) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ Business \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ Business \_ PREMIUM) |
| Microsoft Dynamics CRM Online インスタンスの \_ DE (CRMINSTANCE \_ de) | Microsoft Dynamics CRM Online インスタンス (CRMINSTANCE) |
| Office 365 A1 for faculty \_ DE (STANDARDWOFFPACK \_ 教職員 \_ de) | Office 365 A1 for faculty (STANDARDWOFFPACK \_ 教職員) |
| 学生の Office 365 A1 \_ (STANDARDWOFFPACK \_ STUDENT \_ de) | 学生用 Office 365 A1 (STANDARDWOFFPACK \_ STUDENT) |
| Office 365 Advanced コンプライアンス \_ de (EQUIVIO \_ ANALYTICS \_ de) | Microsoft 365 E5 コンプライアンス (情報 \_ 保護 \_ コンプライアンス) |
| Office 365 Advanced Threat Protection (Plan 1) \_ DE (ATP \_ ENTERPRISE \_ DE) | Office 365 Advanced Threat Protection (プラン 1) (ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ de (O365 \_ Business \_ Essentials \_ de) | Microsoft 365 Business Basic (O365 \_ Business \_ ESSENTIALS) |
| Office 365 Business Premium \_ de (O365 \_ Business \_ premium \_ de) | Microsoft 365 Business Standard (O365 \_ Business \_ PREMIUM) |
| Office 365 Business \_ de (O365 \_ Business \_ de) | Microsoft 365 Apps for business (O365 \_ business) |
| Office 365 E1 \_ de (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| ProPlus de を使用しない Office 365 E3 \_ (ENTERPRISEPACKWITHOUTPROPLUS \_ de) | Office 365 E3 (ProPlus なし) (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ de (STANDARDPACK \_ de) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 特別なファイル記憶域の \_ 除外 (SHAREPOINTSTORAGE \_ de) | Office 365 の特別なファイル記憶域 (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ de (DESKLESSPACK \_ de) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus for Faculty \_ de (OFFICESUBSCRIPTION \_ 教職員 \_ de) | Office 365 ProPlus for Faculty (OFFICESUBSCRIPTION \_ 教職員向け) |
| Office 365 ProPlus for Students \_ (OFFICESUBSCRIPTION \_ STUDENT \_ de) | 学生用 Office 365 ProPlus (OFFICESUBSCRIPTION \_ STUDENT) |
| Office 365 ProPlus \_ de (OFFICESUBSCRIPTION \_ de) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive for Business (プラン 1) \_ DE (WACONEDRIVE 標準 \_ DE) | OneDrive for Business (プラン 1) (WACONEDRIVE STANDARD) |
| OneDrive for Business (プラン 2) \_ DE (WACONEDRIVE enterprise \_ de) | OneDrive for Business (プラン 2) (WACONEDRIVE ENTERPRISE) |
| Power BI Pro for faculty \_ DE (power \_ bi \_ pro \_ 教職員 \_ de) | Power BI Pro for faculty (POWER \_ bi \_ pro \_ 教職員) |
| Power BI Pro \_ de (power \_ bi \_ pro \_ de) | Power BI Pro (POWER \_ bi \_ pro) |
| Project Online Essentials \_ de (PROJECTESSENTIALS \_ de) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ de (PROJECTPREMIUM \_ de) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ de (PROJECTPROFESSIONAL \_ de) | Project Online Professional (PROJECTPROFESSIONAL) |
| プロジェクト計画 3 \_ DE (PROJECTPROFESSIONAL \_ de) | プロジェクト計画 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (プラン 1) \_ DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (プラン 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (プラン 2) \_ DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (プラン 2) (SHAREPOINTENTERPRISE) |
| Skype for Business Online (プラン 1) \_ de (MCOIMP \_ de) | Office 365 E1 (STANDARDPACK) |
| Skype for Business Online (プラン 1) \_ de (MCOIMP \_ de) | Skype for Business Online (プラン 1) (MCOIMP) |
| Skype for Business Online (プラン 2) \_ DE (MCOSTANDARD \_ de) | Skype for Business Online (プラン 2) (MCOSTANDARD) |
| Skype for Business Plus CAL \_ de (MCOPLUSCAL \_ de) | Skype for Business Plus CAL (MCOPLUSCAL) |
| Visio Online プラン 1 for faculty \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Online プラン 1 for faculty (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online プラン 1 \_ DE (VISIOONLINE \_ PLAN1 \_ de) | Visio Online プラン 1 (VISIOONLINE \_ PLAN1) |
| 教職員 de の Visio Online プラン 2 \_ (VISIOCLIENT \_ 教職員 \_ de) | 教職員用の Visio Online プラン 2 (VISIOCLIENT \_ 教職員) |
| Visio Online プラン 2 \_ de (VISIOCLIENT \_ de) | Visio Online プラン 2 (VISIOCLIENT) |
| Visio プラン 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio プラン 1 (VISIOONLINE \_ PLAN1) |
| Visio プラン 2 \_ de (VISIOCLIENT \_ de) | Visio プラン 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>新しいリージョンに移行したりサポートの質問に答えたりするために、Microsoft からヘルプを得るにはどうすればよいですか ?

ご質問がある場合は、弊社またはパートナーにお問い合わせください。

- Azure の場合、Azure ポータルで[新しいサポート リクエスト](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)を送信できます。
- Office 365 では、 &quot; &quot; [Microsoft 365 管理センター](https://portal.office.de/)の [ヘルプが必要ですか?] リンクを使用して、質問を送信することができます。
- Dynamics 365 カスタマーエンゲージメントおよび Power BI のお客様で、かつ Office 365 も所有している場合は、「 &quot; 必要なヘルプ」を参照してください。 &quot; [Microsoft 365 管理センター](https://portal.office.de/)のリンクを使用して、質問を送信することができます。 Dynamics 365 Customer Engagement のサポート オプションは[こちら](https://docs.microsoft.com/dynamics365/get-started/support/)にあります。 Power BI のサポート オプションは[こちら](https://powerbi.microsoft.com/support/)にあります。

## <a name="more-information"></a>詳細情報

新しいドイツ語のデータセンターリージョンへの移行に関するその他の情報が出てきます。 このページにブックマークを作成し、チェックインして現在の状態を維持できるようにします。

- [Microsoft Cloud Deutschland 移行アシスタント](https://aka.ms/germanymigrateassist)
- [移行のオプトイン方法](https://aka.ms/office365germanymoveoptin)
- [Dynamics 365 移行プログラム情報](https://aka.ms/d365ceoptin)
- [Power BI 移行プログラム情報](https://aka.ms/pbioptin)
- [Office 365 の URL と IP アドレスの範囲](https://aka.ms/o365endpoints)
- [Microsoft Teams へのアップグレードを開始する](https://aka.ms/SkypeToTeams-Home)
