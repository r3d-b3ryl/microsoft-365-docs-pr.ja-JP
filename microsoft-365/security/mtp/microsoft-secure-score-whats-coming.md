---
title: Microsoft のセキュリティで保護されたスコアについて
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコア、詳細情報の計算方法、およびセキュリティ管理者が期待できるセキュリティについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティで保護されたスコア、セキュリティセンター、改善アクション
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266975"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="2472a-104">Microsoft のセキュリティで保護されたスコアについて</span><span class="sxs-lookup"><span data-stu-id="2472a-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="2472a-105">Microsoft のセキュリティスコアをより良いものにして、セキュリティの状況をより良くし、利便性を向上させるために、近い将来にいくつかの変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="2472a-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="2472a-106">スコアと可能な最大スコアが変わります。</span><span class="sxs-lookup"><span data-stu-id="2472a-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="2472a-107">ただし、これはセキュリティに関する姿勢の変化を意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="2472a-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="2472a-108">最近の変更については、「 [Microsoft のセキュリティで保護されたスコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2472a-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="2472a-109">2020年3月2日</span><span class="sxs-lookup"><span data-stu-id="2472a-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="2472a-110">Intune からの改善アクションの削除</span><span class="sxs-lookup"><span data-stu-id="2472a-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="2472a-111">Intune から提供された Microsoft のセキュリティで保護されたスコアの改善アクションを評価した後は、組織内のデバイスのセキュリティに関する有益な表現を提供していないと判断されました。</span><span class="sxs-lookup"><span data-stu-id="2472a-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="2472a-112">ポリシーを重視するのではなく、デバイスの構成状態を直接評価するセキュリティ制御に移行することに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="2472a-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="2472a-113">次の Intune 向上アクションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="2472a-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="2472a-114">Microsoft Intune モバイルデバイス管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="2472a-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="2472a-115">Android 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="2472a-116">Android 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="2472a-117">Android 用の Microsoft Intune アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="2472a-118">IOS 用 Microsoft Intune アプリ保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="2472a-119">Microsoft Intune コンプライアンスポリシーが割り当てられていないデバイスを、準拠していないとしてマークする</span><span class="sxs-lookup"><span data-stu-id="2472a-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="2472a-120">IOS 用 Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="2472a-121">MacOS の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="2472a-122">Windows 用の Microsoft Intune コンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="2472a-123">Android 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="2472a-124">Android 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="2472a-125">MacOS 用の Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="2472a-126">IOS 用 Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="2472a-127">Windows 用 Microsoft Intune 構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="2472a-128">Microsoft Intune で拡張 jailbreak 検出を有効にする</span><span class="sxs-lookup"><span data-stu-id="2472a-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="2472a-129">すべてのデバイスにパッチを適用して、ウイルス対策とファイアウォールを有効にする必要がある</span><span class="sxs-lookup"><span data-stu-id="2472a-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="2472a-130">Microsoft Intune への Windows Defender ATP 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="2472a-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="2472a-131">Microsoft Intune Windows 情報保護ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2472a-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="2472a-132">すべてのデバイスに高度なセキュリティ構成を要求する</span><span class="sxs-lookup"><span data-stu-id="2472a-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="2472a-133">毎週ブロックされたデバイスのレポートを確認する</span><span class="sxs-lookup"><span data-stu-id="2472a-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="2472a-134">信頼性の高い測定要件を満たしていない改善アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="2472a-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="2472a-135">マイクロソフトのセキュリティスコアが意味があり、すべての改善アクションが測定可能で信頼性を備えていることを確認するために、次の改善アクションを削除しています。</span><span class="sxs-lookup"><span data-stu-id="2472a-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="2472a-136">監査データの記録を有効にする</span><span class="sxs-lookup"><span data-stu-id="2472a-136">Turn on audit data recording</span></span>
- <span data-ttu-id="2472a-137">危険かつ準拠していないシャドウ IT アプリケーションを検出する</span><span class="sxs-lookup"><span data-stu-id="2472a-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="2472a-138">環境に接続されたリスクの高い OAuth アプリケーションをブロック & アクセス許可を確認する</span><span class="sxs-lookup"><span data-stu-id="2472a-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="2472a-139">SharePoint online ドキュメントライブラリのバージョン管理を設定する</span><span class="sxs-lookup"><span data-stu-id="2472a-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="2472a-140">MFA 向上アクションの更新</span><span class="sxs-lookup"><span data-stu-id="2472a-140">MFA improvement action updates</span></span>

