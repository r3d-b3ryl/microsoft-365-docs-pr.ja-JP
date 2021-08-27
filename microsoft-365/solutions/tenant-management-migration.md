---
title: 手順 4. エンタープライズ テナントのMicrosoft 365移行
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: テナント用Windowsデバイス、Office アプリ、Office サーバーを移行Microsoft 365します。
ms.openlocfilehash: 9570a34c1c1884452ee9090ca0b7d280411e0016
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58571581"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>手順 4. エンタープライズ テナントのMicrosoft 365移行

ほとんどのエンタープライズ組織には、オペレーティング システム、クライアント ソフトウェア、およびサーバー ソフトウェアの複数のリリースを含む異種環境があります。 Microsoft 365には、IT インフラストラクチャの主要なコンポーネントの最も安全なバージョンが含まれています。 また、クラウド テクノロジを活用するように設計された生産性機能も含まれています。

エンタープライズ統合製品スイートMicrosoft 365のビジネス価値を最大化するには、次のリリースを移行するための戦略の計画と実装を開始します。

| From | へ |
|:-------|:-----|
| Windows 7 と Windows 8.1 | Windows 10 Enterprise |
| Officeのデバイスにインストールされているクライアント製品を管理する | Microsoft 365 Apps for enterprise |
| Officeサーバーにインストールされているサーバー製品を管理する | 同じクラウド ベースのサービスをMicrosoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>サーバーへのWindows 10

エンタープライズ Microsoft 365の各ライセンスには、エンタープライズ ライセンスのWindows 10 Enterprise。 7 または 7 を実行するWindowsを移行Windows 8.1、インプレイス アップグレードを実行できます。 *2020* 年 1 月 14 Windows 7 日にサポートが終了しました。 

一時アップグレードを超えてWindows 10 Enterpriseインストールするその他の方法については[、「Windows 10」を参照してください](/windows/deployment/windows-10-deployment-scenarios)。 自分で[Windows 10 の展開を計画](/windows/deployment/planning/)することもできます。

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>サーバーへのMicrosoft 365 Apps for enterprise

Microsoft 365には、microsoft クラウドからインストールおよび更新される Office クライアント製品 (Word、PowerPoint、Excel、および Outlook) のバージョンである Microsoft 365 Apps for enterprise が含まれます。 詳細については、「概要[」 を参照Microsoft 365 Apps for enterprise。](/deployoffice/about-microsoft-365-apps)

2019 以前のバージョンのコンピューターを最新Officeではなく、次の手順を実行します。

1. ユーザーのライセンスを取得Microsoft 365割り当てる。
2. コンピューター Office 2013 または Office 2016 をアンインストールします。
3. 個別Microsoft 365 Apps for enterpriseまたは IT ロールアウト中に、このファイルをインストールします。 詳細については、「[Microsoft 365 Apps の展開ガイド](/deployoffice/deployment-guide-microsoft-365-apps)」をご覧ください。

Microsoft 365 Apps for enterprise更新プログラムと新しい機能更新プログラムの両方を自動的にインストールし、セキュリティと生産性を向上Microsoft 365クラウド ベースのサービスを利用できます。

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>オンプレミスのサーバーとデータをサーバーに移行Microsoft 365

Microsoft 365には、web ブラウザーや Outlook クライアントなど、オンプレミスバージョンの Office サーバー ソフトウェアと同じツールの一部を使用するクラウドベースのバージョンの Office サーバー サービスが含まれます。 これらのクラウドベースのサービスは、セキュリティと新機能のために自動的に更新されます。 移行後、IT 部門はオンプレミス サーバーの保守と更新にかかる時間を節約できます。

特定のワークロードのユーザーとデータを移行する方法については、次Microsoft 365してください。

- [メールボックスをオンプレミスのメールボックスからExchange ServerにExchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [サーバー SharePointからオンラインにSharePointデータをSharePointする](/sharepointmigration/migrate-to-sharepoint-online)
- [オンラインSkype for Businessに移行Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>組織全体の移行

組織全体をエンタープライズ向け製品とサービスに移動する方法の詳細を確認するには、次のMicrosoft 365ポスターをダウンロードします。

[![ポスターへの移行を示Microsoft 365画像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

この2ページのポスターをご覧になると、既存のインフラストラクチャを簡単にインベントリできます。 エンタープライズ向け製品またはサービスへの移行に関するガイダンスを取得するには、このMicrosoft 365使用します。 デバイス管理Windows脅威Office、情報保護とコンプライアンスなど、製品、その他のインフラストラクチャおよびセキュリティ要素に関する情報を表示します。

## <a name="results-of-step-4"></a>手順 4 の結果

テナントの移行Microsoft 365決定しました。

- 7 または 7 WindowsをWindows 8.1するデバイスと、デバイスを更新する計画Windows 10 Enterprise。
- どのデバイスがクライアント Officeを実行し、エンタープライズ向けアプリに更新Microsoft 365計画を立てられています。
- サーバー サービスを同等Officeサーバー サービスに移行するMicrosoft 365、それらのサーバー サービスとそのデータを移行する計画。

オンプレミス サーバーの移行が完了したテナントの例を次に示します。

![オンプレミス サーバーの移行が完了したテナントの例。](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

この図では、組織には次の機能があります。

- オンプレミスのメールボックスをExchange Serverに移行Exchange Online。
- オンプレミスのサーバー サイトとデータSharePointを、サーバー 内のSharePointにMicrosoft 365。

## <a name="ongoing-maintenance-for-migration"></a>移行の継続的なメンテナンス

継続的に、次の必要が生じ得る場合があります。

- メールボックスの移行の状態に応じてExchange移行を組織にExchange Online展開します。
- オンプレミスのサイト移行の状態に応じて、SharePointに移行をSharePoint移行Microsoft 365展開します。

## <a name="next-step"></a>次の手順

[![手順 5.デバイスとアプリの管理を展開します。](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

デバイスと [アプリの管理を続行して、](tenant-management-device-management.md) デバイスとアプリの管理を展開します。