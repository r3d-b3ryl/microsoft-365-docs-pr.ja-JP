---
title: Microsoft 365 Enterprise を展開する
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 組織内で Microsoft 365 Enterprise を展開するのに使用できるリソースについて説明します。
ms.openlocfilehash: 0dcbe9e39f33cab65dff6033f0b78ceb7e1c42cc
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437867"
---
# <a name="deploy-microsoft-365-enterprise"></a>Microsoft 365 Enterprise を展開する

Microsoft 365 Enterprise は、ローカルおよびクラウドベースの生産性アプリとサービスを Windows 10 Enterprise と組み合わせたもので、次のような特徴があります。  

- インテリジェントなセキュリティを備えている。
- 簡素化のため統合されている。
- 創造性を引き出す。
- 共同作業向けに構築されている。

ユーザーは、最先端のセキュリティ サービスと機能が含まれる統合的な手法で、インフラストラクチャと生産性ワークロードを展開することにより、これらの利点を得ることができます。

Microsoft 365 Enterprise を展開するには、主に 3 つの方法があります。

- [Microsoft 365 の FastTrack](#fasttrack-for-microsoft-365) を使用して、Microsoft のエンジニアと一緒に操作する方法。
- Microsoft Consulting Services または [Microsoft partner](https://partner.microsoft.com/) を使う方法。
- [Microsoft 365 Enterprise の展開ガイド](#microsoft-365-enterprise-deployment-guide) を使って自分で操作する方法。

## <a name="fasttrack-for-microsoft-365"></a>Microsoft 365 の FastTrack

FastTrack は、自分のペースでクラウドへと移行できるよう、Microsoft のエンジニアによって提供される継続的かつ反復的なサービスです（*サブスクリプションの一部として無料で利用できます*）。 必要に応じて、追加サービスを提供する認定パートナーにアクセスできます。 FastTrack はこれまで 40,000 を超えるお客様に対応し、ROI を最大化し、展開を迅速化し、組織全体での導入を支援してきました。 「[Microsoft 365 の FastTrack](https://fasttrack.microsoft.com/microsoft365)」を参照してください。

FastTrack を利用して Microsoft 365 Enterprise を展開する場合は、基礎インフラストラクチャを展開および設定する方法のガイダンスとして FastTrack『[Microsoft 365 展開アドバイザー](https://aka.ms/microsoft365setupguide)』を使用できます。 このページにアクセスするには、Office 365 または Microsoft 365 テナントのグローバル管理者としてサインインする必要があります。

[ここ](https://fasttrack.microsoft.com/microsoft365) をクリックして、FastTrackを使ってエンド ツー エンドの展開を始めましょう。

## <a name="microsoft-365-enterprise-deployment-guide"></a>Microsoft 365 Enterprise の展開ガイド

「Microsoft 365 Enterprise の展開ガイド」は、Microsoft 365 Enterprise の製品と機能に必要な設定をするための手順を示します。

Microsoft 365 Enterprise を自分で展開するには: 

- 最初に、管理の簡素化のための組み込みセキュリティと統合に必要な[基礎インフラストラクチャ](deploy-foundation-infrastructure.md)を展開します。これにより、クライアント ソフトウェアが最新の生産性拡張機能とセキュリティ強化機能で更新されます。 
 
  基礎インフラストラクチャーは、互いに番号付けされたフェーズで編成され、Microsoft 365 Enterprise のワークロードとシナリオをサポートする環境のために作られています。 

  **小規模または新しい組織の場合**、次のフェーズにそってインフラストラクチャーを構築します。

  必要に応じて、任意の順番でインフラストラクチャーのフェーズまたはフェーズの一部を展開することができます[交互または同時](deployment-strategies-microsoft-365-enterprise.md)。現在のインフラストラクチャーと統合するには、IT プランおよびリソースが適切で、ビジネスニーズを満たさなければなりません。 非エンタープライズの簡略化された展開については、[ここ](deploy-foundation-infrastructure-non-enterprises.md) をクリックしてください。

  **企業組織の場合**、フェーズをパスではなく IT インフラストラクチャーのレイヤーとして表示し、組織全体のレイヤーに必要な条件に対して最終的に一番いい方法を決定します。

- インフラストラクチャー上に主要な生産性[ワークロードとシナリオ](deploy-workloads.md) を展開します。 これらは、組織内の独創性とチームワークを引き出します。

ここに、基礎インフラストラクチャーとワークロードとシナリオの関係性を示します。

![基礎インフラストラクチャーとワークロードとシナリオの関係性](./media/deploy-microsoft-365-enterprise/m365-deploy-content-arch.png)

ワークロードとシナリオは、基礎インフラストラクチャー上で運用します。 ただし、生産性と共同作業の向上のためにワークロードを使用するのにすべての基礎インフラストラクチャー フェーズを満たす必要はありません。

[ここ](deploy-foundation-infrastructure.md)をクリックして、エンド ツー エンドの展開を始めましょう。

## <a name="take-a-test-drive"></a>体験版の使用

“*何かを学ぶとき、実際にそれを行う事によって我々は学ぶ*” アリストテレス

初めての方は、まずご自分で操作してみるのが Microsoft 365 Enterprise や特定の製品、機能を理解する最善の方法の一つです。

テスト ラボ ガイド (TLGs) を活用すると、試用版や有料サブスクリプションを使用して、簡潔であるが代表的なテスト環境のインフラストラクチャーの設定や機能についてより簡単に学べます。

TLGs を使用すると、複雑な構成、ワークロード、またはエンド ツー エンドのシナリオの概念実証 (PoC) の自己学習、実行、カスタマイズ、または構築を行うことができます。

詳細については、「[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)」を参照してください。 

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

## <a name="transition-your-entire-organization"></a>組織全体の移行

組織全体を Microsoft 365 Enterprise の製品とサービスに移行する方法をより良く理解するためには、[組織を Microsoft 365 に移行する](media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)を参照してください。

[![組織を Microsoft 365 に移行するためのポスター](./media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)

この見開きポスター (2 ページ) で簡単に既存のインフラストラクチャのインベントリを確認して、Microsoft 365 Enterprise で対応する製品またはサービスに移行するためのガイダンスにアクセスできます。 Windows と Office の製品、その他のインフラストラクチャ、それから、デバイス管理、ID、情報および脅威保護などのセキュリティ要素が含まれます。

[移行ポスターをダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)して、レター形式、リーガル形式、またはタブロイド形式 (11 x 17) で印刷することもできます。

## <a name="how-did-others-do-it"></a>他のユーザーはどのように活用しましたか？

他のユーザーがどのように Microsoft 365 Enterprise を展開し、活用しているか知りたい場合は、これらのリソースを使います。

### <a name="how-customers-use-microsoft-365-enterprise"></a>お客様の Microsoft 365 Enterprise の活用方法

お客様導入事例のサイトを使用して、 Microsoft カスタマーによる Microsoft 365 Enterprise の使用方法をご覧ください。

1. [https://customers.microsoft.com/](https://customers.microsoft.com/) に移動して、[**検索**] をクリックします。
2. 左側のウィンドウにある [**言語**] で使用する言語を選択します。
3. [**業種**] で組織の業種を選択します。
4. [**製品**] で [**Microsoft 365**] を選択します。
5. お客様の導入事例を見るには、カードの上をクリックします。

### <a name="how-microsoft-uses-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

デジタル企業文化を定義することは、近代的な職場づくりに努めているすべてのリーダーにとって優先すべき重要課題です。　 この種の文化的なシフトをサポートするために設計された Microsoft 365 では、会社のすべての人々の力となり、自由な創造性と共同作業を育むリーダーを支援しています。 Microsoft の基本となるインフラストラクチャを確立することが、まさにこの種のデジタル文化へのシフトを引き起こしてきました。 Microsoft 365 Enterprise を実装することで、Microsoft Teams や Exchange Online のような共同作業のテクノロジを展開し、セキュリティで保護された SharePoint イントラネット サイト間でオンラインの機密データを共有できるようになりました。

同時に、高度なセキュリティ機能と製品との統合は管理のニーズを効率化し、IT ライフ サイクル全体で総保有コストを最小限に抑えるのに役立ちます。 

セキュリティで保護された環境で、創造性とチームワークの促進を解き放つサービスとアプリケーションをサポートするには、コア サービス エンジニア リングとオペレーション (旧称 Microsoft IT) [計画と基盤の展開](https://www.microsoft.com/ja-JP/itshowcase/deploying-and-managing-microsoft-365)で詳細を確認します。

> [!Note]
> この web ページは、英語でのみ利用できます。

### <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a>Contoso Corporation の Microsoft 365 Enterprise 展開方法

架空の企業、Contoso Corporation は、フランスのパリに本社を置く、代表的な世界規模の製造業の複合企業です。 [Contoso 社が Microsoft 365 Enterprise を展開](contoso-case-study.md)して、ネットワーク、ID、Windows 10 Enterprise、Office 365 ProPlus、モバイル デバイス管理、情報保護そしてセキュリティに関する主な設計上の決定と実装の詳細に、どのように対処したか参照してください。 

## <a name="stay-current-with-deployment-content"></a>展開コンテンツについての最新情報を得る

コンテンツの最新の変更内容については、[この記事](microsoft-365-deploment-guide-changes.md) を参照してください。

## <a name="next-step"></a>次の手順

Microsoft サポートをご希望の場合は、[FastTrack](https://fasttrack.microsoft.com/microsoft365)をご利用下さい。

コンサルタントをご希望の場合は、Microsoft Consulting Services または [Microsoft partner](https://partner.microsoft.com/) へご連絡ください。

自分で操作する場合は、[基礎インフラストラクチャー](deploy-foundation-infrastructure.md)を参照してください。
