---
title: Microsoft 365 Enterprise の Windows 10 Enterprise インフラストラクチャ
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: d704f6392f5f0510478073299fcfe60569560105
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033642"
---
# <a name="phase-3-windows-10-enterprise"></a>フェーズ 3: Windows 10 Enterprise

![フェーズ 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise には、Windows 10 Enterprise が含まれています。これにより、より多くの機能を提供し、安全な状態を維持できます。 Windows 10 Enterprise:

- **は、シンプル化のために統合されてい**ます-クラウドのパワーを活用して、今日の最新の IT デバイス環境の管理の複雑さを軽減します。サイズに関係なく使用できます。
- **インテリジェントセキュリティがあり**ます。これは、Windows の最も安全なリリースです。これは、組織の保護を強化するために連携して機能するように設計されたインテリジェントなセキュリティ機能を備えています。
- **創造性とチームワークを有効**にして、創造性とチームワークのロックを解除することで、ユーザーとユーザーの両方にとって最も生産性の高い操作性を実現できます。

Windows 10 オペレーティングシステムを展開するためのさまざまな方法を理解し、組織に適したものを選択する必要があります。 Microsoft 365 Enterprise のサブスクリプションによっては、windows 10 のサービスとセキュリティ機能も備えており、Windows 10 を最大限に活用するために構成する必要があります。

>[!Note]
>Windows 10 Enterprise と Office 365 ProPlus の両方を展開し、[モダン デスクトップ](https://www.microsoft.com/microsoft-365/modern-desktop)に移行するには、「[モダン デスクトップ展開センター](https://aka.ms/howtoshift)」を参照してください。
>

## <a name="windows-10-deployment"></a>Windows 10 の展開

組織に Windows 10 Enterprise を展開する方法は複数あります。 ここでは、これらのモダン展開シナリオを使用して Windows 10 Enterprise イメージを構成および展開する方法について説明します。

| 展開シナリオ | 使用する状況 |
|:--- |:--- |
| [System Center Configuration Manager を一括アップグレードとして使用する](windows10-deploy-inplaceupgrade.md) | Windows 7 または Windows 8.1 コンピューターを Windows 10 Enterprise の<a href="https://aka.ms/windows-10-release-information" target="_blank">現在のバージョン</a>にアップグレードする必要があり、コンピューターが現在<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (current branch)</a>で管理されている場合は、このオプションを選択します。 |
| [Windows 自動操縦の使用](windows10-deploy-autopilot.md) | Windows 10 Enterprise、バージョン1703以降が事前インストールされている Windows コンピューターを新たにセットアップする場合は、このオプションを選択します。 エンドユーザーは、職場または学校のアカウントの資格情報を入力することによって、目的の構成を使用してセットアップを開始します。 |

これらの展開シナリオが組織のニーズに合わない場合は、他のシナリオについて学習し、 [Windows 10 の展開シナリオ](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)での各機能と制限事項について理解することができます。 自分で<a href="https://aka.ms/planforwin10deployment" target="_blank">Windows 10 の展開を計画</a>することもできます。

Windows 10 の詳細については、次の記事を参照してください。

- [Microsoft 365 Enterprise 製品ページ](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Windows 10 を展開、更新する](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>その他のサービスと機能
Windows 10 Enterprise の展開の一環として、これらの追加のサービスと機能を追加することができます。

### <a name="windows-analytics"></a>Windows Analytics

Windows は診断データを使用して、環境内の Windows 10 デバイスの運用効率と正常性に関する詳細な洞察を得るために役立つ豊富で実用的な情報を提供します。

* アップグレードの準備状況-アップグレードの準備は、Windows 10 に移行し、新しい Windows 10 機能の更新プログラムを最新の状態に保つのに役立ちます。 
* コンプライアンスの更新-更新プログラムのコンプライアンスは、追加のインフラストラクチャ要件を伴わずに、すべての Windows 10 デバイスの全体的なビューを取得する IT 管理者を対象としています。
* デバイスの正常性-デバイスの正常性を使用して、問題に影響を与えるエンドユーザーを事前に検出して修復することができます。

詳細については、「 [Windows Analytics の概要](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)」を参照してください。

### <a name="windows-security"></a>Windows セキュリティ

Windows 10 では、脅威からの保護、デバイスのセキュリティ保護、およびアクセス制御のサポートに役立つ機能が提供されています。 Windows 10 では、デバイスを最初から保護する重要なセキュリティ機能を利用できます。 Microsoft 365 E3 は、Windows Hello for Business、Windows Defender アプリケーションコントロール、および Windows 情報保護などのセキュリティ機能を追加します。 Microsoft 365 E5 を使用すると、Microsoft 365 E3 セキュリティとクラウドベースのセキュリティ機能および Microsoft Defender Advanced Threat Protection からすべての保護を取得できます。 

Windows 10 Enterprise で利用できるセキュリティ機能の詳細については、「[手順 5: windows 10 enterprise のセキュリティ機能](windows10-enable-security-features.md)を展開、管理、構成、およびトラブルシューティングする」のガイダンスを参照してください。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft の内部を見ることで、会社が[Windows 10 Enterprise を展開し、強力な認証、Intune、Microsoft DEFENDER ATP を使用して](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6)いる方法について説明します。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

架空の多国籍企業である Contoso Corporation が[Windows 10 Enterprise を展開](contoso-win10.md)した方法を参照してください。

![Contoso 社](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 1](./media/stepnumbers/Step1.png)| [Windows 10 Enterprise を組織で展開するための準備](windows10-prepare-your-org.md) |
