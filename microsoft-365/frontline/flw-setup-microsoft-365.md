---
title: 現場担当者向けの Microsoft 365
author: samanro
ms.author: samanro
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: 現場担当者に必要なサービスと機能を使用して Microsoft 365 を設定する方法について説明します。
ms.localizationpriority: high
ms.collection:
- m365-frontline
- m365solution-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 25f33208cd52520d810efbb9d48643595c955f3e
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994673"
---
# <a name="set-up-microsoft-365-for-frontline-workers"></a>現場担当者向けの Microsoft 365

現場担当者向けの Microsoft 365 を設定するには、次の全体的なプロセスに従います。

1. **[シナリオを特定する](#step-1-identify-your-scenarios)**: 現場のワーカーに対して実装するシナリオはどれですか? 必要なシナリオを決定したら、次の表を使用して、実装する各シナリオに必要なアプリとサービスを特定します。
1. **[環境とコア Microsoft 365 を設定する](#step-2-set-up-your-environment-and-core-microsoft-365)**: Microsoft 365 管理センターのセットアップ ガイドに従って Microsoft 365 を設定します。 これらのガイドにアクセスする方法については、引き続きご覧ください。
1. **[Microsoft Teams を設定する](#step-3-set-up-microsoft-teams)**: オンボーディング ウィザードまたは大規模なプロセスでチームの展開を使用して、サービスを構成し、チームを作成します。
1. **[シナリオに必要なその他のサービスを設定する](#step-4-set-up-other-services)**: 以下のセクションの手順に従って、これらのサービスをセットアップします。
1. **[アプリを構成する](#step-5-configure-apps-for-your-scenario)**: 管理センターですべてが設定および構成されたら、シナリオのガイダンスに従って、各シナリオに必要なアプリをさらに構成できます。
1. **[デバイス](#step-6-set-up-devices)**: Microsoft 365 および Microsoft Teams と連携し、現場担当者が組織内でより安全に通信できるように、共有デバイスと個人用デバイスを設定します。

:::image type="content" source="media/m365-frontline-setup-steps.png" alt-text="Microsoft 365 for frontline workersを設定する手順。" lightbox="media/m365-frontline-setup-steps.png":::

## <a name="step-1-identify-your-scenarios"></a>手順 1: シナリオを特定する

次の表に、現場担当者のシナリオを示します。 シナリオの選択で各シナリオの概要を読み、必要な各 [シナリオ](flw-choose-scenarios.md)と各アプリまたはサービスへのリンクに従って、構成する必要がある内容を正確に確認できます。

| シナリオ | 必要なサービス |
|  ------- | -------  |
| [チームのコミュニケーションとコラボレーション](flw-team-collaboration.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Exchange Online を使用したメール](#set-up-email-with-exchange-online) |
| [企業内コミュニケーション](flw-corp-comms.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Viva コネクション](#set-up-viva-connections) <br>[Yammer](#set-up-your-organizations-social-network-with-yammer) |
| [仮想予定](virtual-appointments.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) |
| [従業員を関与させ、ウェルビーイングに集中する](flw-wellbeing-engagement.md)| [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Viva コネクション](#set-up-viva-connections) <br>[Yammer](#set-up-your-organizations-social-network-with-yammer) |
| [Shifts を使用してチームをスケジュールする](shifts-for-teams-landing-page.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) |
| [新しい従業員のオンボード](/sharepoint/onboard-employees)| [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Viva コネクション](#set-up-viva-connections) <br>[Viva ラーニング](#set-up-viva-learning)|
| [継続的なスタッフ トレーニング](flw-onboarding-training.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Viva ラーニング](#set-up-viva-learning) |
| [ビジネス プロセスの簡略化](simplify-business-processes.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Power Apps、Power Automate、Power BI](#set-up-power-apps-power-automate-and-power-bi) |

一部のサービスは、電子メールや Power Platform など、F3 ライセンスにのみ含まれています。 [現場担当者のユーザーの種類とライセンスについて](flw-licensing-options.md)確認し、ユーザーに必要なライセンスの種類を確認します。

## <a name="step-2-set-up-your-environment-and-core-microsoft-365"></a>手順 2: 環境とコア Microsoft 365 を設定する

Microsoft 365 管理センターには、Microsoft 365 で製品、セキュリティ機能、コラボレーション ツールを設定する手順を説明する[セットアップ ガイド](/microsoft-365/enterprise/setup-guides-for-microsoft-365)のセットがあります。 セットアップ ガイドには、Microsoft 365 管理センターの[セットアップ ガイダンス ページ](https://aka.ms/setupguidance)からアクセスできます。

1. [環境の準備ガイド](https://aka.ms/prepareyourenvironment)は、Microsoft 365 および Office 365 サービス用に組織の環境を準備するのに役立ちます。
1. [Microsoft 365 セットアップ](https://aka.ms/microsoft365setupguide) ガイドを使用して、生産性ツール、セキュリティ ポリシー、デバイス管理機能を設定します。 このアドバイザーを使用して、組織のデバイスを設定および構成することもできます。

## <a name="step-3-set-up-microsoft-teams"></a>手順 3: Teams for Education を設定する

パイロット プロジェクトの場合、現場担当者オンボーディング ウィザードを使用して、フロントライン ワーカー用に構成された 1 つのチームを設定できます。 詳細なガイダンスについては、「[現場担当者オンボーディング ウィザードを使用して、現場の従業員を稼働させる](flw-onboarding-wizard.md)」を参照してください。

完全なデプロイについては、「 [現場担当者の大規模なチームのデプロイ」のガイダンスに](deploy-teams-at-scale.md)従ってください。

## <a name="step-4-set-up-other-services"></a>手順 4: 他のサービスを設定する

### <a name="set-up-email-with-exchange-online"></a>Exchange Online でメールを設定する

フロントライン マネージャーと現場担当者に電子メールへのアクセス権を付与する場合は、Microsoft 365 で電子メールを設定する必要があります。 電子メールにアクセスするには、ユーザーに F3 ライセンスが必要です。 [メールのセットアップ ガイド](https://aka.ms/office365setup)に従って設定します。

ユーザーは、メールに使用する Outlook アプリをインストールすることもできます。そのため、Outlook アプリをダウンロードする場所を確実に共有する必要があります。

### <a name="set-up-sites-with-sharepoint-in-microsoft-365"></a>Microsoft 365 で SharePoint を使用してサイトを設定する

[SharePoint](/sharepoint/sharepoint-online) を使用すると、ドキュメントを共有したり、サイトを作成したりできます。 Microsoft 365 管理センターの [SharePoint セットアップ ガイド](https://aka.ms/spoguidance)を使用して設定します。

### <a name="set-up-employee-experiences-with-viva-modules"></a>Viva モジュールを使用して従業員エクスペリエンスを設定する

[Microsoft Viva](/viva/microsoft-viva-overview) は、コミュニケーション、知識、学習、リソース、および作業の流れへの分析情報をまとめる統合された従業員エクスペリエンスと従業員を結び付けるのに役立ちます。 Microsoft Viva には、Microsoft Teams で従業員エクスペリエンスを作成するために使用できるモジュールがいくつかあります。

#### <a name="set-up-viva-connections"></a>Viva コネクションのセットアップ

[Viva コネクション](/viva/connections/viva-connections-overview)を使用して、現場担当者の関与と通知に役立つダッシュボードを作成します。 Viva コネクションは、Microsoft Teams のカスタマイズ可能なアプリで、すべてのユーザーに、関連するニュース、会話、成功に必要なツールを発見するためのパーソナライズされた目的地を提供します。 

[従業員エクスペリエンスのセットアップ ガイド](https://aka.ms/EmployeeExperienceDashboard)に従って設定します。 [Viva コネクション](/viva/connections/guide-to-setting-up-viva-connections)の詳細をご覧ください。

#### <a name="set-up-viva-learning"></a>Viva ラーニングを設定する

[Viva ラーニング](/viva/learning/)は、Microsoft Teams のアプリであり、従業員がすでに使用しているツールやプラットフォーム内の作業の流れに学習を取り入れることで、学習を 1 日の自然な部分にすることができます。 Viva ラーニングを設定する方法については、「[Teams 管理センターでMicrosoft Viva ラーニングを設定する](/viva/learning/set-up-viva-learning)」を参照してください。

### <a name="set-up-your-organizations-social-network-with-yammer"></a>Yammer を使用して組織のソーシャル ネットワークを設定する

[Yammer](/yammer) は、会社全体で従業員を結び付けるのに役立ちます。 [Yammer 展開アドバイザー](https://aka.ms/yammerdeploymentguide)を使用して設定します。

### <a name="set-up-power-apps-power-automate-and-power-bi"></a>Power Apps、Power Automate、および Power BI を設定する

Microsoft Teams 内でこれらのアプリをすべて使用できます。 SSL をセットアップする方法の詳細については、以下をご覧ください。

- 詳細情報: [Power Apps と Microsoft Teams の統合](/powerapps/teams/overview)。
- [Power Automate - Microsoft Teams でフローを使用する](/power-automate/teams/overview)
- 詳細情報: [Microsoft Teams と Power BI で共同作業する](/power-bi/collaborate-share/service-collaborate-microsoft-teams)。
- ‎[Microsoft Teams で Power Virtual Agents を使用しているスクリーンショット。](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)
- [Power Apps](/microsoftteams/manage-power-platform-apps)

## <a name="step-5-configure-apps-for-your-scenario"></a>手順 5: シナリオに合わせてアプリを構成する

管理センターですべてが設定および構成されたら、シナリオのガイダンスに従って、各シナリオに必要なアプリをさらに構成できます。

シナリオとアプリ

| シナリオ | 承認 | Bookings | リスト | 称賛 | Shifts | タスク | 更新プログラム |
| :---- | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| [チームのコミュニケーションとコラボレーション](flw-team-collaboration.md) | &#x2705; | &nbsp; | &#x2705; | &#x2705; | &nbsp; | &#x2705; | &#x2705; |
| [企業内コミュニケーション](flw-corp-comms.md) |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |
| [Microsoft Teams と Bookings アプリを使用した仮想予定](bookings-virtual-visits.md) |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp;|  &nbsp; |
| ウェルビーイング & エンゲージメント |  &nbsp; |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; |
| [Shifts を使用してチームをスケジュールする](shifts-for-teams-landing-page.md) |  &nbsp; | &nbsp; | &#x2705; |  &nbsp; | &#x2705; | &#x2705; | &#x2705; |
| [トレーニング: 新しい従業員のオンボーディング](/sharepoint/onboard-employees) |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| 継続的なトレーニング |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| [ビジネス プロセスの簡略化](simplify-business-processes.md) | &#x2705; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| サイト、ストア、プロジェクトを管理する | &#x2705; |  &nbsp; | &#x2705; |  &nbsp; | &nbsp; | &#x2705; | &#x2705; |

## <a name="step-6-set-up-devices"></a>手順 6: デバイスを設定する

Microsoft 365 および Microsoft Teams と連携するように共有デバイスと個人用デバイスを設定し、現場のワーカーが組織内でより安全に通信できるようにするには、「 [現場担当者のモバイル デバイスを管理する](flw-devices.md)」を参照してください。
