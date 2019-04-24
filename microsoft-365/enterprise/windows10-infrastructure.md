---
title: Microsoft 365 enterprise の Windows 10 enterprise インフラストラクチャ
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 88517c6b8de95c54ee9a2e47d4545266eb198249
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289439"
---
# <a name="phase-3-windows-10-enterprise"></a>フェーズ 3: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 enterprise には、Windows 10 enterprise が含まれています。これにより、より多くの機能を提供し、安全な状態を維持できます。 Windows 10 Enterprise:

- **は、シンプル化のために統合されてい**ます-クラウドのパワーを活用して、今日の最新の IT デバイス環境の管理の複雑さを軽減します。サイズに関係なく使用できます。
- **インテリジェントセキュリティがあり**ます。これは、Windows の最も安全なリリースです。これは、組織の保護を強化するために連携して機能するように設計されたインテリジェントなセキュリティ機能を備えています。
- **創造性とチームワークを有効**にして、創造性とチームワークのロックを解除することで、ユーザーとユーザーの両方にとって最も生産性の高い操作性を実現できます。

Windows 10 オペレーティングシステムを展開するためのさまざまな方法を理解し、組織に適したものを選択する必要があります。 Microsoft 365 Enterprise のサブスクリプションによっては、windows 10 のサービスとセキュリティ機能も備えており、windows 10 を最大限に活用するために構成する必要があります。

Windows 10 では、Microsoft 365 Enterprise の次の戦略的なビジネスシナリオが有効になります。

- 集合知や専門知識を活用し、組織全体でファイル、情報、アイデアを発見、共有、発展させるよう人々を支援します
- 柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます
- 業界内で確証された世界標準のコンプライアンスに適合したコントロールと可視性により、安心感を提供します
- 情報を保護して、データ損失のリスクを軽減します
- 外部の脅威を検出して保護する--監視、報告、および分析を行って、組織のセキュリティを迅速に提供する
- ユーザーとそのアカウントを保護する
- 一般データ保護規則 (GDPR) に適合するように、強化されたプライバシーと法令遵守によって組織をサポートします。
- デスクトップ ソフトウェアやデバイスで最新情報を入手し、セキュリティ上のリスクの軽減と IT 効率の最大化を図ります

詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。 

>[!Note]
>Windows 10 Enterprise と Office 365 ProPlus の両方を展開し、[モダン デスクトップ](https://www.microsoft.com/microsoft-365/modern-desktop)に移行するには、「[モダン デスクトップ展開センター](http://aka.ms/howtoshift)」を参照してください。
>

## <a name="windows-10-deployment"></a>Windows 10 の展開

組織に Windows 10 Enterprise を展開する方法は複数あります。 ここでは、これらのモダン展開シナリオを使用して Windows 10 Enterprise イメージを構成および展開する方法について説明します。

| 展開シナリオ | 使用する状況 |
|:--- |:--- |
| [System Center Configuration Manager を一括アップグレードとして使用する](windows10-deploy-inplaceupgrade.md) | windows 7 または windows 8.1 コンピューターを windows 10 Enterprise の<a href="https://aka.ms/windows-10-release-information" target="_blank">現在のバージョン</a>にアップグレードする必要があり、コンピューターが現在<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (current branch)</a>で管理されている場合は、このオプションを選択します。 |
| [Windows 自動操縦の使用](windows10-deploy-autopilot.md) | windows 10 Enterprise、バージョン1703以降が事前インストールされている windows コンピューターを新たにセットアップする場合は、このオプションを選択します。 エンドユーザーは、職場または学校のアカウントの資格情報を入力することによって、目的の構成を使用してセットアップを開始します。 |

これらの展開シナリオが組織のニーズに合わない場合は、他のシナリオについて学習し、 [Windows 10 の展開シナリオ](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)での各機能と制限事項について理解することができます。 また、 <a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 の展開を</a>独自に計画することもできます。

Windows 10 の詳細については、次の記事を参照してください。

- [Microsoft 365 Enterprise 製品ページ](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Windows 10 を展開、更新する](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>その他のサービスと機能
Windows 10 Enterprise の展開の一環として、これらの追加のサービスと機能を追加することができます。

### <a name="windows-analytics"></a>Windows Analytics

windows は診断データを使用して、環境内の windows 10 デバイスの運用効率と正常性に関する詳細な洞察を得るために役立つ豊富で実用的な情報を提供します。

* アップグレードの準備状況-アップグレードの準備は、windows 10 に移行し、新しい windows 10 機能の更新プログラムを最新の状態に保つのに役立ちます。 
* コンプライアンスの更新-更新プログラムのコンプライアンスは、追加のインフラストラクチャ要件を伴わずに、すべての Windows 10 デバイスの全体的なビューを取得する IT 管理者を対象としています。
* デバイスの正常性-デバイスの正常性を使用して、問題に影響を与えるエンドユーザーを事前に検出して修復することができます。

詳細については、「 [Windows Analytics の概要](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)」を参照してください。

### <a name="windows-security"></a>Windows セキュリティ

Windows 10 では、脅威からの保護、デバイスのセキュリティ保護、およびアクセス制御のサポートに役立つ機能が提供されています。 Windows 10 では、デバイスを最初から保護する重要なセキュリティ機能を利用できます。 Microsoft 365 E3 は、windows Hello for business、windows Defender アプリケーションコントロール、および windows 情報保護などのセキュリティ機能を追加します。 microsoft 365 E5 を使用すると、microsoft 365 E3 セキュリティ、クラウドベースのセキュリティ機能、および Windows Defender Advanced Threat protection からのすべての保護を得ることができます。 

windows 10 enterprise で利用できるセキュリティ機能の詳細については、「[手順 5: windows 10 enterprise のセキュリティ機能](windows10-enable-security-features.md)を展開、管理、構成、およびトラブルシューティングする」のガイダンスを参照してください。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft の内部をピークし、Windows 10 の更新プログラムを展開し、管理する方法については、以下を参照してください。

- [Windows 10 をシームレスに展開するための組織の準備](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Microsoft では、サービスとして Windows を使用](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Microsoft における、Windows 10 のインプレース アップグレードとしての展開方法](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Windows Hello for Business を使用した、強力なユーザー認証の実装](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Windows 10 の展開: Microsoft の IT 担当者からのヒント](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (ビデオ)
- [Windows Defender ATP により高度な脅威の検出が可能](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Windows Defender および Windows Defender ATP を使用した、現代の企業のセキュリティ保護](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (ビデオ)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

架空の多国籍企業である Contoso Corporation が[Windows 10 Enterprise を展開](contoso-win10.md)した方法を参照してください。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Windows 10 Enterprise を組織で展開するための準備](windows10-prepare-your-org.md) |
