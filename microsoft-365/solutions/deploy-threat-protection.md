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
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a><span data-ttu-id="08163-104">Microsoft 365 E5 全体に脅威保護機能を展開する</span><span class="sxs-lookup"><span data-stu-id="08163-104">Deploy threat protection capabilities across Microsoft 365 E5</span></span>

<span data-ttu-id="08163-105">[マルウェア](/windows/security/threat-protection/intelligence/understanding-malware)、ファイルレスの脅威などの高度なサイバー攻撃 [は、](/windows/security/threat-protection/intelligence/fileless-threats)一般的に発生します。</span><span class="sxs-lookup"><span data-stu-id="08163-105">[Malware](/windows/security/threat-protection/intelligence/understanding-malware), and sophisticated cyberattacks, such as [fileless threats](/windows/security/threat-protection/intelligence/fileless-threats), are a common occurrence.</span></span> <span data-ttu-id="08163-106">企業は、効果的な IT セキュリティ機能を使用して自分自身と顧客を保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08163-106">Businesses need to protect themselves and their customers with effective IT security capabilities.</span></span> <span data-ttu-id="08163-107">サイバー攻撃は、信頼の喪失から財務上の苦境、ビジネスを脅かすダウンタイムなど、組織にとって大きな問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08163-107">Cyberattacks can cause major problems for your organization, ranging from a loss of trust to financial woes, business-threatening downtime, and more.</span></span> <span data-ttu-id="08163-108">脅威からの保護は重要ですが、組織の時間、労力、リソースをどこに集中する必要があるのか判断することが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="08163-108">Protecting against threats is important, but it can be challenging to determine where to focus your organization's time, effort, and resources.</span></span> 

<span data-ttu-id="08163-109">Microsoft のセキュリティ ソリューションは、製品とサービスに組み込されています。</span><span class="sxs-lookup"><span data-stu-id="08163-109">Microsoft security solutions are built into our products and services.</span></span> <span data-ttu-id="08163-110">オートメーション機能と機械学習機能を使用すると、セキュリティ チームの負荷が軽減され、適切なアイテムが確実に対処されます。</span><span class="sxs-lookup"><span data-stu-id="08163-110">Automation and machine learning capabilities reduce the load on your security teams to make sure the right items are addressed.</span></span> <span data-ttu-id="08163-111">Microsoft セキュリティ ソリューションの強みは、インテリジェント セキュリティ グラフで毎日処理する数兆のシグナルに [基いて構築されています](/graph/security-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="08163-111">And the strength of Microsoft security solutions is built on trillions of signals we process every day in our [Intelligent Security Graph](/graph/security-concept-overview).</span></span> <span data-ttu-id="08163-112">Microsoft 365 セキュリティ ソリューションには [、Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)が含まれており、電子メール、データ、デバイス、および ID 間で信号をまとめ、組織に対する高度な脅威の画像を描画するソリューションです。</span><span class="sxs-lookup"><span data-stu-id="08163-112">Microsoft 365 security solutions include [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), a solution that brings together signals across your email, data, devices, and identities to paint a picture of advanced threats against your organization.</span></span>

<span data-ttu-id="08163-113">このビデオでは、展開プロセスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="08163-113">Watch this video for an overview of the deployment process.</span></span>
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]


## <a name="threat-protection-in-microsoft-365-e5"></a><span data-ttu-id="08163-114">Microsoft 365 E5 の脅威保護</span><span class="sxs-lookup"><span data-stu-id="08163-114">Threat protection in Microsoft 365 E5</span></span>

<span data-ttu-id="08163-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) を使用すると、アダプティブな組み込みのインテリジェンスを使用して組織を保護できます。</span><span class="sxs-lookup"><span data-stu-id="08163-115">[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) enables you to protect your organization with adaptive, built-in intelligence.</span></span> <span data-ttu-id="08163-116">Microsoft 365 E5 の脅威保護機能を使用すると、オンプレミスおよびクラウド環境全体で高度な脅威、侵害された ID、悪意のあるアクションを検出して調査できます。</span><span class="sxs-lookup"><span data-stu-id="08163-116">With the threat protection features in Microsoft 365 E5, you can detect and investigate advanced threats, compromised identities, and malicious actions across your on-premises and cloud environment.</span></span>

