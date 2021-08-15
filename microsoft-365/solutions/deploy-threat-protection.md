---
title: 脅威保護機能を複数のユーザーに展開Microsoft 365
description: 脅威保護サービスとセキュリティ機能の概要については、Microsoft 365 E5。 ユーザー アカウント、デバイス、メール コンテンツなど、ユーザー アカウントを保護Microsoft 365 E5。
keywords: microsoft Threat Protection, Defender, setup, Advanced Threat Protection, security, microsoft 365 E5, protect devices
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: e221c720185e0d6b2d952431b2710d5711b05b39f01ba363c94e33fa41f96c61
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53897124"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>脅威保護機能を複数のユーザーに展開Microsoft 365 E5

このソリューションでは、脅威の保護が重要Microsoft 365 E5の強力な脅威保護機能について説明します。 脅威保護の概要については、Microsoft 365 E5のセットアップと構成に取り組む方法をご覧ください。

## <a name="why-threat-protection-is-important"></a>脅威の保護が重要な理由 

[マルウェア](/windows/security/threat-protection/intelligence/understanding-malware)、ファイルレスの脅威などの高度なサイバー攻撃 [は、](/windows/security/threat-protection/intelligence/fileless-threats)一般的に発生します。 企業は、効果的な IT セキュリティ機能を使用して自分自身と顧客を保護する必要があります。 サイバー攻撃は、信頼の喪失から財務上の苦境、ビジネスを脅かすダウンタイムなど、組織にとって大きな問題を引き起こす可能性があります。 脅威からの保護は重要ですが、組織の時間、労力、リソースをどこに集中する必要があるのか判断することが困難な場合があります。 Microsoft 365 E5役立ちます。 

## <a name="threat-protection-in-microsoft-365-e5"></a>脅威の保護 (Microsoft 365 E5

Microsoft のセキュリティ ソリューションは、製品とサービスに組み込されています。 オートメーション機能と機械学習機能を使用すると、セキュリティ チームの負荷が軽減され、適切なアイテムが確実に対処されます。 Microsoft セキュリティ ソリューションの強みは、インテリジェント セキュリティ ソリューションで毎日処理される数兆のシグナルに[基](/graph/security-concept-overview)Graph。 Microsoft 365には[、Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)、電子メール、データ、デバイス、および ID 間で信号をまとめ、組織に対する高度な脅威の画像を描画するソリューションが含まれます。

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab)を使用すると、アダプティブな組み込みのインテリジェンスを使用して組織を保護できます。 Microsoft 365 E5 のセキュリティ機能を使用すると、環境 (オンプレミスとクラウド) 全体で高度な脅威、侵害された ID、悪意のあるアクションを検出して調査できます。

## <a name="better-protection-with-integration"></a>統合による保護の強化

このMicrosoft 365 E5、脅威保護機能は既定で統合されています。 各機能からの信号は、脅威を検出して対応する全体的な能力に強さを追加します。 一連の機能を組み合わせると、Microsoft 以外の製品を実行する場合と比較して、組織、特に多国籍組織に最適な保護が提供されます。 次の図は、この記事で説明する脅威保護サービスと機能を示しています。

