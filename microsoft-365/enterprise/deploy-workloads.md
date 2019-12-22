---
title: Microsoft 365 Enterprise のワークロードおよびシナリオ
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 組織のユーザーを Microsoft 365 Enterprise の生産性向上ワークロードに参加させます。
ms.openlocfilehash: ff0e4b06972ed53933eb7780759bfcd53e286353
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801902"
---
# <a name="microsoft-365-for-enterprise-workloads-and-scenarios"></a>Microsoft 365 Enterprise のワークロードおよびシナリオ

Microsoft 365 Enterprise の創造性およびチームワークに関するメリットを得るには、これらのワークロードを基盤インフラストラクチャに展開します。

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint および OneDrive](sharepoint-online-onedrive-workload.md)

組織全体を Microsoft 365 Enterprise に移行するための一般的なロードマップについては、[移行](migration-microsoft-365-enterprise-workload.md)に関する記事を参照してください。それには Microsoft Office クライアント製品、オンプレミス Office サーバー製品、および Microsoft Windows ベースのデバイスが含まれます。

シナリオは Microsoft 365 Enterprise の機能およびサービスを統合的に使用し、ビジネス ニーズに対応します。 

こうした必要性の 1 つは、従業員がイントラネットに直接接続していない場合に、従業員が生産的かつ安全に作業できることを保証することです。 インフラストラクチャ要素を展開して、Teams や Exchange Online などの主要なワークロードの導入をリモート ユーザーに促すためのロードマップについては、「[リモート ワーカーの強化](empower-people-to-work-remotely.md)」のシナリオを参照してください。

こうした必要性のもう 1 つは、Microsoft 365 に格納されている規制の厳しいデータを保護することです。 規制の厳しいデータには次に示すデジタル資産が含まれています。

- 地域の規制を遵守しているデータ。
- 企業秘密、財務情報、人事情報、組織戦略など、組織にとって最も重要なデータ。

このデータを内部および外部の脅威から保護するには、次を参照してください。

- [厳しく規制されたデータ用の Teams](secure-teams-highly-regulated-data-scenario.md)
- [厳しく規制されたデータ用の SharePoint サイト](teams-sharepoint-online-sites-highly-regulated-data.md) 

これらのシナリオでは、段階を追って Microsoft Teams チームまたは SharePoint サイトを構成して、最も重要なデータを安全に保管します。

全体的な Microsoft 365 Enterprise 展開ガイドのワークロードおよびシナリオは次のとおりです。

![全体的な Microsoft 365 Enterprise 展開ガイドのワークロードおよびシナリオ](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

その他のシナリオについては、「[Microsoft 365 生産性ライブラリ](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)」を参照してください。 

## <a name="foundation-infrastructure-prerequisites"></a>基盤インフラストラクチャの前提条件

*理想的には*、[基盤インフラストラクチャ](deploy-foundation-infrastructure.md)のすべてのフェーズを設定した後で、ワークロードとシナリオを展開する必要があります。 これにより、基になるすべての基盤レイヤーがユーザーとそのデバイスに対して統合、セキュリティ、および最適な操作性を提供できるようになります。

| フェーズ | 結果 |
|:-------|:-----|
| ネットワーク | Microsoft 365 のクラウド サービスに対して最適なパフォーマンスを得るためにネットワークが更新されます。 |
| ID | ユーザー アカウントの強力な認証と管理アカウントの保護により、ID は同期されセキュリティで保護されます。 |
| Windows 10 Enterprise | Windows 7 または Windows 8.1 を実行しているコンピューターは Windows 10 Enterprise にアップグレードすることができ、新しいデバイスは Windows 10 Enterprise と共にインストールされます。 |
| Office 365 ProPlus | Microsoft Office の既存のユーザーは Office 365 ProPlus にアップグレードすることができます。 |
| モバイル デバイス管理 | デバイスを登録し、管理することができます。 |
| 情報保護 | Office 365 の情報保護機能が構成されると、機密ラベルまたは Azure Information Protection ラベルでドキュメントを保護する準備が整います。 |

これは理想的であり、計画、構成、テスト、およびパイロットのために時間がかかる場合があることに注意してください。特に既存のインフラストラクチャで複数の場所が対象になる大規模な組織が該当します。 すべての場所でこれらのフェーズを完了させることは、Microsoft 365 Enterprise からビジネス上の価値をより迅速に得るためには必要ありません。 

すぐに展開するための一般的なワークロードを以下に示します。 

- 基盤インフラストラクチャの **ID** フェーズがユーザーにロールアウトされた後で、多くの組織は以下を展開します。
  - [Office 365 ProPlus](office365proplus-infrastructure.md) と [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) の組み合わせ。 Office 365 ProPlus は先進的な認証のセキュリティと最新の Microsoft Office クライアントのユーザー エクスペリエンスを提供します。 ユーザーの個人用ファイルを OneDrive に移行すると、インフラストラクチャが削減され、ホーム フォルダーとドライブをサポートする必要性が少なくなります。
  - [Exchange Online](exchangeonline-workload.md)。ユーザーはクラウド ベースのメールの使用できるようになります。
- 厳しく規制されたデジタル資産をすぐにクラウドに保存する必要がない場合は、**情報保護**フェーズの前に [Microsoft Teams](teams-workload.md) と [SharePoint](sharepoint-online-onedrive-workload.md) をユーザー向けに展開します。

ビジネス ニーズを満たすように、基盤インフラストラクチャの前提となるフェーズの設定について最適な順序と展開を決定する必要があります。

### <a name="best-practice"></a>ベスト プラクティス

ユーザーを何らかのワークロードまたはシナリオに参加させる前に、基盤インフラストラクチャの **ID** フェーズを展開しロールアウトすることを強く推奨します。

**ID** フェーズでは、クラウド ベースの ID は、クラウド専用であるかオンプレミスの Active Directory Domain Services (AD DS) と同期されているかにかかわらず、認証とアクセスの管理のためにユーザーおよびコンピューター アカウントとグループを含むようになります。 Microsoft 365 クラウドに組織のデジタル資産を配置する前に、すべてのユーザーの強力な認証のほか管理者アカウントの強力な保護が必要です。

全体的なパフォーマンスにとって基本的かつ非常に重要なことですが、Microsoft 365 のワークロードとサービスのパフォーマンスが時間と共に向上することを考慮すると、ユーザーをワークロードに参加させながら **ネットワーキング** フェーズのロールアウトを進行させることができます。 これは特に複数の場所とエッジ デバイスとインターネット接続が混在する企業にあてはまります。
