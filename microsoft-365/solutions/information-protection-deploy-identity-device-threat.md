---
title: データプライバシー規制に ID、デバイス、および脅威保護を使用する
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
description: Microsoft 365 の ID、デバイス、および脅威保護サービスによる個人データ侵害を防止します。
ms.openlocfilehash: 145b8a59f7eafb95adf71dc24613ee15ef1c2cca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052352"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="f365d-103">データプライバシー規制に ID、デバイス、および脅威保護を使用する</span><span class="sxs-lookup"><span data-stu-id="f365d-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="f365d-104">Microsoft 365 には、組織がデータプライバシー関連のコンプライアンス規制に準拠するために使用できる ID、デバイス、および脅威保護機能が多数提供されています。</span><span class="sxs-lookup"><span data-stu-id="f365d-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="f365d-105">この記事では、これらの分野で必要なデータプライバシー規制について説明し、実装要件に対処するために役立つ詳細な情報へのリンクを含む、関連する Microsoft 365 の機能とサービスの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="f365d-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="f365d-106">ID、デバイス、および脅威保護がデータプライバシー規制とどのように関連付けるか</span><span class="sxs-lookup"><span data-stu-id="f365d-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="f365d-107">データプライバシーに関する規制は、その具体的な内容によって異なりますが、その本質は GDPR の第 5(1)(f) 条に示されています。</span><span class="sxs-lookup"><span data-stu-id="f365d-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="f365d-108">個人データは、不正または違法な処理に対する保護、偶発的な損失、破壊または損害に対する保護を含む、個人データの適切なセキュリティを確保する方法で、適切な技術的または組織的措置 ('整合性と機密性') を使用して処理されます。</span><span class="sxs-lookup"><span data-stu-id="f365d-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="f365d-109">個人データ侵害は、多くの場合、管理アカウントまたはエンド ユーザー アカウントの侵害と悪意のあるシステム アクセスによって引き起こされます。</span><span class="sxs-lookup"><span data-stu-id="f365d-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="f365d-110">たとえば、管理者アカウントのハッキングによって、顧客のクレジット カード番号や他の個人情報が浸透する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f365d-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="f365d-111">Microsoft 365 で使用可能なすべての一般的に推奨される ID、デバイス、および脅威保護を実装する必要があります。コンプライアンス スコアはコンプライアンス マネージャーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="f365d-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="f365d-112">評価作業とコンプライアンス マネージャーの結果の使用</span><span class="sxs-lookup"><span data-stu-id="f365d-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="f365d-113">コンプライアンス マネージャーには、次のカテゴリを使用した ID、デバイス、および脅威の保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f365d-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="f365d-114">IDENTITY はコントロール アクセス **カテゴリに対応** します</span><span class="sxs-lookup"><span data-stu-id="f365d-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="f365d-115">[デバイスの管理] カテゴリに **対応** するデバイス</span><span class="sxs-lookup"><span data-stu-id="f365d-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="f365d-116">脅威保護は、[脅威に対する **保護] カテゴリに対応** します。</span><span class="sxs-lookup"><span data-stu-id="f365d-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="f365d-117">これらが 4 つの主要なデータ プライバシー規制のサンプル セット全体で選択されている場合、コンプライアンス マネージャーは 90 の改善アクションを指定します。そのほとんどが "27" と評価されます。</span><span class="sxs-lookup"><span data-stu-id="f365d-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="f365d-118">このような大きな数は、これらのカテゴリのコンプライアンス マネージャーによって呼び出されるので、参照のために、より一般的な一部がここに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f365d-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="f365d-119">ID およびコントロール アクセス カテゴリAD Azure Active **Directory** [(Azure AD)](https://azure.microsoft.com/services/active-directory/)を使用して、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f365d-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="f365d-120">再生に強い認証を実装する ("Man in the middle" 攻撃を防ぐため)</span><span class="sxs-lookup"><span data-stu-id="f365d-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="f365d-121">レガシ認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="f365d-121">Block legacy authentication.</span></span>
- <span data-ttu-id="f365d-122">ユーザー リスクとユーザー サインイン リスク ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="f365d-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="f365d-123">管理者および管理者以外のユーザーに対して条件付きアクセスと多要素認証 (MFA) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f365d-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="f365d-124">パスワード ポリシーを構成して適用します。</span><span class="sxs-lookup"><span data-stu-id="f365d-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="f365d-125">Azure の特権 ID 管理を使用して、特権ADへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="f365d-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="f365d-126">終了時にアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f365d-126">Disable access upon termination.</span></span>
- <span data-ttu-id="f365d-127">ユーザー アカウントと状態の変更を監査します。</span><span class="sxs-lookup"><span data-stu-id="f365d-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="f365d-128">役割グループと管理上の変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="f365d-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="f365d-129">デバイス [と [デバイスの管理](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) ] カテゴリに Microsoft Endpoint Manager を **使用すると、** 次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f365d-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="f365d-130">壊れた、根ざしたモバイル デバイスの脱獄をブロックします。</span><span class="sxs-lookup"><span data-stu-id="f365d-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="f365d-131">モバイル デバイス管理用に Intune を構成します。</span><span class="sxs-lookup"><span data-stu-id="f365d-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="f365d-132">Android、iOS、macOS、Windows デバイスのコンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f365d-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="f365d-133">Android、iOS、macOS、Windows デバイスのデバイス構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f365d-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="f365d-134">iOS と Windows のアプリ保護ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f365d-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="f365d-135">ロック画面で情報を隠す。</span><span class="sxs-lookup"><span data-stu-id="f365d-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="f365d-136">モバイル デバイスのパスワード ポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="f365d-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="f365d-137">非アクティブ時にモバイル デバイスをロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f365d-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="f365d-138">複数のサインインエラーでモバイル デバイスにワイプを要求する。</span><span class="sxs-lookup"><span data-stu-id="f365d-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="f365d-139">[[脅威に対する保護] カテゴリOffice Exchange](../security/defender-365-security/defender-for-office-365.md) Online Protectionおよび Microsoft Defender を 365 に使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f365d-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/defender-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="f365d-140">送信者認証 (SPF、DMARC、DKIM) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f365d-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="f365d-141">365 のフィッシングOfficeポリシー用に Microsoft Defender をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="f365d-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="f365d-142">安全な添付ファイルを実装します。</span><span class="sxs-lookup"><span data-stu-id="f365d-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="f365d-143">安全なリンクを実装します。</span><span class="sxs-lookup"><span data-stu-id="f365d-143">Implement Safe Links.</span></span>
- <span data-ttu-id="f365d-144">マルウェア検出ポリシーと応答ポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="f365d-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="f365d-145">送信スパム ポリシーと受信スパム ポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="f365d-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="f365d-146">参照:</span><span class="sxs-lookup"><span data-stu-id="f365d-146">References:</span></span>

- [<span data-ttu-id="f365d-147">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="f365d-147">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)
- [<span data-ttu-id="f365d-148">365 の脅威からOfficeする</span><span class="sxs-lookup"><span data-stu-id="f365d-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="f365d-149">添付ファイル保護</span><span class="sxs-lookup"><span data-stu-id="f365d-149">Safe Attachments</span></span>](../security/defender-365-security/safe-attachments.md)
- [<span data-ttu-id="f365d-150">リンク保護</span><span class="sxs-lookup"><span data-stu-id="f365d-150">Safe Links</span></span>](../security/defender-365-security/safe-links.md)
- [<span data-ttu-id="f365d-151">安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="f365d-151">Safe Documents</span></span>](../security/defender-365-security/safe-docs.md)
