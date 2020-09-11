---
title: 基本的なモビリティとセキュリティの機能
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティは、モバイルデバイスをセキュリティで保護し、管理するのに役立ちます。
ms.openlocfilehash: a88afd539209d20046a778f8c6d16cadd51b5a9a
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430241"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="14750-103">基本的なモビリティとセキュリティの機能</span><span class="sxs-lookup"><span data-stu-id="14750-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="14750-104">基本的なモビリティとセキュリティは、組織内のライセンスである Microsoft 365 ユーザーが使用する iPhones、Ipad、Androids、Windows Phone などのモバイルデバイスをセキュリティで保護し、管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14750-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="14750-105">サポートされているモバイルデバイスおよびアプリについて、組織の Microsoft 365 電子メールおよびドキュメントへのアクセスを制御するのに役立つ設定を使用して、モバイルデバイス管理ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="14750-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="14750-106">デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。</span><span class="sxs-lookup"><span data-stu-id="14750-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="14750-107">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="14750-107">Supported devices</span></span>

<span data-ttu-id="14750-108">基本的なモビリティとセキュリティを使用して、以下のデバイスをセキュリティで保護し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="14750-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="14750-109">iOS 11.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="14750-109">iOS 11.0 or later versions</span></span>
    
- <span data-ttu-id="14750-110">Android 5.0 以降のバージョン<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="14750-110">Android 5.0 or later versions<sup>3</sup></span></span>
    
- <span data-ttu-id="14750-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="14750-111">Windows 8.1<sup>1</sup></span></span>
    
- <span data-ttu-id="14750-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="14750-112">Windows 8.1 RT<sup>1</sup></span></span>
    
- <span data-ttu-id="14750-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="14750-113">Windows 10<sup>2</sup></span></span>
    
- <span data-ttu-id="14750-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="14750-114">Windows 10 Mobile<sup>2</sup></span></span>   

