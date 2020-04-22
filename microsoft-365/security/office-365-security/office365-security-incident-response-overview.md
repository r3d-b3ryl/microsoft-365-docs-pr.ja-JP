---
title: セキュリティインシデントへの対応
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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: このソリューションは、Microsoft 365 で最も一般的な cybersecurity 攻撃の内容と、それらに対する応答方法を示します。
ms.openlocfilehash: 4c5713a0689dae07fe5300c04754d77912f53976
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634510"
---
# <a name="security-incident-response"></a><span data-ttu-id="658f5-103">セキュリティインシデントへの対応</span><span class="sxs-lookup"><span data-stu-id="658f5-103">Security Incident Response</span></span>

 <span data-ttu-id="658f5-104">**概要:** このソリューションは、Office 365 の最も一般的な cybersecurity 攻撃に対するインジケーター、特定の攻撃を確実に確認する方法、およびそれに対応する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="658f5-104">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="overview"></a><span data-ttu-id="658f5-105">概要</span><span class="sxs-lookup"><span data-stu-id="658f5-105">Overview</span></span>

<span data-ttu-id="658f5-106">すべての cyberattacks を thwarted にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="658f5-106">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="658f5-107">攻撃者は、絶えず防御戦略の新しい弱点を模索しているか、古い弱点を悪用しています。</span><span class="sxs-lookup"><span data-stu-id="658f5-107">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="658f5-108">攻撃を認識する方法を理解することで、迅速に応答することができます。これにより、セキュリティインシデントの期間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="658f5-108">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="658f5-109">この記事の一連の記事では、Microsoft 365 における特定の種類の攻撃の内容を理解するのに役立つだけでなく、対処するための手順が示されています。</span><span class="sxs-lookup"><span data-stu-id="658f5-109">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="658f5-110">次のことを理解するための簡単なエントリポイントです。</span><span class="sxs-lookup"><span data-stu-id="658f5-110">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="658f5-111">攻撃とは何か、どのように動作するか。</span><span class="sxs-lookup"><span data-stu-id="658f5-111">What the attack is and how it works.</span></span>

- <span data-ttu-id="658f5-112">どのような兆候 (IOC) を検索し、それらを検索するかを示す標識。</span><span class="sxs-lookup"><span data-stu-id="658f5-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="658f5-113">攻撃を確実に確認する方法。</span><span class="sxs-lookup"><span data-stu-id="658f5-113">How to positively confirm the attack.</span></span>

- <span data-ttu-id="658f5-114">攻撃を減らすために必要な手順と、今後の組織の保護を強化するための手順。</span><span class="sxs-lookup"><span data-stu-id="658f5-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="658f5-115">各攻撃の種類に関する詳細情報へのリンク。</span><span class="sxs-lookup"><span data-stu-id="658f5-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="658f5-116">長期間にわたって記事が追加された場合は、ここに戻ってください。</span><span class="sxs-lookup"><span data-stu-id="658f5-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="658f5-117">記事を検出して修復する</span><span class="sxs-lookup"><span data-stu-id="658f5-117">Detect and remediate articles</span></span>

- [<span data-ttu-id="658f5-118">Microsoft Office 365 での不正な同意付与の検出と修復</span><span class="sxs-lookup"><span data-stu-id="658f5-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="658f5-119">Office 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う</span><span class="sxs-lookup"><span data-stu-id="658f5-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="658f5-120">インシデント対応の記事</span><span class="sxs-lookup"><span data-stu-id="658f5-120">Incident response articles</span></span>

- [<span data-ttu-id="658f5-121">侵害された Office 365 電子メール アカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="658f5-121">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="658f5-122">セキュリティで保護された Microsoft 365 (cybersecurity pro など)</span><span class="sxs-lookup"><span data-stu-id="658f5-122">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="658f5-123">Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力な一連のセキュリティ機能が付属しています。</span><span class="sxs-lookup"><span data-stu-id="658f5-123">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="658f5-124">Microsoft 365 のセキュリティロードマップを使用して、[最初の30日間、90日間、](security-roadmap.md) Microsoft の microsoft 365 組織をセキュリティで保護するためのベストプラクティスを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="658f5-124">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="658f5-125">最初の30日間に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="658f5-125">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="658f5-126">これらはすぐに影響を受け、ユーザーにとって影響が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="658f5-126">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="658f5-127">90日以内に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="658f5-127">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="658f5-128">これらは、計画と実装に少し時間がかかりますが、セキュリティに関する姿勢が大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="658f5-128">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="658f5-129">90日を超えています。</span><span class="sxs-lookup"><span data-stu-id="658f5-129">Beyond 90 days.</span></span> <span data-ttu-id="658f5-130">これらの機能強化は、最初の90日間にビルドされました。</span><span class="sxs-lookup"><span data-stu-id="658f5-130">These enhancements build in your first 90 days work.</span></span>
