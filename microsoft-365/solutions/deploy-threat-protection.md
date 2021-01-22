---
title: Microsoft 365 全体にネットワーク セキュリティの脅威保護を展開する
description: Microsoft 365 E5 全体に脅威保護サービスと IT ネットワーク セキュリティ機能を展開する方法について説明します。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 79352aca2012e6615f41b19f4a77fc5cf125f4c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926752"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Microsoft 365 全体に脅威保護機能を展開する

[マルウェア](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)、およびファイルのない脅威などの高度なサイバー攻撃 [は、](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)一般的に発生します。 企業は、効果的な IT ネットワーク セキュリティ機能を使用して自分自身と顧客を保護する必要があります。 このような攻撃は、信頼の喪失から財務上の問題、ビジネスを脅かすダウンタイムなど、組織にとって大きな問題を引き起こす可能性があります。 脅威から保護することが重要ですが、組織の時間、労力、およびリソースをどこに集中する必要があるのか判断することが難しい場合があります。 

Microsoft のセキュリティ ソリューションは、Microsoft の製品とサービスに組み込されています。 オートメーションと機械学習の機能により、セキュリティ チームの負荷が軽減され、適切な項目が確実に処理されます。 また、Microsoft のネットワーク セキュリティ ソリューションの強度は、インテリジェント セキュリティ グラフで毎日処理される数兆のシグナル [を基に構築されています](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph)。 Microsoft 365 セキュリティ ソリューションには [、Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)が含まれます。Microsoft 365 Defender は、電子メール、データ、デバイス、ID を通してシグナルをまとめ、組織に対する高度な脅威の画像を描くソリューションです。


このビデオでは、展開プロセスの概要について説明します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

この記事は、脅威保護ソリューションを実装するためのガイドとして使用します。

## <a name="threat-protection-in-microsoft-365-e5"></a>Microsoft 365 E5 の脅威保護

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) を使用すると、アダプティブな組み込みインテリジェンスを使用して組織を保護できます。 Microsoft 365 E5 の脅威保護機能を使用すると、オンプレミス環境とクラウド環境全体で、高度な脅威、侵害された ID、悪意のあるアクションを検出して調査できます。

Microsoft 365 E5 では、脅威保護機能は既定で統合されています。 各機能からのシグナルは、脅威を検出して対応する全体的な機能に強度を追加します。 一連の機能を組み合わせると、Microsoft 以外の製品を実行する場合と比較して、組織、特に多国籍組織に最適な保護が提供されます。 次の画像は、この記事で説明されている Microsoft 365 E5 の脅威保護サービスと機能を示しています。

![Microsoft 365 Defender の概要](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Office 365 向け Defender の機能を展開するとすぐに、Microsoft 365 Defender を有効にし、シグナルとデータを 1 か所にまとめます。 

![Microsoft 365 Defender ダッシュボードの概念図](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

次の図は、これらの個々の機能を展開する場合の推奨パスを示しています。 

![M365 脅威保護シグナル](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|ソリューション/機能  |説明  |
|---------|---------|
|多要素認証および条件付きアクセス     |侵害された ID とデバイスから保護します。 この保護は基盤なので、まずこの保護を使います。 このガイダンスで推奨される構成には、前提条件として Azure AD Identity Protection が含まれています。     |
|Microsoft Defender for Identity     |  オンプレミスの Active Directory シグナルを利用して、高度な脅威、侵害された ID、組織に向けられた悪意のあるインサイダーアクションを特定、検出、調査するクラウドベースのセキュリティ ソリューション。 次は、Microsoft Defender for Identity に焦点を当て、オンプレムとクラウド インフラストラクチャを保護し、依存関係や前提条件を持たないので、すぐにメリットを得る可能性があります。       | 
|Microsoft Defender for Office 365     | 電子メール メッセージ、リンク (URL)、コラボレーション ツールによって生じ得る悪意のある脅威から組織を保護します。 マルウェア、フィッシング、スプーフィング、その他の攻撃の種類に対する保護。 次に、Office 365 用の Microsoft Defender の構成をお勧めします。変更制御、既存のシステムからの設定の移行など、展開に時間がかかる可能性があります。 <br><br>注: すべての Office 365 サブスクリプション (Exchange Online Protection) に含まれる脅威保護機能を構成してください。       |
|Microsoft Defender for Endpoint    | 高度な脅威の防止、検出、調査、および対応に役立つエンドポイント保護プラットフォーム。  エンドポイント用 Defender の展開には時間がかかる場合がありますが、構成は他の機能と並行して実行できます。   |
|Microsoft Cloud App Security     |   検出、調査、ガバナンスのためのクラウド アクセス セキュリティ ブローカー。 Microsoft Cloud App Security を早期に有効にして、データとインサイトの収集を開始できます。 SaaS アプリ全体に情報や他の対象を絞った保護を実装するには、計画が必要で、時間がかかる場合があります。       | 

> [!TIP]
> 複数のセキュリティ チームを持つ組織は、これらの機能を並行して実装できます。

## <a name="deploy-your-threat-protection-solution"></a>脅威保護ソリューションを展開する

組織に可能な限り最適な保護を提供するには、セキュリティ ソリューションをセットアップして展開し、次の手順を実行します。

1. [多要素認証と条件付きアクセス ポリシーを設定する](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Id 用に Microsoft Defender を構成する](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Microsoft 365 Defender を有効にする](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Defender を Office 365 用に構成する](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [エンドポイント用に Microsoft Defender を構成する](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Microsoft Cloud App Security を構成する](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [状態を監視し、アクションを実行する](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [ユーザーのトレーニング](deploy-threat-protection-configure.md#step-8-train-users)

脅威保護機能は並行して構成できます。複数のネットワーク セキュリティ チームが異なるサービスを担当している場合は、組織の保護機能を同時に構成できます。 次の図は、脅威保護機能を展開する高レベルのプロセスを示しています。 

![脅威保護機能を展開するプロセス](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
