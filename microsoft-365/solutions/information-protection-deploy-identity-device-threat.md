---
title: データプライバシー規制に id、デバイス、および脅威保護を使用する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Microsoft 365 の id、デバイス、および脅威保護サービスによる個人データ漏洩を防止します。
ms.openlocfilehash: a309b5d0ba5f939cf89a31d7ac91ca3aac25ce0d
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46520983"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="b2307-103">データプライバシー規制に id、デバイス、および脅威保護を使用する</span><span class="sxs-lookup"><span data-stu-id="b2307-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="b2307-104">Microsoft 365 には、組織がデータプライバシー関連のコンプライアンス規制に準拠するために役立つ、id、デバイス、および脅威保護のさまざまな機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b2307-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="b2307-105">この記事では、これらの分野で必要なデータプライバシーの規則について説明し、関連する Microsoft 365 の機能とサービスの一覧を提供し、実装要件に対応するための詳細情報へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="b2307-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="b2307-106">Id、デバイス、および脅威保護がデータプライバシー規制にどのように関連しているか</span><span class="sxs-lookup"><span data-stu-id="b2307-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="b2307-107">データのプライバシーに関する規定は、その特異性によって異なりますが、呼び出し対象の本質は GDPR の記事 5 (1) (f) に含まれています。これは次のように記述します。</span><span class="sxs-lookup"><span data-stu-id="b2307-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="b2307-108">個人データの適切なセキュリティを確保する方法で処理されるのは、承認されていない、または違法な処理に対する保護や、適切な技術または組織上の手段 (「誠実で機密性」) を使用した、偶発的な損失、破壊または破損の防止です。</span><span class="sxs-lookup"><span data-stu-id="b2307-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="b2307-109">個人データ違反は、管理者またはエンドユーザーのアカウント侵害や悪意のあるシステムアクセスによって発生することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="b2307-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="b2307-110">たとえば、管理者アカウントのハッキングによって、顧客のクレジットカード番号またはその他の個人情報を exfiltration することができます。</span><span class="sxs-lookup"><span data-stu-id="b2307-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="b2307-111">通常、Microsoft 365 で使用できるすべての推奨される id、デバイス、および脅威保護を実装する必要があります。これは、コンプライアンススコアに反映されます。</span><span class="sxs-lookup"><span data-stu-id="b2307-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your Compliance Score.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a><span data-ttu-id="b2307-112">評価作業とコンプライアンススコアの結果の使用</span><span class="sxs-lookup"><span data-stu-id="b2307-112">Using the results of your assessment work and Compliance Score</span></span>

<span data-ttu-id="b2307-113">コンプライアンススコアには、次のカテゴリを使用した id、デバイス、および脅威保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2307-113">Compliance Score includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="b2307-114">Id は、**コントロールアクセス**のカテゴリに対応します。</span><span class="sxs-lookup"><span data-stu-id="b2307-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="b2307-115">デバイスの**管理**カテゴリに対応します。</span><span class="sxs-lookup"><span data-stu-id="b2307-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="b2307-116">脅威保護は**脅威からの保護**カテゴリに対応します。</span><span class="sxs-lookup"><span data-stu-id="b2307-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="b2307-117">これらの4つの主要なデータプライバシー規制のセット全体でこれらの規則が選択されている場合、コンプライアンススコアは90の改善アクションを指定します。ほとんどの場合、スコアは "27" です。</span><span class="sxs-lookup"><span data-stu-id="b2307-117">If these are selected across our sample set of four major data privacy regulations, Compliance Score specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="b2307-118">このような大規模な番号は、これらのカテゴリのコンプライアンススコアによって呼び出されているため、参考として、より一般的なもののいくつかを紹介します。</span><span class="sxs-lookup"><span data-stu-id="b2307-118">Since such a large number are called out by Compliance Score for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="b2307-119">Id と**コントロールアクセス**カテゴリに[azure Active DIRECTORY (azure AD)](https://azure.microsoft.com/services/active-directory/)を使用します。これには、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b2307-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="b2307-120">リプレイ対策認証を実装する ("Man-in-the-middle" 攻撃を防ぐため)</span><span class="sxs-lookup"><span data-stu-id="b2307-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="b2307-121">レガシ認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="b2307-121">Block legacy authentication.</span></span>
- <span data-ttu-id="b2307-122">ユーザーのリスクとユーザーサインインリスクポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="b2307-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="b2307-123">管理者および非管理者に対して、条件付きアクセスと多要素認証 (MFA) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b2307-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="b2307-124">パスワードポリシーを構成して、適用します。</span><span class="sxs-lookup"><span data-stu-id="b2307-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="b2307-125">Azure AD 特権 Id 管理を使用して、特権アカウントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="b2307-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="b2307-126">終了時にアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b2307-126">Disable access upon termination.</span></span>
- <span data-ttu-id="b2307-127">ユーザーアカウントと状態の変更を監査します。</span><span class="sxs-lookup"><span data-stu-id="b2307-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="b2307-128">役割グループと管理上の変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2307-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="b2307-129">デバイス用の[Microsoft エンドポイントマネージャー](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)と**デバイスの管理**カテゴリを使用して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b2307-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="b2307-130">Jail が壊れていて、モバイルデバイスをブロックする。</span><span class="sxs-lookup"><span data-stu-id="b2307-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="b2307-131">モバイルデバイス管理用に Intune を構成します。</span><span class="sxs-lookup"><span data-stu-id="b2307-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="b2307-132">Android、iOS、macOS、Windows デバイスのコンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2307-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="b2307-133">Android、iOS、macOS、Windows デバイス用のデバイス構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2307-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="b2307-134">IOS および Windows 用のアプリ保護ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2307-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="b2307-135">ロック画面を使用して情報を隠す。</span><span class="sxs-lookup"><span data-stu-id="b2307-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="b2307-136">モバイルデバイスのパスワードポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="b2307-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="b2307-137">モバイルデバイスが非アクティブ時にロックされるようにする。</span><span class="sxs-lookup"><span data-stu-id="b2307-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="b2307-138">複数のサインインエラーについてモバイルデバイスをワイプする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2307-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="b2307-139">[Exchange Online Protection と Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md)を使用して、[**脅威からの保護**] カテゴリを使用します。これには次のことができます。</span><span class="sxs-lookup"><span data-stu-id="b2307-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="b2307-140">送信者の認証を有効にします (SPF、DMARC、および DKIM)。</span><span class="sxs-lookup"><span data-stu-id="b2307-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="b2307-141">Office 365 Advanced Threat Protection (ATP) フィッシング対策ポリシーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="b2307-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="b2307-142">ATP の安全な添付ファイルを実装します。</span><span class="sxs-lookup"><span data-stu-id="b2307-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="b2307-143">ATP の安全なリンクを実装します。</span><span class="sxs-lookup"><span data-stu-id="b2307-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="b2307-144">マルウェアの検出と応答のポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="b2307-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="b2307-145">送信および受信スパムポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="b2307-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="b2307-146">設定</span><span class="sxs-lookup"><span data-stu-id="b2307-146">References:</span></span>

- [<span data-ttu-id="b2307-147">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="b2307-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="b2307-148">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="b2307-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="b2307-149">ATP の安全な添付ファイル機能</span><span class="sxs-lookup"><span data-stu-id="b2307-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="b2307-150">ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="b2307-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="b2307-151">ATP の安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="b2307-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
