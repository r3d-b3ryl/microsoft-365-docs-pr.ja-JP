---
title: Microsoft 365 Enterprise の基礎インフラストラクチャチャ
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise の基礎インフラストラクチャを組織に展開するための主要フェーズについて理解します。
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868998"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a>Microsoft 365 Enterprise の基礎インフラストラクチャチャ

Microsoft 365 Enterprise のメリットをフルに発揮するには、その基礎インフラストラクチャから展開を開始します。 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a>Microsoft 365 Enterprise 展開の基礎インフラストラクチャ

基礎インフラストラクチャは、生産性ワークロード (Microsoft Teams や Office 365 の Exchange Online など) およびシナリオ (Microsoft 365 の移行や自動クライアント更新など) を展開できる基盤です。インテリジェント セキュリティと統合が実現し、これにより継続的な管理が簡素化され、クライアント ソフトウェアが確実に最新の生産性拡張機能およびセキュリティ機能拡張で更新されるようになります。

次のフェーズに従って、組織における Microsoft 365 Enterprise の基礎インフラストラクチャを計画し展開します。

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[フェーズ 1: ネットワーク](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[フェーズ 2: ID](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[フェーズ 3: Windows 10 Enterprise](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[フェーズ 4: Office 365 ProPlus](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[フェーズ 5: モバイル デバイス管理](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[フェーズ 6: 情報保護](infoprotect-infrastructure.md)|


各フェーズを終了する前に、フェーズの終了条件を確認する必要があります。終了条件は、満たしている必要がある必須条件と、検討すべきオプションの条件からなります。各フェーズの終了条件により、オンプレミスおよびクラウド インフラストラクチャとその結果としてのエンドツーエンド構成が、Microsoft 365 Enterprise 展開の要件を満たしていることを確認します。

この短いビデオで、基礎インフラストラクチャ コンテンツの機能を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

次の図に、Microsoft 365 Enterprise 展開全体における基礎インフラストラクチャの内容と、このインフラストラクチャの進み方を示します。

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a>FastTrack

FastTrack は、サブスクリプションの一部として利用可能であり、Microsoft エンジニアがお客様のペースに合わせたクラウドへの移行を支援する継続的かつ反復的なサービスです。FastTrack では、必要に応じて追加サービスを提供する認定パートナーにアクセスできます。FastTrack はこれまでに 40,000 以上のお客様に対応しており、ROI の最大化、展開の迅速化、組織全体での採用の拡充を支援してきました。「[Microsoft 365 の FastTrack](https://fasttrack.microsoft.com/microsoft365)」を参照してください。 

FastTrack を利用して Microsoft 365 Enterprise を展開する場合は、基礎インフラストラクチャを展開およびセットアップする方法のガイダンスとして FastTrack「[Microsoft 365 展開アドバイザー](https://aka.ms/microsoft365setupguide)」を使用できます。このページにアクセスするため、Office 365 または Microsoft 365 テナントでグローバル管理者としてサインオンする必要があります。

## <a name="next-step"></a>次の手順

Office 365、Enterprise Mobility + Security、または Windows 10 Enterprise の既存のインフラストラクチャがある場合は、「[既存のインフラストラクチャを使用した Microsoft 365 Enterprise の展開](deploy-with-existing-infrastructure.md)」を参照してください。この記事では、各フェーズの終了条件について説明しています。この情報から、IT インフラストラクチャを Microsoft 365 Enterprise 対応にするために変更する必要がある内容を容易に判別できます。

それ以外の場合は、Microsoft 365 Enterprise のエンドツーエンドの展開を[フェーズ 1: ネットワーキング](networking-infrastructure.md)から開始できます。