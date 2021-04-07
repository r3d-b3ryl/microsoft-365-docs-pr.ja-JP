---
title: Microsoft 365 全体に脅威保護機能を展開する
description: Microsoft 365 E5 の脅威保護サービスとセキュリティの概要を確認します。
keywords: 脅威保護、セキュリティ、E5、サイバー攻撃、マルウェア、M365、ソリューション
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 922e7b7ea8bceced7085af49485b3479a671d5cd
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599961"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Microsoft 365 E5 全体に脅威保護機能を展開する

[マルウェア](/windows/security/threat-protection/intelligence/understanding-malware)、ファイルレスの脅威などの高度なサイバー攻撃 [は、](/windows/security/threat-protection/intelligence/fileless-threats)一般的に発生します。 企業は、効果的な IT セキュリティ機能を使用して自分自身と顧客を保護する必要があります。 サイバー攻撃は、信頼の喪失から財務上の苦境、ビジネスを脅かすダウンタイムなど、組織にとって大きな問題を引き起こす可能性があります。 脅威からの保護は重要ですが、組織の時間、労力、リソースをどこに集中する必要があるのか判断することが困難な場合があります。 

Microsoft のセキュリティ ソリューションは、製品とサービスに組み込されています。 オートメーション機能と機械学習機能を使用すると、セキュリティ チームの負荷が軽減され、適切なアイテムが確実に対処されます。 Microsoft セキュリティ ソリューションの強みは、インテリジェント セキュリティ グラフで毎日処理する数兆のシグナルに [基いて構築されています](/graph/security-concept-overview)。 Microsoft 365 セキュリティ ソリューションには [、Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)が含まれており、電子メール、データ、デバイス、および ID 間で信号をまとめ、組織に対する高度な脅威の画像を描画するソリューションです。

このビデオでは、展開プロセスの概要について説明します。
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]


## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5 の脅威保護

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) を使用すると、アダプティブな組み込みのインテリジェンスを使用して組織を保護できます。 Microsoft 365 E5 の脅威保護機能を使用すると、オンプレミスおよびクラウド環境全体で高度な脅威、侵害された ID、悪意のあるアクションを検出して調査できます。

Microsoft 365 E5 では、脅威保護機能は既定で統合されています。 各機能からの信号は、脅威を検出して対応する全体的な能力に強さを追加します。 一連の機能を組み合わせると、Microsoft 以外の製品を実行する場合と比較して、組織、特に多国籍組織に最適な保護が提供されます。 次の図は、この記事で説明する Microsoft 365 E5 の脅威保護サービスと機能を示しています。

![Microsoft 365 Defender の概要](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender は、信号とデータを統合された [Microsoft 365](/microsoft-365/security/defender/overview-security-center)セキュリティ センターにまとめます。 

![Microsoft 365 Defender ダッシュボードの概念図](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

次の図は、これらの個々の機能を展開する推奨パスを示しています。 

![M365 脅威保護信号](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|ソリューション/機能  |説明  |
|---------|---------|
|多要素認証と条件付きアクセス     |侵害された ID とデバイスから保護します。 この保護は基礎なので、まずこの保護から始めましょう。 このガイダンスで推奨される構成には、前提条件として Azure AD Id Protection が含まれています。     |
|Microsoft Defender for Identity     |  オンプレミスの Active Directory ドメイン サービス (AD DS) 信号を活用して、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダーアクションを特定、検出、調査するクラウドベースのセキュリティ ソリューション。 オンプレミスおよびクラウド インフラストラクチャを保護し、依存関係や前提条件を持たないので、Microsoft Defender for Identity に次に集中し、すぐにセキュリティ上の利点を提供できます。 | 
|Microsoft Defender for Office 365     | 電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによる悪意のある脅威から組織を保護します。 マルウェア、フィッシング、スプーフィング、その他の攻撃の種類に対する保護。 次に、Office 365 用の Microsoft Defender の構成をお勧めします。変更制御、既存のシステムからの設定の移行など、展開に時間がかかる場合があります。 <p>**注**: すべての 365 サブスクリプション (Exchange Online Protection) に含まれるOffice保護機能を構成してください。       |
|Microsoft Defender for Endpoint    | 高度な脅威を防止、検出、調査、および対応するのに役立つエンドポイント保護プラットフォーム。  Defender for Endpoint の展開には時間がかかる場合がありますが、構成は他の機能と並行して実行できます。   |
|Microsoft Cloud App Security     |   検出、調査、ガバナンスのためのクラウド アクセス セキュリティ ブローカー。 Microsoft Cloud App Security を早期に有効にして、データと分析情報の収集を開始できます。 SaaS アプリ全体で情報や他の対象を絞った保護を実装するには、計画が必要であり、時間がかかる場合があります。       | 

> [!TIP]
> 複数のセキュリティ チームを持つ組織は、これらの機能を並行して実装できます。 

## <a name="deploy-your-threat-protection-solution"></a>脅威保護ソリューションの展開

 次の図は、脅威保護機能を展開する高レベルのプロセスを示しています。 

![脅威保護機能を展開するプロセス](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

組織が可能な限り最高の保護を提供するには、次の手順を含むプロセスを使用してセキュリティ ソリューションをセットアップして展開します。

1. [多要素認証と条件付きアクセス ポリシーのセットアップ](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Id の Microsoft Defender を構成する](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Microsoft 365 Defender を有効にする](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Defender for Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [エンドポイント用の Microsoft Defender の構成](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Microsoft Cloud App Security の構成](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [状態の監視とアクションの実行](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [ユーザーのトレーニング](deploy-threat-protection-configure.md#step-8-train-users)

脅威保護機能は並行して構成できます。そのため、複数のネットワーク セキュリティ チームが異なるサービスを担当している場合は、組織の保護機能を同時に構成できます。

## <a name="next-step"></a>次の手順


![脅威保護機能を展開するプロセス](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Microsoft [365 全体の脅威保護機能の構成に進む](deploy-threat-protection-configure.md)

