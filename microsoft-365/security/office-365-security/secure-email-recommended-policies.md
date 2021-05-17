---
title: セキュリティで保護された電子メール推奨ポリシー - エンタープライズ Microsoft 365の|Microsoft Docs
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
ms.openlocfilehash: c5f5837f4e4069a67bc080178fefd10bd2a08629
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599853"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="50b99-103">電子メールをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="50b99-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="50b99-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="50b99-104">**Applies to**</span></span>
- [<span data-ttu-id="50b99-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="50b99-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="50b99-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="50b99-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="50b99-107">この記事では、最新の認証と条件付きアクセスをサポートする組織の電子メール および電子メール クライアントを保護するために、推奨される ID およびデバイス アクセス ポリシーを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50b99-107">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="50b99-108">このガイダンスは、共通 [ID](identity-access-policies.md) とデバイス アクセス ポリシーに基いて作成され、さらにいくつかの推奨事項も含まれています。</span><span class="sxs-lookup"><span data-stu-id="50b99-108">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="50b99-109">これらの推奨事項は、ニーズの粒度に基づいて適用できる 3 つの異なるセキュリティ層と保護に基づいて行います。ベースライン、機密性の高い、高度に **規制されています**。</span><span class="sxs-lookup"><span data-stu-id="50b99-109">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="50b99-110">これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50b99-110">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="50b99-111">これらの推奨事項では、ユーザーがモバイル デバイス上の iOS および Android のOutlookなど、最新の電子メール クライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50b99-111">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="50b99-112">Outlook iOS と Android 用のアプリは、アプリの最適な機能をサポートOffice 365。</span><span class="sxs-lookup"><span data-stu-id="50b99-112">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="50b99-113">これらのモバイル Outlookアプリは、モバイルの使用をサポートし、他の Microsoft クラウド セキュリティ機能と共に動作するセキュリティ機能も備えた設計されています。</span><span class="sxs-lookup"><span data-stu-id="50b99-113">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="50b99-114">詳細については[、「iOS と Android Outlookに関するよく寄せられる質問」を参照してください](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。</span><span class="sxs-lookup"><span data-stu-id="50b99-114">For more information, see [Outlook for iOS and Android FAQ](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="50b99-115">電子メールを含める一般的なポリシーを更新する</span><span class="sxs-lookup"><span data-stu-id="50b99-115">Update common policies to include email</span></span>

<span data-ttu-id="50b99-116">電子メールを保護するために、次の図は、共通の ID およびデバイス アクセス ポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="50b99-116">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="50b99-117">[![サービスとその依存サービスへのアクセスを保護するためのTeamsの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="50b99-117">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

<span data-ttu-id="50b99-118">ActiveSync クライアントをブロックする新しいポリシー Exchange Onlineに注意してください。</span><span class="sxs-lookup"><span data-stu-id="50b99-118">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="50b99-119">これにより、モバイルでのOutlookされます。</span><span class="sxs-lookup"><span data-stu-id="50b99-119">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="50b99-120">ポリシーの設定時Exchange OnlineポリシーのOutlookをポリシーのスコープに含める場合は、ActiveSync クライアントをブロックする新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50b99-120">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="50b99-121">次の表に示すポリシーを確認し、推奨される追加を行うか、既に含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="50b99-121">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="50b99-122">各ポリシーは、共通 ID およびデバイス アクセス ポリシーの関連する [構成手順にリンクします](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="50b99-122">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="50b99-123">保護レベル</span><span class="sxs-lookup"><span data-stu-id="50b99-123">Protection level</span></span>|<span data-ttu-id="50b99-124">ポリシー</span><span class="sxs-lookup"><span data-stu-id="50b99-124">Policies</span></span>|<span data-ttu-id="50b99-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="50b99-125">More information</span></span>|
|---|---|---|
|<span data-ttu-id="50b99-126">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="50b99-126">**Baseline**</span></span>|[<span data-ttu-id="50b99-127">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="50b99-127">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="50b99-128">クラウド Exchange Online割り当てにアプリを含める</span><span class="sxs-lookup"><span data-stu-id="50b99-128">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="50b99-129">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="50b99-129">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="50b99-130">クラウド Exchange Online割り当てにアプリを含める</span><span class="sxs-lookup"><span data-stu-id="50b99-130">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="50b99-131">APP データ保護ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="50b99-131">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="50b99-132">アプリのOutlookに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="50b99-132">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="50b99-133">各プラットフォームのポリシーを必ず更新してください (iOS、Android、Windows)</span><span class="sxs-lookup"><span data-stu-id="50b99-133">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
||[<span data-ttu-id="50b99-134">承認済みアプリと APP 保護を要求する</span><span class="sxs-lookup"><span data-stu-id="50b99-134">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="50b99-135">クラウド Exchange Onlineリストにアプリを含める</span><span class="sxs-lookup"><span data-stu-id="50b99-135">Include Exchange Online in the list of cloud apps</span></span>|
||[<span data-ttu-id="50b99-136">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="50b99-136">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="50b99-137">クラウド Exchange Onlineリストにアプリを含める</span><span class="sxs-lookup"><span data-stu-id="50b99-137">Include Exchange Online in list of cloud apps</span></span>|
||[<span data-ttu-id="50b99-138">ActiveSync クライアントのブロック</span><span class="sxs-lookup"><span data-stu-id="50b99-138">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="50b99-139">この新しいポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="50b99-139">Add this new policy</span></span>|
|<span data-ttu-id="50b99-140">**機密**</span><span class="sxs-lookup"><span data-stu-id="50b99-140">**Sensitive**</span></span>|[<span data-ttu-id="50b99-141">サインイン リスクが低い、中程度、または高い場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="50b99-141">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="50b99-142">クラウド Exchange Online割り当てにアプリを含める</span><span class="sxs-lookup"><span data-stu-id="50b99-142">Include Exchange Online in the assignment of cloud apps</span></span>|
||[<span data-ttu-id="50b99-143">準拠している PC とモバイル *デバイスを* 要求する</span><span class="sxs-lookup"><span data-stu-id="50b99-143">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="50b99-144">クラウド Exchange Onlineリストにアプリを含める</span><span class="sxs-lookup"><span data-stu-id="50b99-144">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="50b99-145">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="50b99-145">**Highly regulated**</span></span>|[<span data-ttu-id="50b99-146">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="50b99-146">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="50b99-147">クラウド Exchange Online割り当てにアプリを含める</span><span class="sxs-lookup"><span data-stu-id="50b99-147">Include Exchange Online in the assignment of cloud apps</span></span>|
|

## <a name="block-activesync-clients"></a><span data-ttu-id="50b99-148">ActiveSync クライアントのブロック</span><span class="sxs-lookup"><span data-stu-id="50b99-148">Block ActiveSync clients</span></span>

<span data-ttu-id="50b99-149">このポリシーにより、ActiveSync クライアントは他の条件付きアクセス ポリシーをバイパスしません。</span><span class="sxs-lookup"><span data-stu-id="50b99-149">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="50b99-150">ポリシー構成は ActiveSync クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="50b99-150">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="50b99-151">[アプリ保護ポリシーを \*\*[要求する] を選択すると、ActiveSync](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)\*\* クライアントがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="50b99-151">By selecting **[Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="50b99-152">このポリシーの作成の詳細については、「条件付きアクセスを使用したクラウド アプリ アクセスのアプリ保護ポリシーを要求 [する」を参照してください](/azure/active-directory/conditional-access/app-protection-based-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="50b99-152">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="50b99-153">シナリオ[1: Office 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)アプリでは、基本認証を利用する Exchange ActiveSync クライアントが Exchange Online に接続することを防ぐ、アプリ保護ポリシーを持つ承認済みアプリが必要です。「手順 2: ActiveSync (EAS)を使用して Exchange Online 用の Azure AD 条件付きアクセス ポリシーを構成する」に従います。</span><span class="sxs-lookup"><span data-stu-id="50b99-153">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="50b99-154">また、認証ポリシーを使用して基本[](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)認証を無効にし、すべてのクライアント アクセス要求で最新の認証を使用できます。</span><span class="sxs-lookup"><span data-stu-id="50b99-154">You can also use authentication policies to [disable Basic authentication](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="50b99-155">Web 上のExchange OnlineからのOutlookアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="50b99-155">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="50b99-156">ユーザーが umnanaged デバイス上の web 上Outlookから添付ファイルをダウンロードする機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="50b99-156">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="50b99-157">これらのデバイス上のユーザーは、デバイスにファイルを漏洩して保存することなく、Office Online を使用してこれらのファイルを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="50b99-157">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="50b99-158">ユーザーが管理されていないデバイスで添付ファイルを見るのをブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="50b99-158">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="50b99-159">それらのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="50b99-159">Here are the steps:</span></span>

1. <span data-ttu-id="50b99-160">[Connect PowerShell セッションExchange Onlineにアクセスします](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="50b99-160">[Connect to an Exchange Online Remote PowerShell session](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="50b99-161">OWA メールボックス ポリシーをまだ持ってない場合は [、New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="50b99-161">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="50b99-162">添付ファイルの表示を許可するが、ダウンロードを許可する場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="50b99-162">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="50b99-163">添付ファイルをブロックする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="50b99-163">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. <span data-ttu-id="50b99-164">Azure portal で、次の設定を使用して新しい条件付きアクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="50b99-164">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="50b99-165">**割り当て** \>**ユーザーとグループ**: 含めるおよび除外する適切なユーザーとグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="50b99-165">**Assignments** \> **Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="50b99-166">**割り当て** \>**クラウド アプリまたはアクション** \>**クラウド アプリ** \>**Include** \>**アプリの選択**: [アプリの **選択Office 365 Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="50b99-166">**Assignments** \> **Cloud apps or actions** \> **Cloud apps** \> **Include** \> **Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="50b99-167">**アクセス制御** \>**セッション**: [アプリ **の適用制限を使用する] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="50b99-167">**Access controls** \> **Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="50b99-168">iOS デバイスと Android デバイスでデバイスを使用する必要Outlook</span><span class="sxs-lookup"><span data-stu-id="50b99-168">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="50b99-169">iOS および Android デバイスのユーザーが、Outlook for iOS および Android を使用して仕事または学校のコンテンツにのみアクセスするには、それらの潜在的なユーザーを対象とする条件付きアクセス ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="50b99-169">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="50b99-170">このポリシーを構成する手順については、「iOS および Android 用のメッセージング グループOutlookを使用して管理する[」を参照してください](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="50b99-170">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>

## <a name="set-up-message-encryption"></a><span data-ttu-id="50b99-171">メッセージの暗号化を設定する</span><span class="sxs-lookup"><span data-stu-id="50b99-171">Set up message encryption</span></span>

<span data-ttu-id="50b99-172">Azure Information Protection のOffice 365 Message Encryption機能を活用する新しい OME (OME) 機能を使用すると、組織は保護された電子メールを任意のデバイスの誰とでも簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="50b99-172">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="50b99-173">ユーザーは、Microsoft 365.com、Gmail、その Outlook他のメール サービスを使用して、他の組織や非顧客と保護されたメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="50b99-173">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="50b99-174">詳細については、「新しい機能をセットアップ[する」をOffice 365 Message Encryptionしてください](../../compliance/set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="50b99-174">For more information, see [Set up new Office 365 Message Encryption capabilities](../../compliance/set-up-new-message-encryption-capabilities.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="50b99-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="50b99-175">Next steps</span></span>

![手順 4: クラウド アプリMicrosoft 365ポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="50b99-177">次の条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="50b99-177">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="50b99-178">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50b99-178">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="50b99-179">SharePoint</span><span class="sxs-lookup"><span data-stu-id="50b99-179">SharePoint</span></span>](sharepoint-file-access-policies.md)
