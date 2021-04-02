---
title: Microsoft Defender for Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender for Office 365 には、安全な添付ファイル、安全なリンク、高度なフィッシング詐欺対策ツール、レポート ツール、および脅威インテリジェンス機能が含まれています。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec60fc7063bdd4a2656385ed86098d6ae2b4abc0
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205955"
---
# <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="73e6e-103">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="73e6e-103">Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="73e6e-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="73e6e-104">**Applies to**</span></span>
- [<span data-ttu-id="73e6e-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="73e6e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="73e6e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73e6e-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="73e6e-107">この記事は、[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="73e6e-107">This article is intended for business customers who have [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="73e6e-108">Outlook.com、Microsoft 365 Family、または Microsoft 365 Personal を使用していて、Outlook の安全なリンクまたは添付ファイルに関する情報を探している場合は、「[Microsoft 365 サブスクライバー用の Outlook.com の高度なセキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-108">If you are using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safe Links or Safe Attachments in Outlook, see [Advanced Outlook.com security for Microsoft 365 subscribers](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="73e6e-109">Microsoft Defender for Office 365 は、電子メール メッセージ、リンク (URL) や共同作業ツールによって生じる悪意のある脅威から組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-109">Microsoft Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="73e6e-110">Defender for Office 365 には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-110">Defender for Office 365 includes:</span></span>

- <span data-ttu-id="73e6e-111">**[脅威保護ポリシー](#configure-microsoft-defender-for-office-365-policies)**: 脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-111">**[Threat protection policies](#configure-microsoft-defender-for-office-365-policies)**: Define threat-protection policies to set the appropriate level of protection for your organization.</span></span>

- <span data-ttu-id="73e6e-112">**[レポート](#view-microsoft-defender-for-office-365-reports)**: 組織の Defender for Office 365 パフォーマンスを監視するリアルタイム レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-112">**[Reports](#view-microsoft-defender-for-office-365-reports)**: View real-time reports to monitor Defender for Office 365  performance in your organization.</span></span>

- <span data-ttu-id="73e6e-113">**[脅威の調査および反応機能](#use-threat-investigation-and-response-capabilities)**: 最先端のツールを使用して、脅威の調査、把握、シミュレーション、および回避を行います。</span><span class="sxs-lookup"><span data-stu-id="73e6e-113">**[Threat investigation and response capabilities](#use-threat-investigation-and-response-capabilities)**: Use leading-edge tools to investigate, understand, simulate, and prevent threats.</span></span>

- <span data-ttu-id="73e6e-114">**[自動調査および対応機能](office-365-air.md)**: 脅威の調査および軽減にかかる時間と労力を節約します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-114">**[Automated investigation and response capabilities](office-365-air.md)**: Save time and effort investigating and mitigating threats.</span></span>

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a><span data-ttu-id="73e6e-115">Microsoft Defender for Office 365 の対話型のガイド</span><span class="sxs-lookup"><span data-stu-id="73e6e-115">Interactive guide to Microsoft Defender for Office 365</span></span>
<span data-ttu-id="73e6e-116">この対話型のガイドでは、Microsoft Defender for Office 365 を使用して組織を保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-116">In this interactive guide you'll learn how to safeguard your organization with Microsoft Defender for Office 365.</span></span> <span data-ttu-id="73e6e-117">Defender for Office 365 が、保護ポリシーの定義、組織への脅威の分析、攻撃への対応にどのように役立つかをご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-117">You'll see how Defender for Office 365 can help you define protection policies, analyze threats to your organization, and respond to attacks.</span></span>

> [!VIDEO https://aka.ms/MSDO-IG]

## <a name="getting-started"></a><span data-ttu-id="73e6e-118">はじめに</span><span class="sxs-lookup"><span data-stu-id="73e6e-118">Getting Started</span></span>

<span data-ttu-id="73e6e-119">Microsoft Defender for Office 365 を初めて使用している場合、または *実行しながら* 最適な方法を学ぶ場合は、この記事を参照しながら、初期 Defender for Office 365 構成をチャンクに分割し、調査し、レポートを表示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73e6e-119">If you're new to Microsoft Defender for Office 365 or learn best by *doing*, you may benefit from breaking initial Defender for Office 365 configuration into chunks, investigating, and viewing reports using this article as a reference.</span></span> <span data-ttu-id="73e6e-120">論理的な初期構成チャンクは次の通りです。</span><span class="sxs-lookup"><span data-stu-id="73e6e-120">Here are logical early configuration chunks:</span></span>

- <span data-ttu-id="73e6e-121">名前に "*対策*" を使用してすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-121">Configure everything with '*anti*' in the name.</span></span>
  - <span data-ttu-id="73e6e-122">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="73e6e-122">anti-malware</span></span>
  - <span data-ttu-id="73e6e-123">フィッシング詐欺対策</span><span class="sxs-lookup"><span data-stu-id="73e6e-123">anti-phishing</span></span>
  - <span data-ttu-id="73e6e-124">スパム対策</span><span class="sxs-lookup"><span data-stu-id="73e6e-124">anti-spam</span></span>
- <span data-ttu-id="73e6e-125">名前に "*安全*" を使用してすべてを設定します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-125">Set up everything with '*safe*' in the name.</span></span>
  - <span data-ttu-id="73e6e-126">安全なリンク</span><span class="sxs-lookup"><span data-stu-id="73e6e-126">safe links</span></span>
  - <span data-ttu-id="73e6e-127">安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="73e6e-127">safe attachments</span></span>
- <span data-ttu-id="73e6e-128">ワークロードを保護する (例:</span><span class="sxs-lookup"><span data-stu-id="73e6e-128">Defend the workloads (ex.</span></span> <span data-ttu-id="73e6e-129">OSharePoint Online、OneDrive と Teams)</span><span class="sxs-lookup"><span data-stu-id="73e6e-129">SharePoint Online, OneDrive, and Teams)</span></span>
- <span data-ttu-id="73e6e-130">ゼロアワー自動消去を使用して保護する</span><span class="sxs-lookup"><span data-stu-id="73e6e-130">Protect with Zero-Hour auto purge</span></span>

<span data-ttu-id="73e6e-131">詳細については、 [このリンクをクリック](protect-against-threats.md)してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-131">To learn by doing, [click this link](protect-against-threats.md).</span></span>

> [!NOTE]
> <span data-ttu-id="73e6e-132">Microsoft Defender for Office 365 には、2 種類のプランがあります。</span><span class="sxs-lookup"><span data-stu-id="73e6e-132">Microsoft Defender for Office 365 comes in two different Plan types.</span></span> <span data-ttu-id="73e6e-133">"リアルタイム検出" を使用している場合は **プラン 1** で、脅威エクスプローラーを使用している場合は **プラン 2** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-133">You can tell if you have **Plan 1** if you have 'Real-time Detections', and **Plan 2**, if you have Threat Explorer.</span></span> <span data-ttu-id="73e6e-134">このプランは、表示されるツールに影響しますので、お客様のプランについて理解していることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-134">The Plan you have influences the tools you will see, so be certain that you're aware of your Plan as you learn.</span></span>

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a><span data-ttu-id="73e6e-135">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="73e6e-135">Microsoft Defender for Office 365 Plan 1 and Plan 2</span></span>

<span data-ttu-id="73e6e-136">次の表は、各プランに含まれる機能をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="73e6e-136">The following table summarizes what's included in each plan.</span></span>

****

|<span data-ttu-id="73e6e-137">Microsoft Defender for Office 365 プラン 1</span><span class="sxs-lookup"><span data-stu-id="73e6e-137">Microsoft Defender for Office 365 Plan 1</span></span>|<span data-ttu-id="73e6e-138">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="73e6e-138">Microsoft Defender for Office 365 Plan 2</span></span>|
|---|---|
|<span data-ttu-id="73e6e-139">構成、保護、および検出機能:</span><span class="sxs-lookup"><span data-stu-id="73e6e-139">Configuration, protection, and detection capabilities:</span></span> <ul><li>[<span data-ttu-id="73e6e-140">添付ファイル保護</span><span class="sxs-lookup"><span data-stu-id="73e6e-140">Safe Attachments</span></span>](safe-attachments.md)</li><li>[<span data-ttu-id="73e6e-141">リンク保護</span><span class="sxs-lookup"><span data-stu-id="73e6e-141">Safe Links</span></span>](safe-links.md)</li><li>[<span data-ttu-id="73e6e-142">SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="73e6e-142">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)</li><li>[<span data-ttu-id="73e6e-143">Defender for Office 365 保護のフィッシング詐欺対策</span><span class="sxs-lookup"><span data-stu-id="73e6e-143">Anti-phishing in Defender for Office 365 protection</span></span>](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[<span data-ttu-id="73e6e-144">リアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="73e6e-144">Real-time detections</span></span>](threat-explorer.md)</li></ul>|<span data-ttu-id="73e6e-145">Microsoft Defender for Office 365 プラン 1 機能</span><span class="sxs-lookup"><span data-stu-id="73e6e-145">Microsoft Defender for Office 365 Plan 1 capabilities</span></span> <br><span data-ttu-id="73e6e-146">--- プラスのもの ---</span><span class="sxs-lookup"><span data-stu-id="73e6e-146">--- plus ---</span></span><br> <span data-ttu-id="73e6e-147">自動化、調査、修復、教育の機能:</span><span class="sxs-lookup"><span data-stu-id="73e6e-147">Automation, investigation, remediation, and education capabilities:</span></span><ul><li>[<span data-ttu-id="73e6e-148">脅威トラッカー</span><span class="sxs-lookup"><span data-stu-id="73e6e-148">Threat Trackers</span></span>](threat-trackers.md)</li><li>[<span data-ttu-id="73e6e-149">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="73e6e-149">Threat Explorer</span></span>](threat-explorer.md)</li><li>[<span data-ttu-id="73e6e-150">自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="73e6e-150">Automated investigation and response</span></span>](office-365-air.md)</li><li>[<span data-ttu-id="73e6e-151">攻撃シミュレータ</span><span class="sxs-lookup"><span data-stu-id="73e6e-151">Attack Simulator</span></span>](attack-simulator.md)</li><li>[<span data-ttu-id="73e6e-152">キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="73e6e-152">Campaign Views</span></span>](campaigns.md)</li></ul>|
|

- <span data-ttu-id="73e6e-153">Microsoft Defender for Office 365 プラン 2 は、Office 365 E5、Office 365 A5、および Microsoft 365 E5 Security と Microsoft 365 E5 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="73e6e-153">Microsoft Defender for Office 365 Plan 2 is included in Office 365 E5, Office 365 A5, Microsoft 365 E5 Security, and Microsoft 365 E5.</span></span>

- <span data-ttu-id="73e6e-154">Microsoft Defender for Office 365 プラン 1 は、Microsoft 365 Business Premium に含まれています。</span><span class="sxs-lookup"><span data-stu-id="73e6e-154">Microsoft Defender for Office 365 Plan 1 is included in Microsoft 365 Business Premium.</span></span>

- <span data-ttu-id="73e6e-155">Microsoft Defender for Office 365 プラン 1 および Microsoft Defender for Office 365 プラン 2 は、それぞれ特定のサブスクリプションのアドオンとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-155">Microsoft Defender for Office 365 Plan 1 and Microsoft Defender for Office 365 Plan 2 are each available as an add-on for certain subscriptions.</span></span> <span data-ttu-id="73e6e-156">詳細については、「[Microsoft Defender for Office 365 プラン全体での機能の可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-156">To learn more, see [Feature availability across Microsoft Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

- <span data-ttu-id="73e6e-157">[安全なドキュメント](safe-docs.md)機能は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンス (Microsoft Defender for Office 365 プランには含まれません) を持つユーザーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-157">The [Safe Documents](safe-docs.md) feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security licenses (not included in Microsoft Defender for Office 365 plans).</span></span>

- <span data-ttu-id="73e6e-158">現在のサブスクリプションに Microsoft Defender for Office 365 が含まれていない場合は、[販売員に連絡して試用版を開始](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)し、Defender for Office 365 が組織でどのように機能するかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-158">If your current subscription does not include Microsoft Defender for Office 365, [contact sales to start a trial](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html), and see how Defender for Office 365 can work for your organization.</span></span>

## <a name="configure-microsoft-defender-for-office-365-policies"></a><span data-ttu-id="73e6e-159">Microsoft Defender for Office 365 のポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="73e6e-159">Configure Microsoft Defender for Office 365 policies</span></span>

<span data-ttu-id="73e6e-160">Microsoft Defender for Office 365 を使用して、組織のセキュリティ チームは、セキュリティ/コンプライアンス センターでポリシーを定義することにより、保護を構成できます ([<https://protection.office.com> \> **脅威管理** \> **ポリシー**] に移動します)。</span><span class="sxs-lookup"><span data-stu-id="73e6e-160">With Microsoft Defender for Office 365, your organization's security team can configure protection by defining policies in the Security & Compliance Center (Go to <https://protection.office.com> \> **Threat management** \> **Policy**.)</span></span>

> [!TIP]
> <span data-ttu-id="73e6e-161">定義するポリシーの簡便なリストについては、「[脅威から保護する](protect-against-threats.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-161">For a quick list of policies to define, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="defender-for-office-365-policies"></a><span data-ttu-id="73e6e-162">Defender for Office 365 ポリシー</span><span class="sxs-lookup"><span data-stu-id="73e6e-162">Defender for Office 365 Policies</span></span>

<span data-ttu-id="73e6e-163">組織で定義されているポリシーにより、定義済み脅威に対する動作と保護レベルが決まります。</span><span class="sxs-lookup"><span data-stu-id="73e6e-163">The policies that are defined for your organization determine the behavior and protection level for predefined threats.</span></span> <span data-ttu-id="73e6e-164">ポリシー オプションは、非常に柔軟です。</span><span class="sxs-lookup"><span data-stu-id="73e6e-164">Policy options are extremely flexible.</span></span> <span data-ttu-id="73e6e-165">たとえば、組織のセキュリティ チームは、ユーザー、組織、受信者、ドメイン レベルで詳細に脅威保護を設定できます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-165">For example, your organization's security team can set fine-grained threat protection at the user, organization, recipient, and domain level.</span></span> <span data-ttu-id="73e6e-166">新しい脅威や課題が毎日出現するため、ポリシーを定期的に確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="73e6e-166">It is important to review your policies regularly because new threats and challenges emerge daily.</span></span>

- <span data-ttu-id="73e6e-167">**[安全な添付ファイル機能](safe-attachments.md)**: 悪意のあるコンテンツがないかどうかメールの添付ファイルを確認して、メッセージング システムを保護できるゼロデイ保護機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-167">**[Safe Attachments](safe-attachments.md)**: Provides zero-day protection to safeguard your messaging system, by checking email attachments for malicious content.</span></span> <span data-ttu-id="73e6e-168">ウイルス/マルウェアの署名を持たないすべてのメッセージと添付ファイルを特別な環境にルートし、機械学習と分析技術を使用して悪意を検出します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-168">It routes all messages and attachments that do not have a virus/malware signature to a special environment, and then uses machine learning and analysis techniques to detect malicious intent.</span></span> <span data-ttu-id="73e6e-169">疑わしいアクティビティが見つからない場合、メッセージはメールボックスに転送されます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-169">If no suspicious activity is found, the message is forwarded to the mailbox.</span></span> <span data-ttu-id="73e6e-170">詳細については、「[安全な添付ファイル ポリシーを設定する](set-up-safe-attachments-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-170">To learn more, see [Set up Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

- <span data-ttu-id="73e6e-171">**[安全なリンク](safe-links.md)**: メール メッセージや Office ファイルなどで、URL をクリックした時に検証を行います。</span><span class="sxs-lookup"><span data-stu-id="73e6e-171">**[Safe Links](safe-links.md)**: Provides time-of-click verification of URLs, for example, in emails messages and Office files.</span></span> <span data-ttu-id="73e6e-172">保護は継続的に行われ、メッセージおよび Office 環境全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-172">Protection is ongoing and applies across your messaging and Office environment.</span></span> <span data-ttu-id="73e6e-173">クリックごとにリンクがスキャンされます。安全なリンクは常にアクセスでき、悪意のあるリンクは動的にブロックされます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-173">Links are scanned for each click: safe links remain accessible and malicious links are dynamically blocked.</span></span> <span data-ttu-id="73e6e-174">詳細については、「[安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-174">To learn more, see [Set up Safe Links policies](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="73e6e-175">**[SharePoint、OneDrive、Microsoft Teams 用の 安全な添付ファイル](mdo-for-spo-odb-and-teams.md)**: チーム サイトやドキュメント ライブラリ内で悪意のあるファイルを特定してブロックすることで、ユーザーが共同作業でファイルを共有する際に組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-175">**[Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md)**: Protects your organization when users collaborate and share files, by identifying and blocking malicious files in team sites and document libraries.</span></span> <span data-ttu-id="73e6e-176">詳細については、「[SharePoint、OneDrive、Microsoft の Defender for Office 365 を有効にする](turn-on-mdo-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-176">To learn more, see [Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

- <span data-ttu-id="73e6e-177">**[Defender for Office 365 のフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: ユーザー、内部およびカスタム ドメインの偽装を検出します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-177">**[Anti-phishing protection in Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: Detects attempts to impersonate your users and internal or custom domains.</span></span> <span data-ttu-id="73e6e-178">この機能は、コンピューターの学習モデルや高度な偽装検出アルゴリズムを適用してフィッシング攻撃に回避します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-178">It applies machine learning models and advanced impersonation-detection algorithms to avert phishing attacks.</span></span> <span data-ttu-id="73e6e-179">詳細については、「[Microsoft Defender for Office 365 のフィッシング詐欺対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-179">To learn more, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="view-microsoft-defender-for-office-365-reports"></a><span data-ttu-id="73e6e-180">Microsoft Defender for Office 365 レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="73e6e-180">View Microsoft Defender for Office 365 reports</span></span>

<span data-ttu-id="73e6e-181">Microsoft Defender for Office 365 には、Defender for Office 365 のパフォーマンスを監視するための高度な[レポート ダッシュボード](view-reports-for-mdo.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="73e6e-181">Microsoft Defender for Office 365 includes an advanced [reporting dashboard](view-reports-for-mdo.md) to monitor your Defender for Office 365  performance.</span></span> <span data-ttu-id="73e6e-182">セキュリティ/コンプライアンス センターの [**レポート**] \> [**ダッシュ ボード**] でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-182">You can access it at **Reports** \> **Dashboard** in the Security & Compliance Center.</span></span>

<span data-ttu-id="73e6e-183">レポートはリアルタイムで更新され、最新の分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-183">Reports update in real-time, providing you with the latest insights.</span></span> <span data-ttu-id="73e6e-184">また、これらのレポートは推奨事項を提供し、間近に迫った脅威を警告します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-184">These reports also provide recommendations and alert you to imminent threats.</span></span> <span data-ttu-id="73e6e-185">定義済みレポートには次のものが含まれます:</span><span class="sxs-lookup"><span data-stu-id="73e6e-185">Predefined reports include the following:</span></span>

- [<span data-ttu-id="73e6e-186">脅威エクスプローラー (またはリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="73e6e-186">Threat Explorer (or real-time detections)</span></span>](threat-explorer.md)

- [<span data-ttu-id="73e6e-187">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="73e6e-187">Threat protection status report</span></span>](view-reports-for-mdo.md#threat-protection-status-report)

- [<span data-ttu-id="73e6e-188">Defender for Office 365 のファイル型レポート</span><span class="sxs-lookup"><span data-stu-id="73e6e-188">Defender for Office 365 file types report</span></span>](view-reports-for-mdo.md#defender-for-office-365-file-types-report)

- [<span data-ttu-id="73e6e-189">Defender for Office 365 のメッセージ処理レポート</span><span class="sxs-lookup"><span data-stu-id="73e6e-189">Defender for Office 365 message disposition report</span></span>](view-reports-for-mdo.md#defender-for-office-365-message-disposition-report)

- <span data-ttu-id="73e6e-190">レポートは、上記のもの以外にもいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="73e6e-190">... and several more.</span></span>

## <a name="use-threat-investigation-and-response-capabilities"></a><span data-ttu-id="73e6e-191">脅威の調査および対応機能を使用する</span><span class="sxs-lookup"><span data-stu-id="73e6e-191">Use threat investigation and response capabilities</span></span>

<span data-ttu-id="73e6e-192">Microsoft Defender for Office 365 プラン 2 には、組織のセキュリティ チームが悪意のある攻撃を予測、把握、および回避するために、クラス最高の[脅威の調査および対応のツール](office-365-ti.md)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-192">Microsoft Defender for Office 365 Plan 2 includes best-of-class [threat investigation and response tools](office-365-ti.md) that enable your organization's security team to anticipate, understand, and prevent malicious attacks.</span></span>

- <span data-ttu-id="73e6e-193">**[脅威トラッカー](threat-trackers.md)** は、一般的なサイバーセキュリティの問題に関する最新のインテリジェンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-193">**[Threat trackers](threat-trackers.md)** provide the latest intelligence on prevailing cybersecurity issues.</span></span> <span data-ttu-id="73e6e-194">たとえば、最新のマルウェアに関する情報を表示し、組織に対する実際の脅威になる前に対策を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-194">For example, you can view information about the latest malware, and take countermeasures before it becomes an actual threat to your organization.</span></span> <span data-ttu-id="73e6e-195">使用可能な脅威トラッカーには、[[注目のトラッカー](threat-trackers.md#noteworthy-trackers)]、[[急上昇中のトラッカー](threat-trackers.md#trending-trackers)]、[[追跡されたクエリ](threat-trackers.md#tracked-queries)]、[[保存されたクエリ](threat-trackers.md#saved-queries)] があります。</span><span class="sxs-lookup"><span data-stu-id="73e6e-195">Available trackers include [Noteworthy trackers](threat-trackers.md#noteworthy-trackers), [Trending trackers](threat-trackers.md#trending-trackers), [Tracked queries](threat-trackers.md#tracked-queries), and [Saved queries](threat-trackers.md#saved-queries).</span></span>

- <span data-ttu-id="73e6e-196">**[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)** (エクスプローラーとも呼ばれます) は、最近発生した脅威を特定して分析できるリアルタイムのレポートです。</span><span class="sxs-lookup"><span data-stu-id="73e6e-196">**[Threat Explorer (or real-time detections)](threat-explorer.md)** (also referred to as Explorer) is a real-time report that allows you to identify and analyze recent threats.</span></span> <span data-ttu-id="73e6e-197">カスタム期間のデータを表示するようにエクスプローラーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-197">You can configure Explorer to show data for custom periods.</span></span>

- <span data-ttu-id="73e6e-198">**[攻撃シミュレータ](attack-simulator.md)** を使用すると、現実的な攻撃シナリオを組織で実行して、脆弱性を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-198">**[Attack Simulator](attack-simulator.md)** allows you to run realistic attack scenarios in your organization to identify vulnerabilities.</span></span> <span data-ttu-id="73e6e-199">スピア フィッシング資格情報獲得と添付ファイルの攻撃、パスワード スプレーとブルート フォース パスワード攻撃など、現在の種類の攻撃のシミュレーションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-199">Simulations of current types of attacks are available, including spear phishing credential harvest and attachment attacks, and password spray and brute force password attacks.</span></span>

## <a name="save-time-with-automated-investigation-and-response"></a><span data-ttu-id="73e6e-200">自動化された調査と対応で時間を節約する</span><span class="sxs-lookup"><span data-stu-id="73e6e-200">Save time with automated investigation and response</span></span>

<span data-ttu-id="73e6e-201">(**新機能!**) 潜在的なサイバー攻撃を調査している場合は、期限厳守です。</span><span class="sxs-lookup"><span data-stu-id="73e6e-201">(**NEW!**) When you are investigating a potential cyberattack, time is of the essence.</span></span> <span data-ttu-id="73e6e-202">脅威をより早く特定して軽減できれば、組織はより良くなります。</span><span class="sxs-lookup"><span data-stu-id="73e6e-202">The sooner you can identify and mitigate threats, the better off your organization will be.</span></span> <span data-ttu-id="73e6e-203">[自動調査および対応](office-365-air.md) (AIR) 機能には、アラートがトリガーされたときなどには自動的に、またはエクスプローラーのビューから手動で起動できるセキュリティ プレイブックのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="73e6e-203">[Automated investigation and response](office-365-air.md) (AIR) capabilities include a set of security playbooks that can be launched automatically, such as when an alert is triggered, or manually, such as from a view in Explorer.</span></span> <span data-ttu-id="73e6e-204">AIR は、セキュリティ運用チームの脅威を軽減するための時間と労力を効果的かつ効率的に節約できます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-204">AIR can save your security operations team time and effort in mitigating threats effectively and efficiently.</span></span> <span data-ttu-id="73e6e-205">詳細については、「[Office 365 での AIR](office-365-air.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-205">To learn more, see [AIR in Office 365](office-365-air.md).</span></span>

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a><span data-ttu-id="73e6e-206">Microsoft Defender for Office 365 の機能を使用するために必要な権限</span><span class="sxs-lookup"><span data-stu-id="73e6e-206">Permissions required to use Microsoft Defender for Office 365 features</span></span>

<span data-ttu-id="73e6e-207">セキュリティ/コンプライアンス センターで Microsoft Defender for Office 365 機能にアクセスするには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73e6e-207">To access Microsoft Defender for Office 365 features in the Security & Compliance Center, you must be assigned an appropriate role.</span></span> <span data-ttu-id="73e6e-208">次の表にいくつかの例があります:</span><span class="sxs-lookup"><span data-stu-id="73e6e-208">The following table includes some examples:</span></span>

|<span data-ttu-id="73e6e-209">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="73e6e-209">Role or role group</span></span>|<span data-ttu-id="73e6e-210">追加情報</span><span class="sxs-lookup"><span data-stu-id="73e6e-210">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="73e6e-211">グローバル管理者 (Azure Active Directory またはセキュリティ/コンプライアンス センターで割り当てることができます)</span><span class="sxs-lookup"><span data-stu-id="73e6e-211">global administrator (this can be assigned in either Azure Active Directory or in the Security & Compliance Center)</span></span>|[<span data-ttu-id="73e6e-212">Microsoft 365 管理者ロールについて</span><span class="sxs-lookup"><span data-stu-id="73e6e-212">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="73e6e-213">セキュリティ管理者 (Azure Active Directory またはセキュリティ/コンプライアンス センターで割り当てることができます)</span><span class="sxs-lookup"><span data-stu-id="73e6e-213">Security Administrator (this can be assigned in either Azure Active Directory or the Security & Compliance Center)</span></span>|[<span data-ttu-id="73e6e-214">Azure Active Directory での管理者役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="73e6e-214">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [<span data-ttu-id="73e6e-215">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="73e6e-215">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)|
|<span data-ttu-id="73e6e-216">Exchange Online 組織管理 (Exchange Online で割り当てることができます)</span><span class="sxs-lookup"><span data-stu-id="73e6e-216">Exchange Online Organization Management (this is assigned in Exchange Online)</span></span>|[<span data-ttu-id="73e6e-217">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="73e6e-217">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo) <p> [<span data-ttu-id="73e6e-218">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="73e6e-218">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)|
|<span data-ttu-id="73e6e-219">検索と消去 (セキュリティ/コンプライアンス センターでのみ割り当てることができます)</span><span class="sxs-lookup"><span data-stu-id="73e6e-219">Search and Purge (this is assigned only in the Security & Compliance Center)</span></span>|[<span data-ttu-id="73e6e-220">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="73e6e-220">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)|

<span data-ttu-id="73e6e-221">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-221">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-microsoft-defender-for-office-365"></a><span data-ttu-id="73e6e-222">Microsoft Defender for Office 365 を取得する</span><span class="sxs-lookup"><span data-stu-id="73e6e-222">Get Microsoft Defender for Office 365</span></span>

<span data-ttu-id="73e6e-223">Microsoft Defender for Office 365 は、Microsoft 365 E5、Office 365 E5、Office 365 A5、Microsoft 365 Business Premium などの特定のサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="73e6e-223">Microsoft Defender for Office 365 is included in certain subscriptions, such as Microsoft 365 E5, Office 365 E5, Office 365 A5, and Microsoft 365 Business Premium.</span></span> <span data-ttu-id="73e6e-224">サブスクリプションに Defender for Office 365 が含まれていない場合は、特定のサブスクリプションへのアドオンとして Defender for Office 365 プラン 1 または Defender for Office 365 プラン 2 を購入できます。</span><span class="sxs-lookup"><span data-stu-id="73e6e-224">If your subscription does not include Defender for Office 365, you can purchase Defender for Office 365 Plan 1 or Defender for Office 365 Plan 2 as an add-on to certain subscriptions.</span></span> <span data-ttu-id="73e6e-225">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-225">To learn more, see the following resources:</span></span>

- <span data-ttu-id="73e6e-226">Defender for Office 365 プランを含むサブスクリプションのリストについては、「[Microsoft Defender for Office 365 の可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-226">[Microsoft Defender for Office 365 availability](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) for a list of subscriptions that include Defender for Office 365 plans.</span></span>

- <span data-ttu-id="73e6e-227">プラン 1 と 2 に含まれる機能のリストについては、「[Microsoft Defender for Office 365 プランで利用できる機能](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」</span><span class="sxs-lookup"><span data-stu-id="73e6e-227">[Feature availability across Microsoft Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) for a list of features included in Plan 1 and 2.</span></span>

- <span data-ttu-id="73e6e-228">[適切な Microsoft Defender for Office 365 を入手](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)して、プランを比較し、Defender for Office 365 を購入してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-228">[Get the right Microsoft Defender for Office 365](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) to compare plans and purchase Defender for Office 365.</span></span>

- [<span data-ttu-id="73e6e-229">無料試用版を開始する</span><span class="sxs-lookup"><span data-stu-id="73e6e-229">Start a free trial</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a><span data-ttu-id="73e6e-230">Microsoft Defender for Office 365 の新機能</span><span class="sxs-lookup"><span data-stu-id="73e6e-230">New features in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="73e6e-231">Microsoft Defender for Office 365 には継続的に新機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="73e6e-231">New features are added to Microsoft Defender for Office 365 continually.</span></span> <span data-ttu-id="73e6e-232">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73e6e-232">To learn more, see the following resources:</span></span>

- <span data-ttu-id="73e6e-233">「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)」は、開発およびロール アウトの新機能の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="73e6e-233">[Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) provides a list of new features in development and rolling out.</span></span>

- <span data-ttu-id="73e6e-234">[Microsoft Defender for Office 365 サービスの説明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)は、Defender for Office 365 プラン全体の機能と可用性について説明しています。</span><span class="sxs-lookup"><span data-stu-id="73e6e-234">[Microsoft Defender for Office 365 Service Description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describes features and availability across Defender for Office 365 plans.</span></span>

## <a name="see-also"></a><span data-ttu-id="73e6e-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="73e6e-235">See also</span></span>

- [<span data-ttu-id="73e6e-236">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73e6e-236">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

- <span data-ttu-id="73e6e-237">[Microsoft 365 Defender での自動調査と応答 (AIR)](../defender/m365d-autoir.md) 1</span><span class="sxs-lookup"><span data-stu-id="73e6e-237">[Automated investigation and response (AIR) in Microsoft 365 Defender](../defender/m365d-autoir.md) 1</span></span>