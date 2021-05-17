---
title: セキュリティ インシデント対応
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: このソリューションは、最も一般的なサイバーセキュリティ攻撃の外観と、Microsoft 365対応方法を示します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65ff75253f45ae2d0f051dafe73c6e665f89827a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205871"
---
# <a name="security-incident-response"></a><span data-ttu-id="64714-103">セキュリティ インシデント対応</span><span class="sxs-lookup"><span data-stu-id="64714-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="64714-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="64714-104">**Applies to**</span></span>
- [<span data-ttu-id="64714-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="64714-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="64714-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="64714-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="64714-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64714-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="64714-108">**概要:** このソリューションは、Office 365 で最も一般的なサイバーセキュリティ攻撃の指標、特定の攻撃を肯定的に確認する方法、およびそれに対応する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="64714-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="64714-109">サイバー攻撃に対応する方法を学ぶ</span><span class="sxs-lookup"><span data-stu-id="64714-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="64714-110">すべてのサイバー攻撃を利用できない。</span><span class="sxs-lookup"><span data-stu-id="64714-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="64714-111">攻撃者は常に防御戦略の新しい弱点を探している、または古い攻撃を行っています。</span><span class="sxs-lookup"><span data-stu-id="64714-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="64714-112">攻撃を認識する方法を知ることにより、攻撃に迅速に対応できます。これにより、セキュリティ インシデントの期間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="64714-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="64714-113">この一連の記事では、特定の種類の攻撃が Microsoft 365に表示される可能性があることを理解し、対応するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="64714-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="64714-114">これらは、以下を理解する簡単なエントリ ポイントです。</span><span class="sxs-lookup"><span data-stu-id="64714-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="64714-115">攻撃とは何か、どのように機能するのか。</span><span class="sxs-lookup"><span data-stu-id="64714-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="64714-116">侵害の指標 (IOC) と呼ばれる、どのような兆候を検索し、それらを検索する方法。</span><span class="sxs-lookup"><span data-stu-id="64714-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="64714-117">攻撃を肯定的に確認する方法。</span><span class="sxs-lookup"><span data-stu-id="64714-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="64714-118">攻撃を断ち切り、将来組織をより良く保護するための手順。</span><span class="sxs-lookup"><span data-stu-id="64714-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="64714-119">各攻撃の種類に関する詳細な情報へのリンク。</span><span class="sxs-lookup"><span data-stu-id="64714-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="64714-120">より多くの記事が時間の間に追加されるので、毎月ここに戻って確認してください。</span><span class="sxs-lookup"><span data-stu-id="64714-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="64714-121">記事の検出と修復</span><span class="sxs-lookup"><span data-stu-id="64714-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="64714-122">Microsoft Office 365 での不正な同意付与の検出と修復</span><span class="sxs-lookup"><span data-stu-id="64714-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="64714-123">Office 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う</span><span class="sxs-lookup"><span data-stu-id="64714-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="64714-124">インシデント対応の記事</span><span class="sxs-lookup"><span data-stu-id="64714-124">Incident response articles</span></span>

- [<span data-ttu-id="64714-125">侵害された Office 365 電子メール アカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="64714-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="64714-126">サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="64714-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="64714-127">Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="64714-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="64714-128">Microsoft 365 セキュリティ ロードマップ - 最初の[30 日間、90](security-roadmap.md)日間、およびそれ以降の最優先事項を使用して、組織をセキュリティ保護するための Microsoft 推奨ベスト プラクティスを実装Microsoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="64714-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="64714-p104">最初の 30 日間で完了すべき作業。すぐにユーザーに影響しますが、それほど大きな影響ではありません。</span><span class="sxs-lookup"><span data-stu-id="64714-p104">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="64714-131">90 日間で実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="64714-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="64714-132">これらは、計画と実装にもう少し時間がかかるが、セキュリティの態勢を大幅に改善する</span><span class="sxs-lookup"><span data-stu-id="64714-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="64714-p106">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="64714-p106">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>