<span data-ttu-id="14750-115"><sup>1</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。</span><span class="sxs-lookup"><span data-stu-id="14750-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="14750-116"><sup>2</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。</span><span class="sxs-lookup"><span data-stu-id="14750-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="14750-117">Windows 10 のアクセス制御には、Azure AD Premium を含むサブスクリプションが必要です。また、デバイスを Azure Active Directory に参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14750-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="14750-118"><sup>3</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。</span><span class="sxs-lookup"><span data-stu-id="14750-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="14750-119">2020年6月以降、2010バージョン9より後のバージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。</span><span class="sxs-lookup"><span data-stu-id="14750-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="14750-120">以前のバージョンの OS で既に登録されているデバイスは、機能は予告なしに変更されることがありますが、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="14750-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="14750-121">組織内のユーザーが基本的なモビリティとセキュリティでサポートされていないモバイルデバイスを使用している場合、組織のデータのセキュリティを強化するために、これらのデバイスの Microsoft 365 電子メールへの Exchange ActiveSync アプリのアクセスをブロックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14750-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="14750-122">Exchange ActiveSync をブロックする手順については、「 [基本的なモビリティとセキュリティでデバイスアクセス設定を管理](manage-device-access-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14750-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="14750-123">Microsoft 365 メールとドキュメントのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="14750-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="14750-124">次の表に示すさまざまな種類のモバイルデバイス用にサポートされているアプリは、ユーザーのデバイスに適用され、ユーザーが以前にデバイスを登録していない新しいモバイルデバイス管理ポリシーがある場合に、基本的なモビリティとセキュリティに登録するようにユーザーに促します。</span><span class="sxs-lookup"><span data-stu-id="14750-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="14750-125">ユーザーのデバイスがポリシーに準拠していない場合、ポリシーの設定方法によっては、ユーザーがこれらのアプリで Microsoft 365 リソースへのアクセスをブロックされたり、Microsoft 365 がポリシー違反を報告したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="14750-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="14750-126">**製品**</span><span class="sxs-lookup"><span data-stu-id="14750-126">**Product**</span></span>|<span data-ttu-id="14750-127">**iOS 10.0 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="14750-128">**Android 5.0 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="14750-129">**Exchange** Exchange ActiveSync には、Exchange ActiveSync バージョン14.1 以降を使用する、組み込みの電子メールとサードパーティ製のアプリ (接地など) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="14750-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="14750-130">メール</span><span class="sxs-lookup"><span data-stu-id="14750-130">Mail</span></span> |<span data-ttu-id="14750-131">メール</span><span class="sxs-lookup"><span data-stu-id="14750-131">Email</span></span> |
|<span data-ttu-id="14750-132">**Office**  および **OneDrive For business**</span><span class="sxs-lookup"><span data-stu-id="14750-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="14750-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="14750-133">Outlook</span></span> </br><span data-ttu-id="14750-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="14750-134">OneDrive</span></span> </br><span data-ttu-id="14750-135">Word</span><span class="sxs-lookup"><span data-stu-id="14750-135">Word</span></span> </br><span data-ttu-id="14750-136">Excel</span><span class="sxs-lookup"><span data-stu-id="14750-136">Excel</span></span> </br><span data-ttu-id="14750-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="14750-137">PowerPoint</span></span>|<span data-ttu-id="14750-138">**電話とタブレットの**場合:</span><span class="sxs-lookup"><span data-stu-id="14750-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="14750-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="14750-139">Outlook</span></span> <br/> <span data-ttu-id="14750-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="14750-140">OneDrive</span></span> <br/> <span data-ttu-id="14750-141">Word</span><span class="sxs-lookup"><span data-stu-id="14750-141">Word</span></span> <br/> <span data-ttu-id="14750-142">Excel</span><span class="sxs-lookup"><span data-stu-id="14750-142">Excel</span></span> <br/> <span data-ttu-id="14750-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="14750-143">PowerPoint</span></span> <br/> <span data-ttu-id="14750-144">**電話のみ:**</span><span class="sxs-lookup"><span data-stu-id="14750-144">**On phones only:**</span></span> <br/> <span data-ttu-id="14750-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="14750-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="14750-146">IOS 10.0 以降のバージョンのサポートには、iPhone と iPad デバイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="14750-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="14750-147">Microsoft 365 のモバイルデバイス管理では、BlackBerry OS デバイスの管理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="14750-147">Management of BlackBerry OS devices isn’t supported by Mobile Device Management for Microsoft 365.</span></span> <span data-ttu-id="14750-148">Blackberry のビジネスクラウドサービス (BBCS) を blackberry で使用して BlackBerry OS デバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="14750-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="14750-149">Android OS を実行している Blackberry デバイスは標準の Android デバイスとしてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14750-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="14750-150">ユーザーがモバイルブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online 内のドキュメント、または Outlook Web App 内の電子メールにアクセスした場合、登録を求めるメッセージは表示されず、ブロックされたり、ポリシー違反が報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="14750-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>
    
<span data-ttu-id="14750-151">次の図は、新しいデバイスを使用しているユーザーが、基本的なモビリティとセキュリティでアクセス制御をサポートするアプリにサインインしたときの動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="14750-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="14750-152">ユーザーは、デバイスを登録するまで、アプリで Microsoft 365 リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="14750-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティおよびセキュリティアクセス制御":::

