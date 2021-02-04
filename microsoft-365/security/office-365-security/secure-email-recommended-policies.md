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
ms.openlocfilehash: 261c375aa17e4a3bc8f7d1b469d82621cf4ae45b
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097130"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="a26d2-103">電子メールをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="a26d2-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="a26d2-104">この記事では、最新の認証と条件付きアクセスをサポートする組織の電子メール および電子メール クライアントを保護するために、推奨される ID およびデバイス アクセス ポリシーを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="a26d2-105">このガイダンスは、共通 [ID](identity-access-policies.md) ポリシーとデバイス アクセス ポリシーに基じ、さらにいくつかの推奨事項も示します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="a26d2-106">これらの推奨事項は、ニーズの粒度に基づいて適用できる 3 つの異なる層のセキュリティと保護に基づいており、ベースライン、機密、厳しく規制 **されています**。</span><span class="sxs-lookup"><span data-stu-id="a26d2-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="a26d2-107">これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a26d2-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="a26d2-108">これらの推奨事項では、ユーザーがモバイル デバイスで iOS および Android 用の Outlook を含む最新の電子メール クライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a26d2-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="a26d2-109">iOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a26d2-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="a26d2-110">これらのモバイル Outlook アプリは、モバイルの使用をサポートし、他の Microsoft クラウド セキュリティ機能と一緒に動作するセキュリティ機能を使用して設計されています。</span><span class="sxs-lookup"><span data-stu-id="a26d2-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="a26d2-111">詳細については [、iOS および Android 用の Outlook に関する FAQ を参照してください](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="a26d2-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="a26d2-112">電子メールを含める一般的なポリシーを更新する</span><span class="sxs-lookup"><span data-stu-id="a26d2-112">Update common policies to include email</span></span>

<span data-ttu-id="a26d2-113">電子メールを保護するために、次の図は、共通 ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="a26d2-113">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="a26d2-114">[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="a26d2-114">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="a26d2-115">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="a26d2-115">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="a26d2-116">ActiveSync クライアントをブロックする Exchange Online の新しいポリシーの追加に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a26d2-116">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="a26d2-117">これにより、Outlook モバイルが強制的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a26d2-117">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="a26d2-118">ポリシーのセットアップ時にポリシーのスコープに Exchange Online と Outlook を含める場合は、ActiveSync クライアントをブロックする新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a26d2-118">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="a26d2-119">次の表に示すポリシーを確認し、推奨される追加を行うか、既に含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-119">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="a26d2-120">各ポリシーは、共通 ID ポリシーとデバイス アクセス ポリシーに関連 [する構成手順にリンクします](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a26d2-120">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="a26d2-121">保護レベル</span><span class="sxs-lookup"><span data-stu-id="a26d2-121">Protection level</span></span>|<span data-ttu-id="a26d2-122">Policies</span><span class="sxs-lookup"><span data-stu-id="a26d2-122">Policies</span></span>|<span data-ttu-id="a26d2-123">詳細</span><span class="sxs-lookup"><span data-stu-id="a26d2-123">More information</span></span>|
|---|---|---|
|<span data-ttu-id="a26d2-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="a26d2-124">**Baseline**</span></span>|[<span data-ttu-id="a26d2-125">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="a26d2-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a26d2-126">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="a26d2-126">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="a26d2-127">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="a26d2-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="a26d2-128">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="a26d2-128">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="a26d2-129">アプリ のデータ保護ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="a26d2-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="a26d2-130">Outlook がアプリの一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a26d2-130">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="a26d2-131">各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。</span><span class="sxs-lookup"><span data-stu-id="a26d2-131">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
||[<span data-ttu-id="a26d2-132">承認されたアプリとアプリの保護を要求する</span><span class="sxs-lookup"><span data-stu-id="a26d2-132">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="a26d2-133">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="a26d2-133">Include Exchange Online in the list of cloud apps</span></span>|
||[<span data-ttu-id="a26d2-134">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="a26d2-134">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="a26d2-135">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="a26d2-135">Include Exchange Online in list of cloud apps</span></span>|
||[<span data-ttu-id="a26d2-136">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="a26d2-136">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="a26d2-137">この新しいポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="a26d2-137">Add this new policy</span></span>|
|<span data-ttu-id="a26d2-138">**機密**</span><span class="sxs-lookup"><span data-stu-id="a26d2-138">**Sensitive**</span></span>|[<span data-ttu-id="a26d2-139">サインインリスクが低、中、高 *の* 場合 *に* MFA を要求 *する*</span><span class="sxs-lookup"><span data-stu-id="a26d2-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a26d2-140">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="a26d2-140">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="a26d2-141">準拠した PC とモバイル *デバイスが* 必要</span><span class="sxs-lookup"><span data-stu-id="a26d2-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="a26d2-142">クラウド アプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="a26d2-142">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="a26d2-143">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="a26d2-143">**Highly regulated**</span></span>|[<span data-ttu-id="a26d2-144">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="a26d2-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a26d2-145">クラウド アプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="a26d2-145">Include Exchange Online in the assignment of cloud apps</span></span>|
|

## <a name="block-activesync-clients"></a><span data-ttu-id="a26d2-146">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="a26d2-146">Block ActiveSync clients</span></span>

<span data-ttu-id="a26d2-147">このポリシーにより、ActiveSync クライアントは他の条件付きアクセス ポリシーをバイパスしません。</span><span class="sxs-lookup"><span data-stu-id="a26d2-147">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="a26d2-148">ポリシー構成は ActiveSync クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a26d2-148">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="a26d2-149">[アプリ保護ポリシーを \*\*[要求する] を選択](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)\*\* すると、このポリシーは ActiveSync クライアントをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a26d2-149">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="a26d2-150">このポリシーの作成に関する詳細については、「条件付きアクセスによるクラウド アプリ アクセスのアプリ保護ポリシーを要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="a26d2-150">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="a26d2-151">シナリオ [1: Office 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)アプリでは、基本認証を利用する Exchange ActiveSync クライアントが Exchange Online に接続することを防ぐ、アプリ保護ポリシーを持つ承認されたアプリが必要です。シナリオ 1 の「手順 2: ActiveSync (EAS) を使用して Exchange Online 用の Azure AD 条件付きアクセス ポリシーを構成する」に従います。</span><span class="sxs-lookup"><span data-stu-id="a26d2-151">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="a26d2-152">また、認証ポリシーを使用して基本[](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)認証を無効にし、すべてのクライアント アクセス要求で最新の認証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a26d2-152">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="a26d2-153">Outlook on the web からの Exchange Online へのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="a26d2-153">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="a26d2-154">ユーザーが Umaged デバイス上の Outlook on the web から添付ファイルをダウンロードする機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="a26d2-154">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="a26d2-155">これらのデバイス上のユーザーは、デバイスにファイルをリークして保存することなく、Office Online を使用してこれらのファイルを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="a26d2-155">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="a26d2-156">管理されていないデバイスでユーザーに添付ファイルが表示されるのをブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a26d2-156">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="a26d2-157">それらのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a26d2-157">Here are the steps:</span></span>

1. <span data-ttu-id="a26d2-158">[Exchange Online リモート PowerShell セッションに接続します](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a26d2-158">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="a26d2-159">OWA メールボックス ポリシーをまだ持ってない場合は [、New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して OWA メールボックス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-159">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="a26d2-160">添付ファイルの表示を許可し、ダウンロードを許可する場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-160">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="a26d2-161">添付ファイルをブロックする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-161">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. <span data-ttu-id="a26d2-162">Azure portal で、次の設定を使用して新しい条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-162">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="a26d2-163">**割り当て** \>**ユーザーとグループ**: 含める、または除外する適切なユーザーとグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-163">**Assignments** \> **Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="a26d2-164">**割り当て** \>**クラウド アプリまたはアクション** \>**クラウド アプリ** \>**含める** \>**アプリの選択**: Office **365 Exchange Online を選択する**</span><span class="sxs-lookup"><span data-stu-id="a26d2-164">**Assignments** \> **Cloud apps or actions** \> **Cloud apps** \> **Include** \> **Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="a26d2-165">**アクセス制御** \>**セッション**: [アプリによって **適用される制限を使用する] を選択する**</span><span class="sxs-lookup"><span data-stu-id="a26d2-165">**Access controls** \> **Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="a26d2-166">iOS デバイスと Android デバイスで Outlook を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="a26d2-166">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="a26d2-167">iOS および Android デバイスのユーザーが、iOS および Android 用の Outlook を使用して仕事や学校のコンテンツにのみアクセスするには、それらの潜在的なユーザーを対象とする条件付きアクセス ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a26d2-167">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="a26d2-168">このポリシーを構成する手順については、「iOS および Android 用の Outlook を使用してメッセージングコラボレーション アクセス [を管理する」を参照してください]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="a26d2-168">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>

## <a name="set-up-message-encryption"></a><span data-ttu-id="a26d2-169">メッセージの暗号化を設定する</span><span class="sxs-lookup"><span data-stu-id="a26d2-169">Set up message encryption</span></span>

<span data-ttu-id="a26d2-170">Azure Information Protection の保護機能を活用する新しい Office 365 Message Encryption (OME) 機能を使用すると、組織は保護された電子メールを任意のデバイスのすべてのユーザーと簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="a26d2-170">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="a26d2-171">ユーザーは、他の Microsoft 365 組織だけでなく、Outlook.com、Gmail、その他のメール サービスを使用して、保護されたメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="a26d2-171">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="a26d2-172">詳細については [、「Set up new Office 365 Message Encryption capabilities 」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="a26d2-172">For more information, see [Set up new Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a26d2-173">次の手順</span><span class="sxs-lookup"><span data-stu-id="a26d2-173">Next steps</span></span>

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="a26d2-175">次の条件に合ったアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a26d2-175">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="a26d2-176">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a26d2-176">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="a26d2-177">SharePoint</span><span class="sxs-lookup"><span data-stu-id="a26d2-177">SharePoint</span></span>](sharepoint-file-access-policies.md)
