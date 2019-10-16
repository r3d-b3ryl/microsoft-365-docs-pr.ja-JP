---
title: Microsoft 365 Enterprise の Microsoft Teams を展開する
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 組織全体で Microsoft Teams について学習し、展開していきます。
ms.openlocfilehash: 2e34c4fcada0f80c597faf89b221321ffa9183ba
ms.sourcegitcommit: 31392b9599f4b4e9981a1278d6beb9f0a2839ecf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2019
ms.locfileid: "37503393"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>Microsoft 365 Enterprise の Microsoft Teams を展開する

*このワークロードは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに該当します*

Microsoft Teams には、チャット、会議、ドキュメント共有、会話スレッド機能が組み込まれており、コンテンツの作成とグループ間でのコンテンツの共有を容易にします。Teams は、Microsoft 365 Enterprise でチーム作業と共同作業を行うためのコンポーネントであり、Microsoft 365 の Built for Teamwork の価値の重要な要素です。 

Teams を初めて利用する場合は、「[Microsoft Teams へようこそ](https://docs.microsoft.com/MicrosoftTeams/teams-overview)」を参照してください。 


## <a name="roll-out-teams-to-your-organization"></a>Teams を組織に展開する

開始する前に:

- チームに必要なユーザー アカウントとセキュリティ機能が備わるように、適切な[基礎インフラストラクチャチャ](deploy-foundation-infrastructure.md)のフェーズが設定されていることを確認します。 ID および情報保護のフェーズは、保持および機密ラベルが付いた安全な電子メールおよびファイルにサイン オンして使用するのに最も重要です。
- [この記事](https://docs.microsoft.com/microsoftteams/security-compliance-overview)では、Teams のセキュリティとコンプライアンスについて説明します。
- [この記事](https://docs.microsoft.com/microsoftteams/office-365-licensing)では、Teams 向け Office 365 のライセンスについて説明します。

組織で Teams を展開するには、「[Teams のロールアウト方法](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams)」をご覧ください。

Teams 機能の最初のセットについては、「[Microsoft Teams のチャット、チーム、チャネル、およびアプリ](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page)」を参照してください。

Teams のより高度な機能については、次を参照してください。

- [会議](https://docs.microsoft.com/microsoftteams/deploy-meetings-microsoft-teams-landing-page)
- [クラウド ボイス](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (Microsoft 365 Enterprise E5 が必要です)

組織の Teams の使用状況を監視するには、次を参照してください。

- [Teams でチーム間およびチーム別に分析する](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/cross-team-per-team-analytics)
- [分析とレポート](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)


## <a name="upgrade-to-teams"></a>Teams へのアップグレード

まだ行っていない場合は、まもなく Skype for Business から Microsoft Teams にアップグレードします。 Teams を始めたばかりでも、すでに Skype for Business とともに Teams を使用している場合でも、アップグレードの準備ができている場合でも、Teams への旅を成功させるために必要なもののすべてが揃っていることを確認したいと思います。

Skype for Business Online から Teams にアップグレードする場合でも、Skype for Business オンプレミス環境から Teams にアップグレードする場合でも、アップグレード フレームワークは、ビジネス シナリオに基づいたプロセスをガイドします。
 
詳細情報については、「[Microsoft Teams へのアップグレードを開始する](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)」を参照してください。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft がどのように Teams を展開し、共同作業に使用しているかについては下記を参照してください。

- [Microsoft Teams の導入戦略により、従業員は新しい仕事文化に備えることができる](https://www.microsoft.com/ja-JP/itshowcase/microsoft-teams-adoption-strategy-prepares-employees-for-a-new-culture-of-work)
- [Microsoft Teams ミーティングにより、グローバルにスケーラブルな最新の会議体験が実現できる](https://www.microsoft.com/ja-JP/itshowcase/with-microsoft-teams-rooms-comes-a-globally-scalable-modern-meeting-experience)

## <a name="next-steps"></a>次の手順

- [組織の Microsoft Teams の機能を管理する](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Microsoft Teams の管理者トレーニング](https://docs.microsoft.com/microsoftteams/itadmin-readiness)

<!--

## Phase 1: Envision

In this phase, you gather the people for your Teams deployment and determine how your organization will use Teams to address its business needs.

### Step 1: Gather your Teams deployment members

For a successful deployment of Teams on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users. 

These three groups ensure that your Teams deployment includes considerations that address business needs, technical aspects of licensing and security, and that Teams is something that your typical users will use.

#### Result

A list of people that represent the business, technical, and end user perspectives of your organization.

### Step 2: Determine and prioritize your Teams business scenarios
Teams can be used for many different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, and individual working and project teams. Take a look at the [Microsoft 365 Productivity Library](https://www.microsoft.com/microsoft-365/success/?rtc=1) for examples to help you define Teams scenarios. 

You should target Teams to address fast-moving and highly collaborative teams that work closely together and require many more facilities than just email with Exchange Online can provide. Examples are live group chats with a recorded history and a common and easy-to-find place to store files and notes. 

One way to see the benefits of Teams is to examine how a team or v-team interacts today, and then find an appropriate Teams scenario that replaces the interaction and provides easier ways to collaborate and provide additional capabilities.

#### Microsoft Teams for highly regulated data

Highly regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a team for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).

#### Result

A list of Teams scenarios that address your organization’s needs for collaboration and teamwork.

## Phase 2: Onboard

In this phase, you plan for the technical aspects of a Teams deployment and start rolling out Teams to selected groups of users.

### Prerequisites: Identity and device access configuration

To protect access to teams, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).

### Step 1: Complete your technical planning

Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365, you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *available at no additional cost* to guide you through planning, deployment and service adoption. Or, you can complete this work yourself using our FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Microsoft 365 account.

If you are doing your own planning (or in conjunction with FastTrack), you need to determine if your network and organization are ready for Teams. It is especially important that you meet the exit criteria for [networking](networking-infrastructure.md) in your foundation infrastructure for users connected to your organization network. Pay special attention to bandwidth, throughput, and traffic delays to maximize performance for Teams-based meetings.

Use these resources to prepare the technical aspects of your organization for a Teams rollout: 

- [Check your environment's readiness for Teams](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [Prepare your network for Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [Office 365 URLs and IP address ranges](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

For a better understanding of security in Teams, review the following additional resources:

- [Overview of security and compliance in Teams](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Office 365 groups and Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Guest access in Teams](https://docs.microsoft.com/microsoftteams/guest-access)

Next, use these resources to understand Teams licensing and to perform the setup of Teams for your organization:

- [Office 365 licensing for Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [Manage user access to Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [Get clients for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [Turn on Microsoft Teams in your organization](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [Manage Microsoft Teams features for your organization](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365)

#### Result

Your network, security, and Microsoft 365 licensing planning are done and you are ready to begin rolling out Teams to selected groups in your organization.

### Step 2: Run an IT pilot

In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts. During the IT pilot:

- Choose a Teams business scenario in which your IT pilot participants can practice. See the [Microsoft Teams getting started kit](http://microsoft.com/download/56505) for ideas.
- Give your pilot participants a set of exercises to test Teams-based chats, meetings, file storage, meetings, and other capabilities.
- Determine your change management strategy and produce materials to drive organization-wide user adoption. 

  Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Teams and its benefits with the goals of raising awareness and driving usage. See [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) for some ideas.

- Have your IT pilot participants review the change management strategy materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Teams and how to use it for collaboration.

#### Result

Your Teams IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.

### Step 3: Roll out to a business group

After completing your IT pilot, roll out Teams to a business group or department in your organization. This rollout should include:

- Identification of key business scenarios for Teams within the business group.
- Announcement activities to inform users of the expectations and timelines for Teams usage for departmental, work, or project teams.
- Delivery of [user training on Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) or links to resources to introduce Teams and how to use it.
- A feedback mechanism, such as a central team containing everyone in the business group, to collect comments and issues from users in the business group.

During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.

#### Result

A business group is up and running with Teams and the change management materials have been tested and refined.

## Phase 3: Drive value

In this phase, you complete the rollout of Teams to your organization and support your users so that they are realizing its benefits.

### Step 1: Roll out Teams to the rest of your organization

After completing your rollout to a targeted business group, roll out Teams to the rest of your organization. This rollout should include:

- Identification of key business scenarios for Teams within your separate business groups.
- Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Teams usage for departmental, work, or project teams.
- Delivery of [user training on Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) or links to resources to introduce Teams and how to use it.
- A feedback mechanism, such as a central team containing everyone, to collect comments and act on issues from organization users. If your organization has less than 2500 individuals, use a public team or channel in Teams. Otherwise, use a public group in Yammer.

#### Result

Your organization is up and running and your change management strategy is in place to inform, train, and enable users to begin using Teams.

### Step 2: Measure usage, manage satisfaction, and drive adoption

After rolling out Teams to your entire organization, you must continue to employ your change management strategy to:

- Have your leadership promote Teams as the teamwork and collaboration tool for the organization.
- Encourage individuals to use it for business group, departmental, work, and project team communications and collaboration.

Here are some suggested activities:

- See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption. 
- See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is to grant your user account Reports Reader permissions so you can access activity reports.
- Monitor your feedback venue (a public channel in a central team or a public Yammer group) for issues and feedback from individuals about their experiences with Teams. Address questions and issues as quickly as you can to prevent frustration and abandonment of Teams by individuals.
- Identify and nurture your champions in each business group and highlight their accomplishments and best practices using Teams. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.

#### Result

Your organization has adopted Teams as its collaboration and teamwork tool.


--> 