<span data-ttu-id="14750-154">注: Microsoft 365 Business Standard 用 MDM で作成されるポリシーとアクセスルールは、exchange ActiveSync モバイルデバイスメールボックスポリシーと、Exchange 管理センターで作成されたデバイスアクセスルールより優先されます。</span><span class="sxs-lookup"><span data-stu-id="14750-154">Note:Policies and access rules created in MDM for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="14750-155">Microsoft 365 Business Standard の MDM にデバイスを登録した後、デバイスに適用された Exchange ActiveSync モバイルデバイスメールボックスポリシーまたはデバイスアクセスルールは無視されます。</span><span class="sxs-lookup"><span data-stu-id="14750-155">After a device is enrolled in MDM for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="14750-156">Exchange ActiveSync の詳細については、「exchange [activesync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14750-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="14750-157">モバイル デバイス用のポリシー設定</span><span class="sxs-lookup"><span data-stu-id="14750-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="14750-158">特定の設定を有効にしてアクセスをブロックするポリシーを作成した場合、 [microsoft 365 の電子メールとドキュメントのアクセス制御](capabilities.md)に記載されているサポートされているアプリを使用すると、ユーザーは microsoft 365 リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="14750-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="14750-159">ユーザーが Microsoft 365 リソースにアクセスできないようにする設定については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14750-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="14750-160">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="14750-160">Security</span></span>
    
- <span data-ttu-id="14750-161">暗号化</span><span class="sxs-lookup"><span data-stu-id="14750-161">Encryption</span></span>
    
- <span data-ttu-id="14750-162">脱獄</span><span class="sxs-lookup"><span data-stu-id="14750-162">Jail broken</span></span>
    
- <span data-ttu-id="14750-163">管理された電子メール プロファイル</span><span class="sxs-lookup"><span data-stu-id="14750-163">Managed email profile</span></span>  

<span data-ttu-id="14750-164">例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="14750-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="14750-165">ユーザーは、基本的なモビリティとセキュリティでアクセス制御をサポートするアプリにサインインします。</span><span class="sxs-lookup"><span data-stu-id="14750-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="14750-166">デバイスがセキュリティ設定に準拠するまで、アプリ内の Microsoft 365 リソースへのアクセスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="14750-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本的なモビリティおよびセキュリティコンプライアンスメッセージ":::

<span data-ttu-id="14750-168">次のセクションでは、Microsoft 365 組織のリソースに接続するモバイルデバイスをセキュリティで保護し、管理するために使用できるポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="14750-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="14750-169">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="14750-169">Security settings</span></span>

|<span data-ttu-id="14750-170">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-170">**Setting name**</span></span>|<span data-ttu-id="14750-171">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-172">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-172">**Android 5 and later**</span></span>|<span data-ttu-id="14750-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="14750-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14750-174">パスワードを要求</span><span class="sxs-lookup"><span data-stu-id="14750-174">Require a password</span></span>|<span data-ttu-id="14750-175">はい</span><span class="sxs-lookup"><span data-stu-id="14750-175">Yes</span></span>|<span data-ttu-id="14750-176">はい</span><span class="sxs-lookup"><span data-stu-id="14750-176">Yes</span></span>|<span data-ttu-id="14750-177">はい</span><span class="sxs-lookup"><span data-stu-id="14750-177">Yes</span></span>|
|<span data-ttu-id="14750-178">シンプルなパスワードを禁止</span><span class="sxs-lookup"><span data-stu-id="14750-178">Prevent simple password</span></span>|<span data-ttu-id="14750-179">必要</span><span class="sxs-lookup"><span data-stu-id="14750-179">Yes</span></span>|<span data-ttu-id="14750-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-180">No</span></span>|<span data-ttu-id="14750-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-181">No</span></span>|
|<span data-ttu-id="14750-182">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="14750-182">Require an alphanumeric password</span></span>|<span data-ttu-id="14750-183">必要</span><span class="sxs-lookup"><span data-stu-id="14750-183">Yes</span></span>|<span data-ttu-id="14750-184">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-184">No</span></span>|<span data-ttu-id="14750-185">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-185">No</span></span>|
|<span data-ttu-id="14750-186">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="14750-186">Minimum password length</span></span> |<span data-ttu-id="14750-187">はい</span><span class="sxs-lookup"><span data-stu-id="14750-187">Yes</span></span>|<span data-ttu-id="14750-188">はい</span><span class="sxs-lookup"><span data-stu-id="14750-188">Yes</span></span>|<span data-ttu-id="14750-189">はい</span><span class="sxs-lookup"><span data-stu-id="14750-189">Yes</span></span>|
|<span data-ttu-id="14750-190">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="14750-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="14750-191">はい</span><span class="sxs-lookup"><span data-stu-id="14750-191">Yes</span></span>|<span data-ttu-id="14750-192">はい</span><span class="sxs-lookup"><span data-stu-id="14750-192">Yes</span></span>|<span data-ttu-id="14750-193">はい</span><span class="sxs-lookup"><span data-stu-id="14750-193">Yes</span></span>|
|<span data-ttu-id="14750-194">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="14750-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="14750-195">はい</span><span class="sxs-lookup"><span data-stu-id="14750-195">Yes</span></span>|<span data-ttu-id="14750-196">はい</span><span class="sxs-lookup"><span data-stu-id="14750-196">Yes</span></span>|<span data-ttu-id="14750-197">はい</span><span class="sxs-lookup"><span data-stu-id="14750-197">Yes</span></span>|
|<span data-ttu-id="14750-198">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="14750-198">Password expiration (days)</span></span> |<span data-ttu-id="14750-199">はい</span><span class="sxs-lookup"><span data-stu-id="14750-199">Yes</span></span>|<span data-ttu-id="14750-200">はい</span><span class="sxs-lookup"><span data-stu-id="14750-200">Yes</span></span>|<span data-ttu-id="14750-201">はい</span><span class="sxs-lookup"><span data-stu-id="14750-201">Yes</span></span>|
|<span data-ttu-id="14750-202">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="14750-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="14750-203">はい</span><span class="sxs-lookup"><span data-stu-id="14750-203">Yes</span></span>|<span data-ttu-id="14750-204">はい</span><span class="sxs-lookup"><span data-stu-id="14750-204">Yes</span></span>|<span data-ttu-id="14750-205">はい</span><span class="sxs-lookup"><span data-stu-id="14750-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="14750-206">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="14750-206">Encryption settings</span></span> 

|<span data-ttu-id="14750-207">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-207">**Setting name**</span></span>|<span data-ttu-id="14750-208">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-209">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-209">**Android 5 and later**</span></span>|<span data-ttu-id="14750-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="14750-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14750-211">デバイス<sup>1</sup>でデータの暗号化を必須にする</span><span class="sxs-lookup"><span data-stu-id="14750-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="14750-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-212">No</span></span>|<span data-ttu-id="14750-213">はい</span><span class="sxs-lookup"><span data-stu-id="14750-213">Yes</span></span>|<span data-ttu-id="14750-214">はい</span><span class="sxs-lookup"><span data-stu-id="14750-214">Yes</span></span>|

<span data-ttu-id="14750-215"><sup>1</sup>Samsung Knox では、ストレージカードの暗号化も要求できます。</span><span class="sxs-lookup"><span data-stu-id="14750-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="14750-216">脱獄の設定</span><span class="sxs-lookup"><span data-stu-id="14750-216">Jail broken setting</span></span> 

|<span data-ttu-id="14750-217">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-217">**Setting name**</span></span>|<span data-ttu-id="14750-218">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-219">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-219">**Android 5 and later**</span></span>|<span data-ttu-id="14750-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="14750-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14750-221">デバイスの脱獄またはルート化はできません</span><span class="sxs-lookup"><span data-stu-id="14750-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="14750-222">はい</span><span class="sxs-lookup"><span data-stu-id="14750-222">Yes</span></span>|<span data-ttu-id="14750-223">はい</span><span class="sxs-lookup"><span data-stu-id="14750-223">Yes</span></span>|<span data-ttu-id="14750-224">はい</span><span class="sxs-lookup"><span data-stu-id="14750-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="14750-225">管理された電子メール プロファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="14750-225">Managed email profile option</span></span> 

<span data-ttu-id="14750-226">次のオプションを使用すると、ユーザーが手動で作成した電子メールプロファイルを使用している場合に、ユーザーが Microsoft 365 メールにアクセスするのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="14750-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="14750-227">iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="14750-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="14750-228">プロファイルを削除した後、新しいプロファイルがデバイスに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="14750-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="14750-229">エンドユーザーが準拠できる方法については、「 [既存の電子メールアカウントが見つかりました](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14750-229">For instructions on how end users can get compliant, see [An existing email account was found](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="14750-230">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-230">**Setting name**</span></span>|<span data-ttu-id="14750-231">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-232">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-232">**Android 5 and later**</span></span>|<span data-ttu-id="14750-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="14750-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14750-234">電子メール プロファイルが管理されている</span><span class="sxs-lookup"><span data-stu-id="14750-234">Email profile is managed</span></span> |<span data-ttu-id="14750-235">必要</span><span class="sxs-lookup"><span data-stu-id="14750-235">Yes</span></span>|<span data-ttu-id="14750-236">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-236">No</span></span>|<span data-ttu-id="14750-237">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="14750-238">クラウドの設定</span><span class="sxs-lookup"><span data-stu-id="14750-238">Cloud settings</span></span> 

|<span data-ttu-id="14750-239">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-239">**Setting name**</span></span>|<span data-ttu-id="14750-240">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-241">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-241">**Android 5 and later**</span></span>|<span data-ttu-id="14750-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="14750-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14750-243">暗号化されたバックアップを要求</span><span class="sxs-lookup"><span data-stu-id="14750-243">Require encrypted backup</span></span> |<span data-ttu-id="14750-244">必要</span><span class="sxs-lookup"><span data-stu-id="14750-244">Yes</span></span>|<span data-ttu-id="14750-245">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-245">No</span></span>|<span data-ttu-id="14750-246">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-246">No</span></span>|
|<span data-ttu-id="14750-247">クラウド バックアップの禁止</span><span class="sxs-lookup"><span data-stu-id="14750-247">Block cloud backup</span></span> |<span data-ttu-id="14750-248">必要</span><span class="sxs-lookup"><span data-stu-id="14750-248">Yes</span></span>|<span data-ttu-id="14750-249">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-249">No</span></span>|<span data-ttu-id="14750-250">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-250">No</span></span>|
|<span data-ttu-id="14750-251">ドキュメントの同期の禁止</span><span class="sxs-lookup"><span data-stu-id="14750-251">Block document synchronization</span></span> |<span data-ttu-id="14750-252">必要</span><span class="sxs-lookup"><span data-stu-id="14750-252">Yes</span></span>|<span data-ttu-id="14750-253">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-253">No</span></span>|<span data-ttu-id="14750-254">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-254">No</span></span>|
|<span data-ttu-id="14750-255">写真の同期の禁止</span><span class="sxs-lookup"><span data-stu-id="14750-255">Block photo synchronization</span></span>  |<span data-ttu-id="14750-256">必要</span><span class="sxs-lookup"><span data-stu-id="14750-256">Yes</span></span>|<span data-ttu-id="14750-257">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-257">No</span></span>|<span data-ttu-id="14750-258">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-258">No</span></span>|
|<span data-ttu-id="14750-259">Google バックアップを許可する</span><span class="sxs-lookup"><span data-stu-id="14750-259">Allow Google backup</span></span>  |<span data-ttu-id="14750-260">該当なし</span><span class="sxs-lookup"><span data-stu-id="14750-260">N/A</span></span>|<span data-ttu-id="14750-261">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-261">No</span></span>|<span data-ttu-id="14750-262">はい</span><span class="sxs-lookup"><span data-stu-id="14750-262">Yes</span></span>|
|<span data-ttu-id="14750-263">Google アカウントの自動同期を許可する</span><span class="sxs-lookup"><span data-stu-id="14750-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="14750-264">該当なし</span><span class="sxs-lookup"><span data-stu-id="14750-264">N/A</span></span>|<span data-ttu-id="14750-265">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-265">No</span></span>|<span data-ttu-id="14750-266">はい</span><span class="sxs-lookup"><span data-stu-id="14750-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="14750-267">システムの設定</span><span class="sxs-lookup"><span data-stu-id="14750-267">System settings</span></span> 

|<span data-ttu-id="14750-268">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-268">**Setting name**</span></span>|<span data-ttu-id="14750-269">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-270">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-270">**Android 5 and later**</span></span>|<span data-ttu-id="14750-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="14750-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14750-272">画面キャプチャの禁止</span><span class="sxs-lookup"><span data-stu-id="14750-272">Block screen capture</span></span> |<span data-ttu-id="14750-273">必要</span><span class="sxs-lookup"><span data-stu-id="14750-273">Yes</span></span>|<span data-ttu-id="14750-274">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-274">No</span></span>|<span data-ttu-id="14750-275">はい</span><span class="sxs-lookup"><span data-stu-id="14750-275">Yes</span></span>|
|<span data-ttu-id="14750-276">デバイスからの診断データ送信の禁止</span><span class="sxs-lookup"><span data-stu-id="14750-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="14750-277">必要</span><span class="sxs-lookup"><span data-stu-id="14750-277">Yes</span></span>|<span data-ttu-id="14750-278">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-278">No</span></span>|<span data-ttu-id="14750-279">はい</span><span class="sxs-lookup"><span data-stu-id="14750-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="14750-280">アプリケーションの設定</span><span class="sxs-lookup"><span data-stu-id="14750-280">Application settings</span></span> 

|<span data-ttu-id="14750-281">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-281">**Setting name**</span></span>|<span data-ttu-id="14750-282">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-283">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-283">**Android 5 and later**</span></span>|<span data-ttu-id="14750-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="14750-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14750-285">デバイスでのビデオ会議をブロックする</span><span class="sxs-lookup"><span data-stu-id="14750-285">Block video conferences on device</span></span> |<span data-ttu-id="14750-286">必要</span><span class="sxs-lookup"><span data-stu-id="14750-286">Yes</span></span>|<span data-ttu-id="14750-287">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-287">No</span></span>|<span data-ttu-id="14750-288">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-288">No</span></span>|
|<span data-ttu-id="14750-289">アプリケーション ストアへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="14750-289">Block access to application store</span></span> |<span data-ttu-id="14750-290">必要</span><span class="sxs-lookup"><span data-stu-id="14750-290">Yes</span></span>|<span data-ttu-id="14750-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-291">No</span></span>|<span data-ttu-id="14750-292">はい</span><span class="sxs-lookup"><span data-stu-id="14750-292">Yes</span></span>|
|<span data-ttu-id="14750-293">アプリケーション ストアへアクセスする際にパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="14750-293">Require password when accessing application store</span></span> |<span data-ttu-id="14750-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-294">No</span></span>|<span data-ttu-id="14750-295">はい</span><span class="sxs-lookup"><span data-stu-id="14750-295">Yes</span></span>|<span data-ttu-id="14750-296">はい</span><span class="sxs-lookup"><span data-stu-id="14750-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="14750-297">デバイスの機能の設定</span><span class="sxs-lookup"><span data-stu-id="14750-297">Device capabilities settings</span></span> 

|<span data-ttu-id="14750-298">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-298">**Setting name**</span></span>|<span data-ttu-id="14750-299">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-300">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-300">**Android 5 and later**</span></span>|<span data-ttu-id="14750-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="14750-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14750-302">リムーバブル記憶域との接続の禁止</span><span class="sxs-lookup"><span data-stu-id="14750-302">Block connection with removable storage</span></span> |<span data-ttu-id="14750-303">はい</span><span class="sxs-lookup"><span data-stu-id="14750-303">Yes</span></span>|<span data-ttu-id="14750-304">はい</span><span class="sxs-lookup"><span data-stu-id="14750-304">Yes</span></span>|<span data-ttu-id="14750-305">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-305">No</span></span>|
|<span data-ttu-id="14750-306">Bluetooth 接続の禁止</span><span class="sxs-lookup"><span data-stu-id="14750-306">Block Bluetooth connection</span></span> |<span data-ttu-id="14750-307">はい</span><span class="sxs-lookup"><span data-stu-id="14750-307">Yes</span></span>|<span data-ttu-id="14750-308">はい</span><span class="sxs-lookup"><span data-stu-id="14750-308">Yes</span></span>|<span data-ttu-id="14750-309">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-309">No</span></span>|

##  <a name="additional-settings"></a><span data-ttu-id="14750-310">その他の設定</span><span class="sxs-lookup"><span data-stu-id="14750-310">Additional settings</span></span> 

<span data-ttu-id="14750-311">PowerShell コマンドレットを使用して、次のようなポリシー設定もできます。</span><span class="sxs-lookup"><span data-stu-id="14750-311">You can set the following additional policy settings by using PowerShell cmdlets.</span></span> <span data-ttu-id="14750-312">詳細については、「 [Security & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14750-312">For more information, see [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

|<span data-ttu-id="14750-313">**設定名**</span><span class="sxs-lookup"><span data-stu-id="14750-313">**Setting name**</span></span>|<span data-ttu-id="14750-314">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="14750-315">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="14750-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="14750-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="14750-316">CameraEnabled</span></span>|<span data-ttu-id="14750-317">はい</span><span class="sxs-lookup"><span data-stu-id="14750-317">Yes</span></span>|<span data-ttu-id="14750-318">はい</span><span class="sxs-lookup"><span data-stu-id="14750-318">Yes</span></span>|
|<span data-ttu-id="14750-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="14750-319">RegionRatings</span></span>|<span data-ttu-id="14750-320">必要</span><span class="sxs-lookup"><span data-stu-id="14750-320">Yes</span></span>|<span data-ttu-id="14750-321">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-321">No</span></span>|
|<span data-ttu-id="14750-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="14750-322">MoviesRatings</span></span>|<span data-ttu-id="14750-323">必要</span><span class="sxs-lookup"><span data-stu-id="14750-323">Yes</span></span>|<span data-ttu-id="14750-324">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-324">No</span></span>|
|<span data-ttu-id="14750-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="14750-325">TVShowsRating</span></span> |<span data-ttu-id="14750-326">必要</span><span class="sxs-lookup"><span data-stu-id="14750-326">Yes</span></span>|<span data-ttu-id="14750-327">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-327">No</span></span>|
|<span data-ttu-id="14750-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="14750-328">AppsRatings</span></span> |<span data-ttu-id="14750-329">必要</span><span class="sxs-lookup"><span data-stu-id="14750-329">Yes</span></span>|<span data-ttu-id="14750-330">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-330">No</span></span>|
|<span data-ttu-id="14750-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="14750-331">AllowVoiceDialing</span></span> |<span data-ttu-id="14750-332">必要</span><span class="sxs-lookup"><span data-stu-id="14750-332">Yes</span></span>|<span data-ttu-id="14750-333">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-333">No</span></span>|
|<span data-ttu-id="14750-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="14750-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="14750-335">必要</span><span class="sxs-lookup"><span data-stu-id="14750-335">Yes</span></span>|<span data-ttu-id="14750-336">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-336">No</span></span>|
|<span data-ttu-id="14750-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="14750-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="14750-338">必要</span><span class="sxs-lookup"><span data-stu-id="14750-338">Yes</span></span>|<span data-ttu-id="14750-339">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-339">No</span></span>|
|<span data-ttu-id="14750-340">Allowpass Booklocked Locked</span><span class="sxs-lookup"><span data-stu-id="14750-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="14750-341">必要</span><span class="sxs-lookup"><span data-stu-id="14750-341">Yes</span></span>|<span data-ttu-id="14750-342">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-342">No</span></span>|
|<span data-ttu-id="14750-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="14750-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="14750-344">必要</span><span class="sxs-lookup"><span data-stu-id="14750-344">Yes</span></span>|<span data-ttu-id="14750-345">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-345">No</span></span>|
|<span data-ttu-id="14750-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="14750-346">PasswordQuality</span></span> |<span data-ttu-id="14750-347">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-347">No</span></span>|<span data-ttu-id="14750-348">はい</span><span class="sxs-lookup"><span data-stu-id="14750-348">Yes</span></span>|
|<span data-ttu-id="14750-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="14750-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="14750-350">必要</span><span class="sxs-lookup"><span data-stu-id="14750-350">Yes</span></span>|<span data-ttu-id="14750-351">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-351">No</span></span>|
|<span data-ttu-id="14750-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="14750-352">WLANEnabled</span></span>  |<span data-ttu-id="14750-353">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-353">No</span></span>|<span data-ttu-id="14750-354">いいえ</span><span class="sxs-lookup"><span data-stu-id="14750-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="14750-355">Windows でサポートされている設定</span><span class="sxs-lookup"><span data-stu-id="14750-355">Settings supported by Windows</span></span> 

<span data-ttu-id="14750-356">Windows 10 デバイスは、モバイルデバイスとして登録することによって管理できます。</span><span class="sxs-lookup"><span data-stu-id="14750-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="14750-357">適用可能なポリシーを展開した後、Windows 10 デバイスを使用しているユーザーは、組み込みの電子メールアプリを使用して Microsoft 365 メールにアクセスするときに、基本的なモビリティとセキュリティに登録する必要があります (Azure AD premium サブスクリプションを必要とします)。</span><span class="sxs-lookup"><span data-stu-id="14750-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="14750-358">次の設定は、モバイルデバイスとして登録されている Windows 10 デバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="14750-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="14750-359">これらの設定は、ユーザーが Microsoft 365 リソースにアクセスすることをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="14750-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="14750-360">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="14750-360">Security settings</span></span>

- <span data-ttu-id="14750-361">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="14750-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="14750-362">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="14750-362">Minimum password length</span></span>
    
- <span data-ttu-id="14750-363">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="14750-363">Number of sign-in failures before device is wiped</span></span>
    
- <span data-ttu-id="14750-364">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="14750-364">Minutes of inactivity before device is locked</span></span>
    
- <span data-ttu-id="14750-365">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="14750-365">Password expiration (days)</span></span>
    
- <span data-ttu-id="14750-366">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="14750-366">Remember password history and prevent reuse</span></span>   

>[!NOTE]
><span data-ttu-id="14750-367">次の設定は、パスワードを制御するローカル Windows アカウントのみを制御します。</span><span class="sxs-lookup"><span data-stu-id="14750-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="14750-368">ドメインまたは Azure Active Directory に参加して提供された Windows アカウントは、これらの設定の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="14750-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="14750-369">システムの設定</span><span class="sxs-lookup"><span data-stu-id="14750-369">System settings</span></span>

<span data-ttu-id="14750-370">デバイスから診断データを送信することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="14750-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="14750-371">その他の設定</span><span class="sxs-lookup"><span data-stu-id="14750-371">Additional settings</span></span>

<span data-ttu-id="14750-372">PowerShell コマンドレットを使用して、これらの追加のポリシー設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="14750-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="14750-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="14750-373">AllowConvenienceLogon</span></span>
    
- <span data-ttu-id="14750-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="14750-374">UserAccountControlStatus</span></span>
    
- <span data-ttu-id="14750-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="14750-375">FirewallStatus</span></span>
    
- <span data-ttu-id="14750-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="14750-376">AutoUpdateStatus</span></span>
    
- <span data-ttu-id="14750-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="14750-377">AntiVirusStatus</span></span>   

- <span data-ttu-id="14750-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="14750-378">AntiVirusSignatureStatus</span></span>
    
- <span data-ttu-id="14750-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="14750-379">SmartScreenEnabled</span></span>
    
- <span data-ttu-id="14750-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="14750-380">WorkFoldersSyncUrl</span></span>
    

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="14750-381">モバイル デバイスをリモートからワイプする</span><span class="sxs-lookup"><span data-stu-id="14750-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="14750-382">デバイスが紛失または盗難にあった場合は、機密の組織データを削除し、セキュリティ & コンプライアンスセンター >**データ損失防止**  >  **デバイス管理**からのワイプを行って、Microsoft 365 組織のリソースにアクセスできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="14750-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="14750-383">個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="14750-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="14750-384">詳細については、「 [Basic Mobility And Security でモバイルデバイスをワイプする](wipe-mobile-device.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14750-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="14750-385">関連項目</span><span class="sxs-lookup"><span data-stu-id="14750-385">Related topics</span></span>

[<span data-ttu-id="14750-386">Microsoft 365 の基本的なモビリティとセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="14750-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="14750-387">基本的なモビリティとセキュリティでデバイスのセキュリティポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="14750-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)