<span data-ttu-id="2472a-141">ビジネスに適したポリシーを適用しているときに、最高レベルのセキュリティを確保するための企業の必要性を反映するために、Microsoft Secure Score は、多要素認証を中心とした3つの改善アクションを削除し、2つを追加します。</span><span class="sxs-lookup"><span data-stu-id="2472a-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="2472a-142">削除される3つのを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2472a-142">The three that will be removed:</span></span>

- <span data-ttu-id="2472a-143">すべてのユーザーに多要素認証を登録する</span><span class="sxs-lookup"><span data-stu-id="2472a-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="2472a-144">すべてのユーザーに MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="2472a-144">Require MFA for all users</span></span>
- <span data-ttu-id="2472a-145">Azure AD の特権の役割に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="2472a-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="2472a-146">新しい向上アクションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="2472a-146">New improvement actions added:</span></span>

- <span data-ttu-id="2472a-147">すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする</span><span class="sxs-lookup"><span data-stu-id="2472a-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="2472a-148">管理役割に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="2472a-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="2472a-149">これらの新しい改善アクションでは、ユーザーまたは管理者に対して複数要素認証 (MFA) をディレクトリに登録し、組織のニーズに合ったポリシーの適切なセットを確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2472a-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="2472a-150">主な目標は柔軟性にありますが、すべてのユーザーと管理者が複数の要因またはリスクベースの id 確認プロンプトで認証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2472a-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="2472a-151">これには、スコープ決定を適用する複数のポリシーを作成するか、または Microsoft が MFA のユーザーをチャレンジするタイミングを決定するセキュリティの既定値 (3 月16日) を設定するという形をとることができます。</span><span class="sxs-lookup"><span data-stu-id="2472a-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="2472a-152">"レビュー" の向上アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="2472a-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="2472a-153">セキュリティで保護されたスコアの原則の1つは、スコアが標準化され、関連性が簡単であるということです。</span><span class="sxs-lookup"><span data-stu-id="2472a-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="2472a-154">測定できない、または実用的でない改善アクションが発生すると、混乱が生じています。</span><span class="sxs-lookup"><span data-stu-id="2472a-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="2472a-155">1つの Microsoft セキュリティスコアは、すべての推奨事項がスコアに明確な影響を与える場合にのみ意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="2472a-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="2472a-156">改善アクションのレビューは、他の改善アクションと同じ基準として測定されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2472a-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="2472a-157">これらの理由により、レビューリズムを必要とするすべての改善アクションが一時的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="2472a-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="2472a-158">パーツに必要な操作はありません。</span><span class="sxs-lookup"><span data-stu-id="2472a-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="2472a-159">2020年3月16日</span><span class="sxs-lookup"><span data-stu-id="2472a-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="2472a-160">信頼性の高い測定要件を満たしていない改善アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="2472a-160">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="2472a-161">マイクロソフトのセキュリティスコアが意味があり、すべての改善アクションが測定可能で信頼性を備えていることを確認するために、次の改善アクションを削除しています。</span><span class="sxs-lookup"><span data-stu-id="2472a-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="2472a-162">OneDrive for business でユーザーのドキュメントを保存する</span><span class="sxs-lookup"><span data-stu-id="2472a-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="2472a-163">Office 365 の ATP の安全な添付ファイルポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="2472a-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="2472a-164">Office 365 の安全なリンクを設定して Url を確認する</span><span class="sxs-lookup"><span data-stu-id="2472a-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="2472a-165">メールボックスの委任を許可しない</span><span class="sxs-lookup"><span data-stu-id="2472a-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="2472a-166">サイトおよびドキュメントの匿名ゲスト共有リンクを許可する</span><span class="sxs-lookup"><span data-stu-id="2472a-166">Allow anonymous guest sharing links for sites and docs</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="2472a-167">Azure AD 向上アクションのセキュリティの既定のサポート</span><span class="sxs-lookup"><span data-stu-id="2472a-167">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="2472a-168">Microsoft Secure Score は、強化された操作を更新して[AZURE AD のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートします。これにより、一般的な攻撃のために事前に構成されたセキュリティ設定を使用して組織を保護することが容易になります。</span><span class="sxs-lookup"><span data-stu-id="2472a-168">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="2472a-169">次の改善アクションに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="2472a-169">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="2472a-170">すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする</span><span class="sxs-lookup"><span data-stu-id="2472a-170">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="2472a-171">管理役割に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="2472a-171">Require MFA for administrative roles</span></span>
- <span data-ttu-id="2472a-172">従来の認証をブロックするポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="2472a-172">Enable policy to block legacy authentication</span></span>
