---
title: セキュリティで保護された電子メールの推奨ポリシー - Microsoft 365 enterprise |Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 4651f220e88bf5161a8ddfe4e2bdde03118afa15
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288481"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="aedc7-103">電子メールをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="aedc7-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="aedc7-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="aedc7-104">**Applies to**</span></span>
- [<span data-ttu-id="aedc7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="aedc7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="aedc7-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="aedc7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)


<span data-ttu-id="aedc7-107">この記事では、最新の認証と条件付きアクセスをサポートする組織の電子メール および電子メール クライアントを保護するために、推奨される ID およびデバイス アクセス ポリシーを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-107">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="aedc7-108">このガイダンスは、共通 [ID](identity-access-policies.md) ポリシーとデバイス アクセス ポリシーに基じ、さらにいくつかの推奨事項も示します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-108">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="aedc7-109">これらの推奨事項は、ニーズの粒度に基づいて適用できるセキュリティと保護の 3 つの異なる層に基づいており、ベースライン、機密、厳しく規制 **されています**。</span><span class="sxs-lookup"><span data-stu-id="aedc7-109">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="aedc7-110">これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aedc7-110">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="aedc7-111">これらの推奨事項では、ユーザーがモバイル デバイスで iOS および Android 用の Outlook を含む最新の電子メール クライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aedc7-111">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="aedc7-112">iOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="aedc7-112">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="aedc7-113">これらのモバイル Outlook アプリは、モバイルの使用をサポートし、他の Microsoft クラウド セキュリティ機能と一緒に動作するセキュリティ機能も備えた設計です。</span><span class="sxs-lookup"><span data-stu-id="aedc7-113">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="aedc7-114">詳細については [、iOS および Android 用の Outlook に関する FAQ を参照してください](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="aedc7-114">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="aedc7-115">電子メールを含める一般的なポリシーを更新する</span><span class="sxs-lookup"><span data-stu-id="aedc7-115">Update common policies to include email</span></span>

<span data-ttu-id="aedc7-116">電子メールを保護するために、次の図は、共通 ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="aedc7-116">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="aedc7-117">[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="aedc7-117">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="aedc7-118">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="aedc7-118">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="aedc7-119">ActiveSync クライアントをブロックする Exchange Online の新しいポリシーの追加に注意してください。</span><span class="sxs-lookup"><span data-stu-id="aedc7-119">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="aedc7-120">これにより、Outlook モバイルが強制的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="aedc7-120">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="aedc7-121">ポリシーのセットアップ時にポリシーのスコープに Exchange Online と Outlook を含める場合は、ActiveSync クライアントをブロックする新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aedc7-121">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="aedc7-122">次の表に示すポリシーを確認し、推奨される追加を行うか、既に含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-122">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="aedc7-123">各ポリシーは、共通 ID ポリシーとデバイス アクセス ポリシーに関連 [する構成手順にリンクします](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="aedc7-123">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="aedc7-124">保護レベル</span><span class="sxs-lookup"><span data-stu-id="aedc7-124">Protection level</span></span>|<span data-ttu-id="aedc7-125">Policies</span><span class="sxs-lookup"><span data-stu-id="aedc7-125">Policies</span></span>|<span data-ttu-id="aedc7-126">詳細情報</span><span class="sxs-lookup"><span data-stu-id="aedc7-126">More information</span></span>|
|---|---|---|
|<span data-ttu-id="aedc7-127">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="aedc7-127">**Baseline**</span></span>|[<span data-ttu-id="aedc7-128">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="aedc7-128">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="aedc7-129">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="aedc7-129">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="aedc7-130">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="aedc7-130">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="aedc7-131">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="aedc7-131">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="aedc7-132">アプリ データ保護ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="aedc7-132">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="aedc7-133">Outlook がアプリの一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aedc7-133">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="aedc7-134">各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。</span><span class="sxs-lookup"><span data-stu-id="aedc7-134">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
||[<span data-ttu-id="aedc7-135">承認されたアプリとアプリの保護を要求する</span><span class="sxs-lookup"><span data-stu-id="aedc7-135">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="aedc7-136">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="aedc7-136">Include Exchange Online in the list of cloud apps</span></span>|
||[<span data-ttu-id="aedc7-137">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="aedc7-137">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="aedc7-138">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="aedc7-138">Include Exchange Online in list of cloud apps</span></span>|
||[<span data-ttu-id="aedc7-139">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="aedc7-139">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="aedc7-140">この新しいポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="aedc7-140">Add this new policy</span></span>|
|<span data-ttu-id="aedc7-141">**機密**</span><span class="sxs-lookup"><span data-stu-id="aedc7-141">**Sensitive**</span></span>|[<span data-ttu-id="aedc7-142">サインインリスクが低、中、高 *の* 場合 *に* MFA を要求 *する*</span><span class="sxs-lookup"><span data-stu-id="aedc7-142">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="aedc7-143">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="aedc7-143">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="aedc7-144">準拠した PC とモバイル *デバイスが* 必要</span><span class="sxs-lookup"><span data-stu-id="aedc7-144">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="aedc7-145">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="aedc7-145">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="aedc7-146">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="aedc7-146">**Highly regulated**</span></span>|[<span data-ttu-id="aedc7-147">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="aedc7-147">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="aedc7-148">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="aedc7-148">Include Exchange Online in the assignment of cloud apps</span></span>|
|

## <a name="block-activesync-clients"></a><span data-ttu-id="aedc7-149">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="aedc7-149">Block ActiveSync clients</span></span>

<span data-ttu-id="aedc7-150">このポリシーにより、ActiveSync クライアントは他の条件付きアクセス ポリシーをバイパスしません。</span><span class="sxs-lookup"><span data-stu-id="aedc7-150">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="aedc7-151">ポリシー構成は ActiveSync クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="aedc7-151">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="aedc7-152">[アプリ保護ポリシーを \*\*[要求する] を選択](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)\*\* すると、このポリシーは ActiveSync クライアントをブロックします。</span><span class="sxs-lookup"><span data-stu-id="aedc7-152">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="aedc7-153">このポリシーの作成の詳細については、「条件付きアクセスによるクラウド アプリ アクセスのアプリ保護ポリシーを要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="aedc7-153">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="aedc7-154">シナリオ [1: Office 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)アプリでは、基本認証を利用する Exchange ActiveSync クライアントが Exchange Online に接続することを防ぐ、アプリ保護ポリシーを持つ承認されたアプリが必要です。シナリオ 1 の「手順 2: ActiveSync (EAS) を使用して Exchange Online 用の Azure AD 条件付きアクセス ポリシーを構成する」に従います。</span><span class="sxs-lookup"><span data-stu-id="aedc7-154">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="aedc7-155">また、認証ポリシーを使用して基本[](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)認証を無効にし、すべてのクライアント アクセス要求で最新の認証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aedc7-155">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="aedc7-156">Outlook on the web からの Exchange Online へのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="aedc7-156">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="aedc7-157">ユーザーが Umaged デバイス上の Outlook on the web から添付ファイルをダウンロードする機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="aedc7-157">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="aedc7-158">これらのデバイス上のユーザーは、デバイスにファイルをリークして保存することなく、Office Online を使用してこれらのファイルを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="aedc7-158">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="aedc7-159">管理されていないデバイスでユーザーに添付ファイルが表示されるのをブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aedc7-159">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="aedc7-160">それらのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="aedc7-160">Here are the steps:</span></span>

1. <span data-ttu-id="aedc7-161">[Exchange Online リモート PowerShell セッションに接続します](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aedc7-161">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="aedc7-162">OWA メールボックス ポリシーをまだ持ってない場合は [、New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して OWA メールボックス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-162">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="aedc7-163">添付ファイルの表示を許可し、ダウンロードを許可する場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-163">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="aedc7-164">添付ファイルをブロックする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-164">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. <span data-ttu-id="aedc7-165">Azure portal で、次の設定を使用して新しい条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-165">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="aedc7-166">**割り当て** \>**ユーザーとグループ**: 含める、または除外する適切なユーザーとグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-166">**Assignments** \> **Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="aedc7-167">**割り当て** \>**クラウド アプリまたはアクション** \>**クラウド アプリ** \>**含める** \>**アプリの選択**: Office **365 Exchange Online を選択する**</span><span class="sxs-lookup"><span data-stu-id="aedc7-167">**Assignments** \> **Cloud apps or actions** \> **Cloud apps** \> **Include** \> **Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="aedc7-168">**アクセス制御** \>**セッション**: [アプリによって **適用される制限を使用する] を選択する**</span><span class="sxs-lookup"><span data-stu-id="aedc7-168">**Access controls** \> **Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="aedc7-169">iOS デバイスと Android デバイスで Outlook を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="aedc7-169">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="aedc7-170">iOS および Android デバイスのユーザーが、iOS および Android 用の Outlook を使用して仕事や学校のコンテンツにのみアクセスするには、それらの潜在的なユーザーを対象とする条件付きアクセス ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="aedc7-170">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="aedc7-171">このポリシーを構成する手順については、「iOS および Android 用の Outlook を使用してメッセージングコラボレーション アクセス [を管理する」を参照してください]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="aedc7-171">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>

## <a name="set-up-message-encryption"></a><span data-ttu-id="aedc7-172">メッセージの暗号化を設定する</span><span class="sxs-lookup"><span data-stu-id="aedc7-172">Set up message encryption</span></span>

<span data-ttu-id="aedc7-173">Azure Information Protection の保護機能を活用する新しい Office 365 Message Encryption (OME) 機能により、組織は保護された電子メールを任意のデバイスの誰とでも簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="aedc7-173">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="aedc7-174">ユーザーは、他の Microsoft 365 組織だけでなく、Outlook.com、Gmail、その他のメール サービスを使用して、保護されたメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="aedc7-174">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="aedc7-175">詳細については [、「Set up new Office 365 Message Encryption capabilities 」を参照してください](../../compliance/set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="aedc7-175">For more information, see [Set up new Office 365 Message Encryption capabilities](../../compliance/set-up-new-message-encryption-capabilities.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="aedc7-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="aedc7-176">Next steps</span></span>

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="aedc7-178">次の条件に合ったアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="aedc7-178">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="aedc7-179">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aedc7-179">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="aedc7-180">SharePoint</span><span class="sxs-lookup"><span data-stu-id="aedc7-180">SharePoint</span></span>](sharepoint-file-access-policies.md)
