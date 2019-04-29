---
title: Microsoft 365 Enterprise のワークロードとシナリオ
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 組織のユーザーを Microsoft 365 Enterprise の生産性ワークロードへ参加させます。
ms.openlocfilehash: 30dbf913016687025c6159f1f1fc311462a13d29
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400141"
---
# <a name="microsoft-365-enterprise-workloads-and-scenarios"></a>Microsoft 365 Enterprise のワークロードとシナリオ

Microsoft 365 Enterprise の創造性とチームワークのメリットを得るため、次のワークロードを基礎インフラストラクチャに展開します。

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint Online](sharepoint-online-onedrive-workload.md)

組織全体を Microsoft 365 Enterprise に移行するための一般的なロードマップについては、[移行](migration-microsoft-365-enterprise-workload.md)ワークロードを参照してください。Microsoft 365 Enterprise には Microsoft Office クライアント製品、オンプレミス Office サーバー製品、および Microsoft Windows ベースのデバイスが含まれます。

シナリオは Microsoft 365 Enterprise 全体から機能およびサービスを統合された方法で使用し、ビジネスニーズに対応します。 そうしたニーズの 1 つは Microsoft 365 に格納されている規制の厳しいデータを保護することです。 規制の厳しいデータには次に示すデジタル資産が含まれています。

- 地域の規制を遵守しているデータ。
- 企業秘密、財務情報、人事情報、組織戦略など、組織にとって最も重要なデータ。

こうしたデータを内外の脅威から保護するには、「[Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには](teams-sharepoint-online-sites-highly-regulated-data.md)」の手順を参照してください。 このシナリオは段階を追って SharePoint Online サイトまたは Microsoft Teams チームを設定し、最も重要なデータを安全に保管します。

Microsoft 365 Enterprise 展開ガイド全体のワークロードとシナリオを次に示します。

![](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a>基盤インフラストラクチャの前提条件

*理想的には*、[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)のすべてのフェーズを設定した後で、ワークロードとシナリオを展開する必要があります。 これにより、基になるすべてのレイヤーがユーザーとそのデバイスに対して統合、セキュリティ、および最適な操作性を提供できるようになります。

| フェーズ | 結果 |
|:-------|:-----|
| ネットワーク | Microsoft 365 のクラウド サービスに対して最適なパフォーマンスを得るためにネットワークが更新されます。 |
| ID | ユーザー アカウントの強力な認証と管理アカウントの保護により、ID は同期されセキュリティで保護されます。 |
| Windows 10 Enterprise | Windows 7 または Windows 8.1 を実行しているコンピューターは Windows 10 Enterprise にアップグレードすることができ、新しいデバイスは Windows 10 Enterprise と共にインストールされます。 |
| Office 365 ProPlus | Microsoft Office の既存のユーザーは Office 365 ProPlus にアップグレードすることができます。 |
| モバイル デバイス管理 | デバイスを登録し、管理することができます。 |
| 情報保護 | Office 365 のセキュリティ機能が有効で、機密または Azure Information Protection ラベルはドキュメントを保護する準備ができています。 |

これは理想的であり、計画、構成、テスト、およびパイロットのために時間がかかる場合があることに注意してください。特に既存のインフラストラクチャで複数の場所が対象になる大規模な組織が該当します。 こうしたレイヤーのすべてをあらゆる場所に配置することは、Microsoft 365 Enterprise からビジネス上の価値をより迅速に得るためには必要ありません。 

すぐに展開するための一般的なワークロードを以下に示します。 

- 基盤インフラストラクチャの **ID** レイヤーがユーザーにロールアウトされた後で、多くの組織は以下を展開します。
  - [Office 365 ProPlus](office365proplus-infrastructure.md)。[OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) を組み合わせます。 Office 365 ProPlus は先進的な認証のセキュリティと最新の Microsoft Office クライアントのユーザー エクスペリエンスを提供します。 ユーザーの個人用ファイルを OneDrive for Business に移行するとインフラストラクチャが削減され、ホーム フォルダーとドライブをサポートする必要性も少なくなります。
  - [Exchange Online](exchangeonline-workload.md)。ユーザーはクラウド ベースのメールの使用できるようになります。
- 厳しく規制されたデジタル資産をすぐにクラウドで使用する必要がない場合は、**情報保護**レイヤーの前に [Microsoft Teams](teams-workload.md) と [SharePoint Online](sharepoint-online-onedrive-workload.md) をユーザー向けに展開します。

ビジネス ニーズの達成が最高になるように、基盤インフラストラクチャの前提となるフェーズの設定について最適な順序と展開を決定する必要があります。

### <a name="best-practice"></a>ベスト プラクティス

ユーザーを何らかのワークロードまたはシナリオに参加させる前に、基盤インフラストラクチャの **ID** フェーズを展開しロールアウトすることを強く推奨します。

**ID** フェーズでは、クラウド ベースの ID は、クラウド専用であるかオンプレミスの Active Directory Domain Services (AD DS) と同期されているかにかかわらず、認証とアクセスの管理のためにユーザーおよびコンピューター アカウントとグループを含むようになります。 Microsoft 365 クラウドに組織のデジタル資産を配置する前に、すべてのユーザーの強力な認証のほか管理者アカウントの強力な保護が必要です。

全体的なパフォーマンスにとって基本的で非常に重要ですが、Microsoft 365 のアプリケーションとサービスのパフォーマンスは時間の経過とともに向上することを考慮すると、使用するネットワークにおける**ネットワーキング** フェーズのロールアウトはユーザーをワークロードに参加させながら進めることができます。

これは特に複数の場所とエッジ デバイスとインターネット接続が混在する企業にあてはまります。
