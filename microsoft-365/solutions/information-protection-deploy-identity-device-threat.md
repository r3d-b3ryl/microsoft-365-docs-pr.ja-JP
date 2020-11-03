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
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 の id、デバイス、および脅威保護サービスによる個人データ漏洩を防止します。
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847180"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="51c3e-103">データプライバシー規制に id、デバイス、および脅威保護を使用する</span><span class="sxs-lookup"><span data-stu-id="51c3e-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="51c3e-104">Microsoft 365 には、組織がデータプライバシー関連のコンプライアンス規制に準拠するために役立つ、id、デバイス、および脅威保護のさまざまな機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="51c3e-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="51c3e-105">この記事では、これらの分野で必要なデータプライバシーの規則について説明し、関連する Microsoft 365 の機能とサービスの一覧を提供し、実装要件に対応するための詳細情報へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="51c3e-106">Id、デバイス、および脅威保護がデータプライバシー規制にどのように関連しているか</span><span class="sxs-lookup"><span data-stu-id="51c3e-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="51c3e-107">データのプライバシーに関する規定は、その特異性によって異なりますが、呼び出し対象の本質は GDPR の記事 5 (1) (f) に含まれています。これは次のように記述します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="51c3e-108">個人データの適切なセキュリティを確保する方法で処理されるのは、承認されていない、または違法な処理に対する保護や、適切な技術または組織上の手段 (「誠実で機密性」) を使用した、偶発的な損失、破壊または破損の防止です。</span><span class="sxs-lookup"><span data-stu-id="51c3e-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="51c3e-109">個人データ違反は、管理者またはエンドユーザーのアカウント侵害や悪意のあるシステムアクセスによって発生することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="51c3e-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="51c3e-110">たとえば、管理者アカウントのハッキングによって、顧客のクレジットカード番号またはその他の個人情報を exfiltration することができます。</span><span class="sxs-lookup"><span data-stu-id="51c3e-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="51c3e-111">Microsoft 365 で使用可能なすべての推奨される id、デバイス、および脅威保護を実装する必要があります。これは、コンプライアンスマネージャーに含まれるコンプライアンススコアに反映される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="51c3e-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="51c3e-112">評価作業とコンプライアンスマネージャーの結果の使用</span><span class="sxs-lookup"><span data-stu-id="51c3e-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="51c3e-113">コンプライアンスマネージャーには、次のカテゴリを使用した id、デバイス、および脅威保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51c3e-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="51c3e-114">Id は、 **コントロールアクセス** のカテゴリに対応します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="51c3e-115">デバイスの **管理** カテゴリに対応します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="51c3e-116">脅威保護は **脅威からの保護** カテゴリに対応します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="51c3e-117">これらの4つの主要なデータプライバシー規制のセット全体でこれらを選択した場合、コンプライアンスマネージャーは90の改善アクションを指定します。ほとんどの場合、スコアは "27" です。</span><span class="sxs-lookup"><span data-stu-id="51c3e-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="51c3e-118">このような大規模な番号は、これらのカテゴリのコンプライアンスマネージャーによって呼び出されているため、参考として、いくつかの一般的なものがここに記載されています。</span><span class="sxs-lookup"><span data-stu-id="51c3e-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="51c3e-119">Id と **コントロールアクセス** カテゴリに [azure Active DIRECTORY (azure AD)](https://azure.microsoft.com/services/active-directory/)を使用します。これには、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="51c3e-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="51c3e-120">リプレイ対策認証を実装する ("Man-in-the-middle" 攻撃を防ぐため)</span><span class="sxs-lookup"><span data-stu-id="51c3e-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="51c3e-121">レガシ認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="51c3e-121">Block legacy authentication.</span></span>
- <span data-ttu-id="51c3e-122">ユーザーのリスクとユーザーサインインリスクポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="51c3e-123">管理者および非管理者に対して、条件付きアクセスと多要素認証 (MFA) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="51c3e-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="51c3e-124">パスワードポリシーを構成して、適用します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="51c3e-125">Azure AD 特権 Id 管理を使用して、特権アカウントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="51c3e-126">終了時にアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="51c3e-126">Disable access upon termination.</span></span>
- <span data-ttu-id="51c3e-127">ユーザーアカウントと状態の変更を監査します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="51c3e-128">役割グループと管理上の変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="51c3e-129">デバイス用の [Microsoft エンドポイントマネージャー](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) と **デバイスの管理** カテゴリを使用して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="51c3e-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="51c3e-130">Jail が壊れていて、モバイルデバイスをブロックする。</span><span class="sxs-lookup"><span data-stu-id="51c3e-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="51c3e-131">モバイルデバイス管理用に Intune を構成します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="51c3e-132">Android、iOS、macOS、Windows デバイスのコンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="51c3e-133">Android、iOS、macOS、Windows デバイス用のデバイス構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="51c3e-134">IOS および Windows 用のアプリ保護ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="51c3e-135">ロック画面を使用して情報を隠す。</span><span class="sxs-lookup"><span data-stu-id="51c3e-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="51c3e-136">モバイルデバイスのパスワードポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="51c3e-137">モバイルデバイスが非アクティブ時にロックされるようにする。</span><span class="sxs-lookup"><span data-stu-id="51c3e-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="51c3e-138">複数のサインインエラーについてモバイルデバイスをワイプする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c3e-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="51c3e-139">「 **脅威からの保護** 」カテゴリで、 [Exchange Online Protection と Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md)を使用します。これには、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="51c3e-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="51c3e-140">送信者の認証を有効にします (SPF、DMARC、および DKIM)。</span><span class="sxs-lookup"><span data-stu-id="51c3e-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="51c3e-141">Microsoft Defender for Office 365 のフィッシング対策ポリシーをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="51c3e-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="51c3e-142">安全な添付ファイルを実装します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="51c3e-143">安全なリンクを実装します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-143">Implement Safe Links.</span></span>
- <span data-ttu-id="51c3e-144">マルウェアの検出と応答のポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="51c3e-145">送信および受信スパムポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="51c3e-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="51c3e-146">設定</span><span class="sxs-lookup"><span data-stu-id="51c3e-146">References:</span></span>

- [<span data-ttu-id="51c3e-147">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="51c3e-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="51c3e-148">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="51c3e-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="51c3e-149">添付ファイル保護</span><span class="sxs-lookup"><span data-stu-id="51c3e-149">Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="51c3e-150">リンク保護</span><span class="sxs-lookup"><span data-stu-id="51c3e-150">Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="51c3e-151">安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="51c3e-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