<span data-ttu-id="08163-117">Microsoft 365 E5 では、脅威保護機能は既定で統合されています。</span><span class="sxs-lookup"><span data-stu-id="08163-117">In Microsoft 365 E5, threat protection capabilities are integrated by default.</span></span> <span data-ttu-id="08163-118">各機能からの信号は、脅威を検出して対応する全体的な能力に強さを追加します。</span><span class="sxs-lookup"><span data-stu-id="08163-118">Signals from each capability add strength to the overall ability to detect and respond to threats.</span></span> <span data-ttu-id="08163-119">一連の機能を組み合わせると、Microsoft 以外の製品を実行する場合と比較して、組織、特に多国籍組織に最適な保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="08163-119">The combined set of capabilities offers the best protection for organizations, especially multi-national organizations, compared to running non-Microsoft products.</span></span> <span data-ttu-id="08163-120">次の図は、この記事で説明する Microsoft 365 E5 の脅威保護サービスと機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="08163-120">The following image depicts the threat protection services and capabilities in Microsoft 365 E5 that are described in this article.</span></span>

![Microsoft 365 Defender の概要](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

<span data-ttu-id="08163-122">Microsoft 365 Defender は、信号とデータを統合された [Microsoft 365](/microsoft-365/security/defender/overview-security-center)セキュリティ センターにまとめます。</span><span class="sxs-lookup"><span data-stu-id="08163-122">Microsoft 365 Defender brings the signals and data together into a [unified Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span> 

![Microsoft 365 Defender ダッシュボードの概念図](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

<span data-ttu-id="08163-124">次の図は、これらの個々の機能を展開する推奨パスを示しています。</span><span class="sxs-lookup"><span data-stu-id="08163-124">The following illustration depicts a recommended path for deploying these individual capabilities.</span></span> 

![M365 脅威保護信号](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|<span data-ttu-id="08163-126">ソリューション/機能</span><span class="sxs-lookup"><span data-stu-id="08163-126">Solution/capabilities</span></span>  |<span data-ttu-id="08163-127">説明</span><span class="sxs-lookup"><span data-stu-id="08163-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="08163-128">多要素認証と条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="08163-128">Multi-factor authentication and Conditional Access</span></span>     |<span data-ttu-id="08163-129">侵害された ID とデバイスから保護します。</span><span class="sxs-lookup"><span data-stu-id="08163-129">Protect against compromised identities and devices.</span></span> <span data-ttu-id="08163-130">この保護は基礎なので、まずこの保護から始めましょう。</span><span class="sxs-lookup"><span data-stu-id="08163-130">Begin with this protection because it's foundational.</span></span> <span data-ttu-id="08163-131">このガイダンスで推奨される構成には、前提条件として Azure AD Id Protection が含まれています。</span><span class="sxs-lookup"><span data-stu-id="08163-131">The configuration recommended in this guidance includes Azure AD Identity Protection as a prerequisite.</span></span>     |
|<span data-ttu-id="08163-132">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="08163-132">Microsoft Defender for Identity</span></span>     |  <span data-ttu-id="08163-133">オンプレミスの Active Directory ドメイン サービス (AD DS) 信号を活用して、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダーアクションを特定、検出、調査するクラウドベースのセキュリティ ソリューション。</span><span class="sxs-lookup"><span data-stu-id="08163-133">A cloud-based security solution that leverages your on-premises Active Directory Domain Services (AD DS) signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <span data-ttu-id="08163-134">オンプレミスおよびクラウド インフラストラクチャを保護し、依存関係や前提条件を持たないので、Microsoft Defender for Identity に次に集中し、すぐにセキュリティ上の利点を提供できます。</span><span class="sxs-lookup"><span data-stu-id="08163-134">Focus on Microsoft Defender for Identity next because it protects your on-premises and cloud infrastructure, has no dependencies or prerequisites, and can provide immediate security benefits.</span></span> | 
|<span data-ttu-id="08163-135">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="08163-135">Microsoft Defender for Office 365</span></span>     | <span data-ttu-id="08163-136">電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによる悪意のある脅威から組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="08163-136">Safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="08163-137">マルウェア、フィッシング、スプーフィング、その他の攻撃の種類に対する保護。</span><span class="sxs-lookup"><span data-stu-id="08163-137">Protections for malware, phishing, spoofing, and other attack types.</span></span> <span data-ttu-id="08163-138">次に、Office 365 用の Microsoft Defender の構成をお勧めします。変更制御、既存のシステムからの設定の移行など、展開に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08163-138">Configuring Microsoft Defender for Office 365 is recommended next because change control, migrating settings from incumbent system, and other considerations can take longer to deploy.</span></span> <p><span data-ttu-id="08163-139">**注**: すべての 365 サブスクリプション (Exchange Online Protection) に含まれるOffice保護機能を構成してください。</span><span class="sxs-lookup"><span data-stu-id="08163-139">**NOTE**: Make sure to configure the threat protection capabilities that are included in all Office 365 subscriptions (Exchange Online Protection).</span></span>       |
|<span data-ttu-id="08163-140">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="08163-140">Microsoft Defender for Endpoint</span></span>    | <span data-ttu-id="08163-141">高度な脅威を防止、検出、調査、および対応するのに役立つエンドポイント保護プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="08163-141">An endpoint protection platform that helps prevent, detect, investigate, and respond to advanced threats.</span></span>  <span data-ttu-id="08163-142">Defender for Endpoint の展開には時間がかかる場合がありますが、構成は他の機能と並行して実行できます。</span><span class="sxs-lookup"><span data-stu-id="08163-142">Defender for Endpoint can take some time to deploy, but configuration can be done in parallel with other capabilities.</span></span>   |
|<span data-ttu-id="08163-143">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="08163-143">Microsoft Cloud App Security</span></span>     |   <span data-ttu-id="08163-144">検出、調査、ガバナンスのためのクラウド アクセス セキュリティ ブローカー。</span><span class="sxs-lookup"><span data-stu-id="08163-144">A cloud access security broker for discovery, investigation, and governance.</span></span> <span data-ttu-id="08163-145">Microsoft Cloud App Security を早期に有効にして、データと分析情報の収集を開始できます。</span><span class="sxs-lookup"><span data-stu-id="08163-145">You can enable Microsoft Cloud App Security early to begin collecting data and insights.</span></span> <span data-ttu-id="08163-146">SaaS アプリ全体で情報や他の対象を絞った保護を実装するには、計画が必要であり、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08163-146">Implementing information and other targeted protection across your SaaS apps involves planning and can take more time.</span></span>       | 

> [!TIP]
> <span data-ttu-id="08163-147">複数のセキュリティ チームを持つ組織は、これらの機能を並行して実装できます。</span><span class="sxs-lookup"><span data-stu-id="08163-147">Organizations who have multiple security teams can implement these capabilities in parallel.</span></span> 

## <a name="deploy-your-threat-protection-solution"></a><span data-ttu-id="08163-148">脅威保護ソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="08163-148">Deploy your threat protection solution</span></span>

 <span data-ttu-id="08163-149">次の図は、脅威保護機能を展開する高レベルのプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="08163-149">The following diagram illustrates the high-level process for deploying threat protection capabilities.</span></span> 

![脅威保護機能を展開するプロセス](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

<span data-ttu-id="08163-151">組織が可能な限り最高の保護を提供するには、次の手順を含むプロセスを使用してセキュリティ ソリューションをセットアップして展開します。</span><span class="sxs-lookup"><span data-stu-id="08163-151">To make sure your organization has the best protection possible, set up and deploy your security solution with a process that includes the following steps:</span></span>

1. [<span data-ttu-id="08163-152">多要素認証と条件付きアクセス ポリシーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="08163-152">Set up multi-factor authentication and Conditional Access policies</span></span>](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [<span data-ttu-id="08163-153">Id の Microsoft Defender を構成する</span><span class="sxs-lookup"><span data-stu-id="08163-153">Configure Microsoft Defender for Identity</span></span>](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [<span data-ttu-id="08163-154">Microsoft 365 Defender を有効にする</span><span class="sxs-lookup"><span data-stu-id="08163-154">Turn on Microsoft 365 Defender</span></span>](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [<span data-ttu-id="08163-155">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="08163-155">Configure Defender for Office 365</span></span>](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [<span data-ttu-id="08163-156">エンドポイント用の Microsoft Defender の構成</span><span class="sxs-lookup"><span data-stu-id="08163-156">Configure Microsoft Defender for Endpoint</span></span>](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [<span data-ttu-id="08163-157">Microsoft Cloud App Security の構成</span><span class="sxs-lookup"><span data-stu-id="08163-157">Configure Microsoft Cloud App Security</span></span>](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [<span data-ttu-id="08163-158">状態の監視とアクションの実行</span><span class="sxs-lookup"><span data-stu-id="08163-158">Monitor status and take actions</span></span>](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [<span data-ttu-id="08163-159">ユーザーのトレーニング</span><span class="sxs-lookup"><span data-stu-id="08163-159">Train users</span></span>](deploy-threat-protection-configure.md#step-8-train-users)

<span data-ttu-id="08163-160">脅威保護機能は並行して構成できます。そのため、複数のネットワーク セキュリティ チームが異なるサービスを担当している場合は、組織の保護機能を同時に構成できます。</span><span class="sxs-lookup"><span data-stu-id="08163-160">Your threat protection features can be configured in parallel, so if you have multiple network security teams responsible for different services, they can configure your organization’s protection features at the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="08163-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="08163-161">Next step</span></span>


![脅威保護機能を展開するプロセス](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

<span data-ttu-id="08163-163">Microsoft [365 全体の脅威保護機能の構成に進む](deploy-threat-protection-configure.md)</span><span class="sxs-lookup"><span data-stu-id="08163-163">Proceed to [Configure threat protection capabilities across Microsoft 365](deploy-threat-protection-configure.md)</span></span>

