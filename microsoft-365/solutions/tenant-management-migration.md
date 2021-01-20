---
title: 手順 4. エンタープライズ テナント向け Microsoft 365 の移行
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナント用Office Windows デバイス、Office クライアント アプリ、およびサーバーを移行します。
ms.openlocfilehash: 3230f7e1087b573691f04b9335a15b4ad6d20b65
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908626"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>手順 4. エンタープライズ テナント向け Microsoft 365 の移行

ほとんどの企業組織には、オペレーティング システム、クライアント ソフトウェア、およびサーバー ソフトウェアの複数のリリースを含む異種環境があります。 Microsoft 365 enterprise には、IT インフラストラクチャの主要なコンポーネントの最も安全なバージョンが含まれています。 また、クラウド テクノロジを活用するように設計された生産性機能も含まれています。

Microsoft 365 enterprise 統合製品スイートのビジネス価値を最大限に高めるには、次のリリースを移行する戦略の計画と実装を開始します。

| 送信元 | 宛先 |
|:-------|:-----|
| Windows 7 および Windows 8.1 | Windows 10 Enterprise |
| Officeのデバイスにインストールされているクライアント製品を管理する | Microsoft 365 Apps for enterprise |
| Officeサーバーにインストールされているサーバー製品を管理する | Microsoft 365 の同等のクラウドベースのサービス |
|  |  |

## <a name="migrating-to-windows-10"></a>Windows 10 への移行

各 Microsoft 365 enterprise ライセンスには、Windows 10 Enterprise のライセンスが含まれています。 Windows 7 または Windows 8.1 を実行するデバイスを移行するには、一時アップグレードを実行します。 Windows 7 のサポートは *、2020 年 1 月 14 日に終了しました*。 

一時アップグレード以外に Windows 10 Enterprise をインストールするその他の方法については [、Windows 10 の展開シナリオに関するページをご覧ください](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。 自分で[Windows 10 の展開を計画](https://aka.ms/planforwin10deployment)することもできます。

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise への移行

Microsoft 365 for enterprise には、Microsoft クラウドからインストールおよび更新される Office クライアント製品 (Word、PowerPoint、Excel、Outlook) のバージョンである Microsoft 365 Apps for enterprise が含まれています。 詳細については [、「Microsoft 365 Apps for enterprise について」を参照してください](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。

2019 以前のバージョンのコンピューターを最新Officeするのではなく、次の手順を実行します。

1. ユーザーに Microsoft 365 ライセンスを取得して割り当てる。
2. コンピューター Office 2013 2016 Officeまたは 2016 をアンインストールします。
3. Microsoft 365 Apps for enterprise を個別に、または IT ロールアウト中にインストールします。 詳細については [、Microsoft 365 アプリの展開ガイドを参照してください](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)。

Microsoft 365 Apps for enterprise は、セキュリティ更新プログラムと新しい機能更新プログラムの両方を自動的にインストールし、Microsoft 365 のクラウドベースのサービスを活用してセキュリティと生産性を強化できます。

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>オンプレミスのサーバーとデータを Microsoft 365 に移行する

Microsoft 365 for enterprise には、Web ブラウザーや Outlook クライアントなど、オンプレミス バージョンの Office サーバー ソフトウェアと同じツールの一部を使用するクラウドベースのバージョンの Office サーバー サービスが含まれています。 これらのクラウドベースのサービスは、セキュリティと新機能のために自動的に更新されます。 移行後、IT 部門はオンプレミス サーバーの保守と更新にかかる時間を節約できます。

特定の Microsoft 365 ワークロードのユーザーとデータの移行に関する情報については、次のリソースを使用してください。

- [オンプレミスのメールボックスから Exchange Online Exchange Serverメールボックスを移動する](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [SharePoint Server から SharePoint Online に SharePoint データを移行する](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [Skype for Business Online を Microsoft Teams に移行する](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>組織全体の移行

組織全体を Microsoft 365 enterprise の製品とサービスに移行する方法をより良く理解するには、次の移行ポスターをダウンロードしてください。

[![Microsoft 365 への移行ポスターを示す画像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

この2ページのポスターをご覧になると、既存のインフラストラクチャを簡単にインベントリできます。 Microsoft 365 enterprise の製品またはサービスへの移行に関するガイダンスを受け取る場合に使用します。 Windows と Office製品、デバイス管理、ID と脅威の保護、情報保護とコンプライアンスなどの他のインフラストラクチャとセキュリティ要素を示します。

## <a name="results-of-step-4"></a>手順 4 の結果

Microsoft 365 テナントの移行では、次の点を決定しました。

- Windows 7 または Windows 8.1 を実行しているデバイスと、それらを Windows 10 Enterprise に更新する計画。
- Office クライアント アプリを実行しているデバイスと、それらを Microsoft 365 Enterprise アプリに更新する計画。
- どのオンプレミスの Office サーバー サービスを Microsoft 365 と同等のサービスに移行し、それらのサービスとそのデータを移行する計画を立てるべきか。

オンプレミス サーバーの移行が完了したテナントの例を次に示します。

![オンプレミス サーバーの移行が完了したテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

この図では、組織には次の機能があります。

- オンプレミスのメールボックスを Exchange Online Exchange Server移行しました。
- オンプレミスの SharePoint Server サイトとデータを Microsoft 365 の SharePoint に移行しました。

## <a name="ongoing-maintenance-for-migration"></a>移行の継続的なメンテナンス

継続的に、次の必要が生じ得る場合があります。

- Exchange メールボックスの移行の状態に応じて、引き続き Exchange Online への組織への移行を展開します。
- オンプレミスの SharePoint サイトの移行の状態に応じて、Microsoft 365 の SharePoint への移行を引き続き組織に展開します。

## <a name="next-step"></a>次の手順

[![手順 5.デバイスとアプリの管理を展開する](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

デバイスと [アプリの管理を続行して、](tenant-management-device-management.md) デバイスとアプリの管理を展開します。
