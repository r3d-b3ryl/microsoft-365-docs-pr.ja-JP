---
title: セキュリティで保護された電子メールの推奨ポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c8a1609bed124789229c6ae6d1f80b7d9c70bb66
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646813"
---
# <a name="policy-recommendations-for-securing-email"></a><span data-ttu-id="fe748-103">電子メールをセキュリティで保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="fe748-103">Policy recommendations for securing email</span></span>

<span data-ttu-id="fe748-104">この記事では、推奨される id とデバイスアクセスポリシーを実装して、先進認証および条件付きアクセスをサポートする組織の電子メールと電子メールクライアントを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe748-104">This article describes how to implement the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and conditional access.</span></span> <span data-ttu-id="fe748-105">このガイダンスは、 [一般的な id とデバイスのアクセスポリシー](identity-access-policies.md) を基に作成されており、さらにいくつかの推奨事項も含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe748-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md) and also includes a few additional recommendations.</span></span>

<span data-ttu-id="fe748-106">これらの推奨事項は、ニーズの粒度 ( **基準**、 **機密**、 **高規制**) に基づいて適用できる、セキュリティと保護の3つの異なる層に基づいています。</span><span class="sxs-lookup"><span data-stu-id="fe748-106">These recommendations are based on three different tiers of security and protection that can be applied based on the granularity of your needs: **baseline**, **sensitive**, and **highly regulated**.</span></span> <span data-ttu-id="fe748-107">これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe748-107">You can learn more about these security tiers, and the recommended client operating systems, referenced by these recommendations in the [recommended security policies and configurations introduction](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="fe748-108">これらの推奨事項では、ユーザーがモバイルデバイスの iOS および Android 用の Outlook を含むモダンメールクライアントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe748-108">These recommendations require your users to use modern email clients, including Outlook for iOS and Android on mobile devices.</span></span> <span data-ttu-id="fe748-109">IOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="fe748-109">Outlook for iOS and Android provide support for the best features of Office 365.</span></span> <span data-ttu-id="fe748-110">これらのモバイル Outlook アプリは、モバイル使用をサポートし、他の Microsoft クラウドセキュリティ機能と連携するセキュリティ機能を備えた設計も行われています。</span><span class="sxs-lookup"><span data-stu-id="fe748-110">These mobile Outlook apps are also architected with security capabilities that support mobile use and work together with other Microsoft cloud security capabilities.</span></span> <span data-ttu-id="fe748-111">詳細については、「 [iOS および Android 用の OUTLOOK FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe748-111">For more information, see [Outlook for iOS and Android FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).</span></span>

## <a name="update-common-policies-to-include-email"></a><span data-ttu-id="fe748-112">一般的なポリシーを更新して電子メールを含める</span><span class="sxs-lookup"><span data-stu-id="fe748-112">Update common policies to include email</span></span>

<span data-ttu-id="fe748-113">電子メールを保護するために、次の図は、共通 id およびデバイスアクセスポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="fe748-113">To protect email, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span>

<span data-ttu-id="fe748-114">[![Teams およびその依存サービスへのアクセスを保護するためのポリシー更新の概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span><span class="sxs-lookup"><span data-stu-id="fe748-114">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)</span></span>

[<span data-ttu-id="fe748-115">この画像のより大きいバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="fe748-115">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

<span data-ttu-id="fe748-116">Exchange Online の新しいポリシーを追加して、ActiveSync クライアントをブロックすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fe748-116">Note the addition of a new policy for Exchange Online to block ActiveSync clients.</span></span> <span data-ttu-id="fe748-117">これにより、Outlook mobile が強制的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe748-117">This forces the use of Outlook mobile.</span></span>

<span data-ttu-id="fe748-118">ポリシーの設定時に Exchange Online と Outlook がポリシーのスコープに含まれていた場合は、ActiveSync クライアントをブロックするために新しいポリシーを作成するだけでよいことになります。</span><span class="sxs-lookup"><span data-stu-id="fe748-118">If you included Exchange Online and Outlook in the scope of the policies when you set them up, you only need to create the new policy to block ActiveSync clients.</span></span> <span data-ttu-id="fe748-119">次の表に記載されているポリシーを確認し、推奨される追加を行うか、またはこれらが既に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe748-119">Review the policies listed in the following table and either make the recommended additions, or confirm that these are already included.</span></span> <span data-ttu-id="fe748-120">各ポリシーは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)の関連する構成手順にリンクします。</span><span class="sxs-lookup"><span data-stu-id="fe748-120">Each policy links to the associated configuration instructions in [Common identity and device access policies](identity-access-policies.md).</span></span>

|<span data-ttu-id="fe748-121">保護レベル</span><span class="sxs-lookup"><span data-stu-id="fe748-121">Protection level</span></span>|<span data-ttu-id="fe748-122">Policies</span><span class="sxs-lookup"><span data-stu-id="fe748-122">Policies</span></span>|<span data-ttu-id="fe748-123">詳細</span><span class="sxs-lookup"><span data-stu-id="fe748-123">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="fe748-124">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="fe748-124">**Baseline**</span></span>|[<span data-ttu-id="fe748-125">サインインリスクが*中*または*高*の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="fe748-125">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="fe748-126">クラウドアプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="fe748-126">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="fe748-127">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="fe748-127">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="fe748-128">クラウドアプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="fe748-128">Include Exchange Online in the assignment of cloud apps</span></span>|
|        |[<span data-ttu-id="fe748-129">アプリデータ保護ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="fe748-129">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="fe748-130">Outlook がアプリの一覧に含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fe748-130">Be sure Outlook is included in the list of apps.</span></span> <span data-ttu-id="fe748-131">各プラットフォーム (iOS、Android、Windows) のポリシーを更新してください。</span><span class="sxs-lookup"><span data-stu-id="fe748-131">Be sure to update the policy for each platform (iOS, Android, Windows)</span></span>|
|        |[<span data-ttu-id="fe748-132">承認済みアプリとアプリ保護を必要とする</span><span class="sxs-lookup"><span data-stu-id="fe748-132">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="fe748-133">クラウドアプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="fe748-133">Include Exchange Online in the list of cloud apps</span></span>|
|        |[<span data-ttu-id="fe748-134">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="fe748-134">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="fe748-135">クラウドアプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="fe748-135">Include Exchange Online in list of cloud apps</span></span>|
|        |[<span data-ttu-id="fe748-136">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="fe748-136">Block ActiveSync clients</span></span>](#block-activesync-clients)|<span data-ttu-id="fe748-137">この新しいポリシーを追加する</span><span class="sxs-lookup"><span data-stu-id="fe748-137">Add this new policy</span></span>| 
|<span data-ttu-id="fe748-138">**機密**</span><span class="sxs-lookup"><span data-stu-id="fe748-138">**Sensitive**</span></span>|[<span data-ttu-id="fe748-139">サインインリスクが*低*、*中*、*高*のときに MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="fe748-139">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| <span data-ttu-id="fe748-140">クラウドアプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="fe748-140">Include Exchange Online in the assignment of cloud apps</span></span>|
|         |[<span data-ttu-id="fe748-141">準拠 *して* いる pc とモバイルデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="fe748-141">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="fe748-142">クラウドアプリの一覧に Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="fe748-142">Include Exchange Online in the list of cloud apps</span></span>|
|<span data-ttu-id="fe748-143">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="fe748-143">**Highly regulated**</span></span>|[<span data-ttu-id="fe748-144">*常に* MFA が必要</span><span class="sxs-lookup"><span data-stu-id="fe748-144">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="fe748-145">クラウドアプリの割り当てに Exchange Online を含める</span><span class="sxs-lookup"><span data-stu-id="fe748-145">Include Exchange Online in the assignment of cloud apps</span></span>|

## <a name="block-activesync-clients"></a><span data-ttu-id="fe748-146">ActiveSync クライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="fe748-146">Block ActiveSync clients</span></span>

<span data-ttu-id="fe748-147">このポリシーでは、ActiveSync クライアントが他の条件付きアクセスポリシーをバイパスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="fe748-147">This policy prevents ActiveSync clients from bypassing other Conditional Access policies.</span></span> <span data-ttu-id="fe748-148">ポリシー構成は、ActiveSync クライアントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fe748-148">The policy configuration applies only to ActiveSync clients.</span></span> <span data-ttu-id="fe748-149">[ **[アプリ保護ポリシーを必須](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** にする] を選択すると、このポリシーによって ActiveSync クライアントがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="fe748-149">By selecting **[Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, this policy blocks ActiveSync clients.</span></span> <span data-ttu-id="fe748-150">このポリシーの作成の詳細については、「 [条件付きアクセスでのクラウドアプリケーションへのアクセスにアプリ保護ポリシーが必要](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe748-150">Details on creating this policy can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).</span></span>

- <span data-ttu-id="fe748-151">「 [シナリオ 1: Office 365 アプリは、アプリ保護ポリシーを使用して承認済みアプリを必要](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)とする」の「手順 2: exchange Online の Azure AD 条件付きアクセスポリシーを構成する」を参照してください。これにより、exchange ActiveSync クライアントは、基本認証を活用して exchange online に接続することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="fe748-151">Follow "Step 2: Configure an Azure AD Conditional Access policy for Exchange Online with ActiveSync (EAS)" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.</span></span>

<span data-ttu-id="fe748-152">認証ポリシーを使用して [基本認証を無効](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)にすることもできます。これにより、すべてのクライアントアクセス要求で先進認証を使用することが強制されます。</span><span class="sxs-lookup"><span data-stu-id="fe748-152">You can also use authentication policies to [disable Basic authentication](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), which forces all client access requests to use modern authentication.</span></span>

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a><span data-ttu-id="fe748-153">Web 上の Outlook から Exchange Online へのアクセスを制限する</span><span class="sxs-lookup"><span data-stu-id="fe748-153">Limit access to Exchange Online from Outlook on the web</span></span>

<span data-ttu-id="fe748-154">ユーザーが umnanaged デバイス上の Outlook on the web から添付ファイルをダウンロードする機能を制限できます。</span><span class="sxs-lookup"><span data-stu-id="fe748-154">You can restrict the ability for users to download attachments from Outlook on the web on umnanaged devices.</span></span> <span data-ttu-id="fe748-155">これらのデバイスのユーザーは、ファイルをリークしてデバイスに格納することなく、Office Online を使用してこれらのファイルを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="fe748-155">Users on these devices can view and edit these files using Office Online without leaking and storing the files on the device.</span></span> <span data-ttu-id="fe748-156">また、ユーザーが管理されていないデバイスで添付ファイルを表示することを禁止することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe748-156">You can also block users from seeing attachments on an unmanaged device.</span></span>

<span data-ttu-id="fe748-157">それらのステップは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe748-157">Here are the steps:</span></span>

1. <span data-ttu-id="fe748-158">[Exchange Online リモート PowerShell セッションに接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="fe748-158">[Connect to an Exchange Online Remote PowerShell session](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="fe748-159">OWA メールボックスポリシーをまだ持っていない場合は、 [新しい-Owam/boxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="fe748-159">If you don't already have an OWA mailbox policy, create one with the [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) cmdlet.</span></span>
3. <span data-ttu-id="fe748-160">添付ファイルの表示を許可するが、ダウンロードしない場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe748-160">If you want to allow viewing of attachments but no downloading, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. <span data-ttu-id="fe748-161">添付ファイルをブロックする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe748-161">If you want to block attachments, use this command:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

4. <span data-ttu-id="fe748-162">Azure ポータルで、次の設定を使用して新しい条件付きアクセスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe748-162">In the Azure portal, create a new Conditional Access policy with these settings:</span></span>

   <span data-ttu-id="fe748-163">**割り当て > ユーザーとグループ**: 該当するユーザーとグループを選択して、含めるか除外します。</span><span class="sxs-lookup"><span data-stu-id="fe748-163">**Assignments > Users and groups**: Select appropriate users and groups to include and exclude.</span></span>

   <span data-ttu-id="fe748-164">クラウドアプリ**または > アクション > クラウドアプリまたはアクションを含む割り当て。アプリの選択 > >** を選択してください。 **Office 365 Exchange Online**を選択する</span><span class="sxs-lookup"><span data-stu-id="fe748-164">**Assignments > Cloud apps or actions > Cloud apps > Include > Select apps**: Select **Office 365 Exchange Online**</span></span>

   <span data-ttu-id="fe748-165">**Access controls > Session**: **Use app 強制制限**の選択</span><span class="sxs-lookup"><span data-stu-id="fe748-165">**Access controls > Session**: Select **Use app enforced restrictions**</span></span>

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a><span data-ttu-id="fe748-166">IOS および Android デバイスで Outlook を使用する必要があることを要求する</span><span class="sxs-lookup"><span data-stu-id="fe748-166">Require that iOS and Android devices must use Outlook</span></span>

<span data-ttu-id="fe748-167">IOS および Android デバイスのユーザーが、iOS および Android 用の Outlook を使用して、職場または学校のコンテンツにのみアクセスできるようにするには、それらの可能性のあるユーザーを対象とする条件付きアクセスポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="fe748-167">To ensure that users of iOS and Android devices can only access work or school content using Outlook for iOS and Android, you need a Conditional Access policy that targets those potential users.</span></span>

<span data-ttu-id="fe748-168">このポリシーを構成する手順については、「 [iOS および Android 用の Outlook を使用して、メッセージのグループ作業アクセスを管理]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe748-168">See the steps to configure this policy in [Manage messaging collaboration access by using Outlook for iOS and Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).</span></span>


## <a name="set-up-message-encryption"></a><span data-ttu-id="fe748-169">メッセージの暗号化をセットアップする</span><span class="sxs-lookup"><span data-stu-id="fe748-169">Set up message encryption</span></span>

<span data-ttu-id="fe748-170">新しい Office 365 Message Encryption (OME) 機能を使用すると、Azure Information Protection の保護機能を活用できるため、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="fe748-170">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device.</span></span> <span data-ttu-id="fe748-171">ユーザーは、保護されたメッセージを他の Microsoft 365 組織や、Outlook.com、Gmail、その他の電子メールサービスを使用しないお客様との間で送受信することができます。</span><span class="sxs-lookup"><span data-stu-id="fe748-171">Users can send and receive protected messages with other Microsoft 365 organizations as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="fe748-172">詳細については、「 [Office の新しい365メッセージ暗号化機能をセットアップ](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe748-172">For more information, see [Set up new Office 365 Message Encryption capabilities](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe748-173">次の手順</span><span class="sxs-lookup"><span data-stu-id="fe748-173">Next steps</span></span>

![手順 4: Microsoft 365 クラウドアプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="fe748-175">次の条件付きアクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="fe748-175">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="fe748-176">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe748-176">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="fe748-177">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe748-177">SharePoint</span></span>](sharepoint-file-access-policies.md)
