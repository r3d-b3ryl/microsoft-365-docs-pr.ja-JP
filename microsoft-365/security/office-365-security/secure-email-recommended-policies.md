---
title: セキュリティで保護された電子メールの推奨ポリシー - Microsoft 365 enterprise |Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 653b16b7b3f6637440e3740830ffe9f9a51c6dd8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166509"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="4eaeb-103">電子メールをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="4eaeb-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="4eaeb-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4eaeb-104">**Applies to**</span></span>
- [<span data-ttu-id="4eaeb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4eaeb-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="4eaeb-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="4eaeb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)


<span data-ttu-id="4eaeb-107">この記事では、最新の認証と条件付きアクセスをサポートする組織の電子メール および電子メール クライアントを保護するために、推奨される ID およびデバイス アクセス ポリシーを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-107">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="4eaeb-108">このガイダンスは、共通 [ID](identity-access-policies.md) ポリシーとデバイス アクセス ポリシーに基に構築され、いくつかの推奨事項も含まれています。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-108">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="4eaeb-109">これらの推奨事項は、ニーズの粒度に基づいて適用できる 3 つの異なる層のセキュリティと保護に基づいており、ベースライン、機密、厳しく規制 **されています**。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-109">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="4eaeb-110">これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-110">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="4eaeb-111">これらの推奨事項では、ユーザーがモバイル デバイスで iOS および Android 用の Outlook を含む最新の電子メール クライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-111">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="4eaeb-112">iOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-112">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="4eaeb-113">これらのモバイル Outlook アプリは、モバイルの使用をサポートし、他の Microsoft クラウド セキュリティ機能と一緒に動作するセキュリティ機能を使用して設計されています。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-113">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="4eaeb-114">詳細については [、iOS および Android 用の Outlook に関する FAQ を参照してください](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-114">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="4eaeb-115">電子メールを含める一般的なポリシーを更新する</span><span class="sxs-lookup"><span data-stu-id="4eaeb-115">Update common policies to include email</span></span>

<span data-ttu-id="4eaeb-116">電子メールを保護するために、次の図は、共通 ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-116">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="4eaeb-117">[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新の概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="4eaeb-117">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="4eaeb-118">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="4eaeb-118">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="4eaeb-119">ActiveSync クライアントをブロックする Exchange Online の新しいポリシーの追加に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-119">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="4eaeb-120">これにより、Outlook モバイルの使用が強制的に行います。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-120">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="4eaeb-121">ポリシーのセットアップ時にポリシーのスコープに Exchange Online と Outlook を含める場合は、ActiveSync クライアントをブロックする新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-121">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="4eaeb-122">次の表に示すポリシーを確認し、推奨される追加を行うか、既に含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-122">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="4eaeb-123">各ポリシーは、共通 ID ポリシーとデバイス アクセス ポリシーに関連 [する構成手順にリンクします](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-123">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="4eaeb-124">保護レベル</span><span class="sxs-lookup"><span data-stu-id="4eaeb-124">Protection level</span></span>|<span data-ttu-id="4eaeb-125">Policies</span><span class="sxs-lookup"><span data-stu-id="4eaeb-125">Policies</span></span>|<span data-ttu-id="4eaeb-126">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4eaeb-126">More information</span></span>|
|---|---|---|
|<span data-ttu-id="4eaeb-127">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="4eaeb-127">**Baseline**</span></span>|[<span data-ttu-id="4eaeb-128">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="4eaeb-128">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="4eaeb-129">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="4eaeb-129">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="4eaeb-130">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="4eaeb-130">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="4eaeb-131">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="4eaeb-131">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="4eaeb-132">アプリ のデータ保護ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="4eaeb-132">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="4eaeb-133">Outlook がアプリの一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-133">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="4eaeb-134">各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-134">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
||[<span data-ttu-id="4eaeb-135">承認されたアプリとアプリの保護を要求する</span><span class="sxs-lookup"><span data-stu-id="4eaeb-135">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="4eaeb-136">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="4eaeb-136">Include Exchange Online in the list of cloud apps</span></span>|
||[<span data-ttu-id="4eaeb-137">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="4eaeb-137">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="4eaeb-138">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="4eaeb-138">Include Exchange Online in list of cloud apps</span></span>|
||[<span data-ttu-id="4eaeb-139">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="4eaeb-139">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="4eaeb-140">この新しいポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="4eaeb-140">Add this new policy</span></span>|
|<span data-ttu-id="4eaeb-141">**機密**</span><span class="sxs-lookup"><span data-stu-id="4eaeb-141">**Sensitive**</span></span>|[<span data-ttu-id="4eaeb-142">サインインリスクが低、中、高 *の* 場合 *に* MFA を要求 *する*</span><span class="sxs-lookup"><span data-stu-id="4eaeb-142">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="4eaeb-143">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="4eaeb-143">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="4eaeb-144">準拠した PC とモバイル *デバイスが* 必要</span><span class="sxs-lookup"><span data-stu-id="4eaeb-144">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="4eaeb-145">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="4eaeb-145">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="4eaeb-146">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="4eaeb-146">**Highly regulated**</span></span>|[<span data-ttu-id="4eaeb-147">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="4eaeb-147">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="4eaeb-148">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="4eaeb-148">Include Exchange Online in the assignment of cloud apps</span></span>|
|

## <a name="block-activesync-clients"></a><span data-ttu-id="4eaeb-149">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="4eaeb-149">Block ActiveSync clients</span></span>

<span data-ttu-id="4eaeb-150">このポリシーにより、ActiveSync クライアントは他の条件付きアクセス ポリシーをバイパスしません。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-150">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="4eaeb-151">ポリシー構成は ActiveSync クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-151">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="4eaeb-152">[アプリ保護ポリシーを \*\*[要求する] を選択](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)\*\* すると、このポリシーは ActiveSync クライアントをブロックします。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-152">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="4eaeb-153">このポリシーの作成に関する詳細については、「条件付きアクセスによるクラウド アプリ アクセスのアプリ保護ポリシーを要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-153">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="4eaeb-154">シナリオ [1: Office 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)アプリでは、基本認証を利用する Exchange ActiveSync クライアントが Exchange Online に接続することを防ぐ、アプリ保護ポリシーを持つ承認済みアプリが必要です。シナリオ 1 の「手順 2: ActiveSync (EAS) を使用して Exchange Online 用の Azure AD 条件付きアクセス ポリシーを構成する」に従います。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-154">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="4eaeb-155">また、認証ポリシーを使用して基本[](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)認証を無効にし、すべてのクライアント アクセス要求で最新の認証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-155">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="4eaeb-156">Outlook on the web からの Exchange Online へのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="4eaeb-156">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="4eaeb-157">ユーザーが Umaged デバイス上の Outlook on the web から添付ファイルをダウンロードする機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-157">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="4eaeb-158">これらのデバイスのユーザーは、デバイスにファイルをリークして保存することなく、Office Online を使用してこれらのファイルを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-158">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="4eaeb-159">管理されていないデバイスでユーザーに添付ファイルが表示されるのをブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-159">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="4eaeb-160">それらのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-160">Here are the steps:</span></span>

1. <span data-ttu-id="4eaeb-161">[Exchange Online リモート PowerShell セッションに接続します](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-161">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="4eaeb-162">OWA メールボックス ポリシーをまだ持ってない場合は [、New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して OWA メールボックス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-162">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="4eaeb-163">添付ファイルの表示を許可し、ダウンロードを許可する場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-163">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="4eaeb-164">添付ファイルをブロックする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-164">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. <span data-ttu-id="4eaeb-165">Azure portal で、次の設定を使用して新しい条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-165">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="4eaeb-166">**割り当て** \>**ユーザーとグループ**: 含める、または除外する適切なユーザーとグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-166">**Assignments** \> **Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="4eaeb-167">**割り当て** \>**クラウド アプリまたはアクション** \>**クラウド アプリ** \>**含める** \>**アプリの選択**: Office **365 Exchange Online を選択する**</span><span class="sxs-lookup"><span data-stu-id="4eaeb-167">**Assignments** \> **Cloud apps or actions** \> **Cloud apps** \> **Include** \> **Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="4eaeb-168">**アクセス制御** \>**セッション**: [アプリによって **適用される制限を使用する] を選択する**</span><span class="sxs-lookup"><span data-stu-id="4eaeb-168">**Access controls** \> **Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="4eaeb-169">iOS デバイスと Android デバイスで Outlook を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="4eaeb-169">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="4eaeb-170">iOS および Android デバイスのユーザーが、iOS および Android 用の Outlook を使用して仕事や学校のコンテンツにのみアクセスするには、それらの潜在的なユーザーを対象とする条件付きアクセス ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-170">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="4eaeb-171">このポリシーを構成する手順については、「iOS および Android 用の Outlook を使用してメッセージングコラボレーション アクセス [を管理する」を参照してください]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-171">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>

## <a name="set-up-message-encryption"></a><span data-ttu-id="4eaeb-172">メッセージの暗号化を設定する</span><span class="sxs-lookup"><span data-stu-id="4eaeb-172">Set up message encryption</span></span>

<span data-ttu-id="4eaeb-173">Azure Information Protection の保護機能を活用する新しい Office 365 Message Encryption (OME) 機能を使用すると、組織は保護された電子メールを任意のデバイスのすべてのユーザーと簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-173">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="4eaeb-174">ユーザーは、他の Microsoft 365 組織だけでなく、Outlook.com、Gmail、その他のメール サービスを使用して、保護されたメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-174">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="4eaeb-175">詳細については [、「Set up new Office 365 Message Encryption capabilities 」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-175">For more information, see [Set up new Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4eaeb-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="4eaeb-176">Next steps</span></span>

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="4eaeb-178">次の条件に合ったアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4eaeb-178">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="4eaeb-179">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4eaeb-179">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="4eaeb-180">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4eaeb-180">SharePoint</span></span>](sharepoint-file-access-policies.md)