![概要 Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defenderは、信号とデータを統合されたセキュリティ センター Microsoft 365[します](/microsoft-365/security/defender/overview-security-center)。 

> [!div class="mx-imgBorder"]
> ![ダッシュボードの概念Microsoft 365 Defender図](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>展開の概要

次の図は、これらの個々の機能を展開する推奨パスを示しています。 

> [!div class="mx-imgBorder"]
> ![M365 脅威保護信号](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

このビデオでは、展開プロセスの概要について説明します。
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

次の表では、構成するさまざまなソリューション/機能と、その機能について説明します。

|手順 |ソリューション/機能  |説明  |
|--|---------|---------|
| 1 |[多要素認証と条件付きアクセス](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |侵害された ID とデバイスから保護します。 この保護は基礎なので、まずこの保護から始めましょう。 このガイダンスで推奨される構成には、前提条件として Azure AD Id Protection が含まれています。 詳細については [、「Azure AD Id Protection」を参照してください](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection)。     |
| 2 |[Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  オンプレミスの Active Directory ドメイン サービス (AD DS) 信号を使用して、組織に向けられた高度な脅威、侵害された ID、悪意のある内部者のアクションを特定、検出、および調査するクラウドベースのセキュリティ ソリューション。 オンプレミスおよびクラウド インフラストラクチャを保護し、依存関係や前提条件を持たないので、Microsoft Defender for Identity に次に集中し、すぐにセキュリティ上の利点を提供できます。 詳細については [、「What is Identity Protection? 」を参照してください](/azure/active-directory/identity-protection/overview-identity-protection)。 | 
| 3 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |信号を組み合わせ、機能を 1 つのソリューションに調整します。 セキュリティ専門家が脅威信号を一緒に縫い合わせ、脅威の全範囲と影響を特定できます。 Microsoft 365 Defender攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復する自動アクションを実行します。 詳細については、「Microsoft 365 Defender」[を参照してください](/microsoft-365/security/defender/microsoft-365-defender)。 |
| 4  |[Microsoft Defender for Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | 電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによる悪意のある脅威から組織を保護します。 マルウェア、フィッシング、スプーフィング、その他の攻撃の種類から保護します。 Microsoft Defender for Office 365構成する方法は、変更制御、現職のシステムからの設定の移行など、展開に時間がかかる可能性があるからです。 詳細については[、「Microsoft Defender for Office 365」 を参照してください](/microsoft-365/security/office-365-security/defender-for-office-365)。       |
| 5  |[Microsoft Defender for Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | デバイス間の高度な脅威 (エンドポイントとも呼ばれます) の防止、検出、調査、および対応に役立ちます。 Defender for Endpoint は、堅牢な脅威保護の提供です。 詳細については [、「Microsoft Defender for Endpoint」を参照してください](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)。  |
| 6  |[Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | 検出、調査、ガバナンスのためのクラウド アクセス セキュリティ ブローカー。 データと分析情報のMicrosoft Cloud App Securityを開始するには、早い段階でデータの収集を有効にできます。 SaaS アプリ全体で情報や他の対象を絞った保護を実装するには、計画が必要であり、時間がかかる場合があります。 詳細については、「What [is is Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> 複数のセキュリティ チームを持つ組織は、並行して機能を実装できます。 たとえば、あるチームは Defender for endpoint を構成Office 365、別のチームは Defender for Endpoint を構成できます。 構成は、提案された順序に正確に従う必要があります。 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>脅威保護ソリューションの展開を計画する

次の図は、脅威保護機能を展開する高レベルのプロセスを示しています。 

![脅威保護機能を展開するプロセス](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

組織が可能な限り最高の保護を提供[](deploy-threat-protection-configure.md)するには、次の手順を含むプロセスを使用してセキュリティ ソリューションをセットアップして展開します。

1. [多要素認証と条件付きアクセス ポリシーを設定します](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)。
2. [Id の Microsoft Defender を構成します](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)。
3. [[設定] をオンMicrosoft 365 Defender。](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [[Defender for Office 365] をOffice 365。](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [エンドポイントの Microsoft Defender を構成します](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)。
6. [構成Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)します。
7. [状態を監視し、アクションを実行します](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)。
8. [ユーザーをトレーニングします](deploy-threat-protection-configure.md#step-8-train-users)。

脅威保護機能は並行して構成できます。そのため、複数のネットワーク セキュリティ チームが異なるサービスを担当している場合は、組織の保護機能を同時に構成できます。

## <a name="next-step"></a>次の手順

[脅威保護[機能の構成] に進み](deploy-threat-protection-configure.md)、Microsoft 365。


