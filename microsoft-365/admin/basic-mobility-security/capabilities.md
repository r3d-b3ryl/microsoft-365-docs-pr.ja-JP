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
ms.openlocfilehash: aed4f4c2d252e487d24496ac00f3de24bc57ab55
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545898"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="bd35a-103">基本的なモビリティとセキュリティの機能</span><span class="sxs-lookup"><span data-stu-id="bd35a-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="bd35a-104">基本的なモビリティとセキュリティは、組織内のライセンスである Microsoft 365 ユーザーが使用する iPhones、Ipad、Androids、Windows Phone などのモバイルデバイスをセキュリティで保護し、管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="bd35a-105">サポートされているモバイルデバイスおよびアプリについて、組織の Microsoft 365 電子メールおよびドキュメントへのアクセスを制御するのに役立つ設定を使用して、モバイルデバイス管理ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="bd35a-106">デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="bd35a-107">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="bd35a-107">Supported devices</span></span>

<span data-ttu-id="bd35a-108">基本的なモビリティとセキュリティを使用して、以下のデバイスをセキュリティで保護し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="bd35a-109">iOS 11.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="bd35a-109">iOS 11.0 or later versions</span></span>
    
- <span data-ttu-id="bd35a-110">Android 5.0 以降のバージョン<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="bd35a-110">Android 5.0 or later versions<sup>3</sup></span></span>
    
- <span data-ttu-id="bd35a-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bd35a-111">Windows 8.1<sup>1</sup></span></span>
    
- <span data-ttu-id="bd35a-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bd35a-112">Windows 8.1 RT<sup>1</sup></span></span>
    
- <span data-ttu-id="bd35a-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bd35a-113">Windows 10<sup>2</sup></span></span>
    
- <span data-ttu-id="bd35a-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bd35a-114">Windows 10 Mobile<sup>2</sup></span></span>   

<span data-ttu-id="bd35a-115"><sup>1</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="bd35a-116"><sup>2</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="bd35a-117">Windows 10 のアクセス制御には、Azure AD Premium を含むサブスクリプションが必要です。また、デバイスを Azure Active Directory に参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd35a-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="bd35a-118"><sup>3</sup>Windows 8.1 RT デバイスのアクセス制御は、Exchange ActiveSync に限定されます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="bd35a-119">2020年6月以降、2010バージョン9より後のバージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。</span><span class="sxs-lookup"><span data-stu-id="bd35a-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="bd35a-120">以前のバージョンの OS で既に登録されているデバイスは、機能は予告なしに変更されることがありますが、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="bd35a-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="bd35a-121">組織内のユーザーが基本的なモビリティとセキュリティでサポートされていないモバイルデバイスを使用している場合、組織のデータのセキュリティを強化するために、これらのデバイスの Microsoft 365 電子メールへの Exchange ActiveSync アプリのアクセスをブロックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bd35a-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="bd35a-122">Exchange ActiveSync をブロックする手順については、「 [基本的なモビリティとセキュリティでデバイスアクセス設定を管理](manage-device-access-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd35a-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="bd35a-123">Microsoft 365 メールとドキュメントのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="bd35a-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="bd35a-124">次の表に示すさまざまな種類のモバイルデバイス用にサポートされているアプリは、ユーザーのデバイスに適用され、ユーザーが以前にデバイスを登録していない新しいモバイルデバイス管理ポリシーがある場合に、基本的なモビリティとセキュリティに登録するようにユーザーに促します。</span><span class="sxs-lookup"><span data-stu-id="bd35a-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="bd35a-125">ユーザーのデバイスがポリシーに準拠していない場合、ポリシーの設定方法によっては、ユーザーがこれらのアプリで Microsoft 365 リソースへのアクセスをブロックされたり、Microsoft 365 がポリシー違反を報告したりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="bd35a-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="bd35a-126">**製品**</span><span class="sxs-lookup"><span data-stu-id="bd35a-126">**Product**</span></span>|<span data-ttu-id="bd35a-127">**iOS 10.0 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="bd35a-128">**Android 5.0 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-129">**Exchange** Exchange ActiveSync には、Exchange ActiveSync バージョン14.1 以降を使用する、組み込みの電子メールとサードパーティ製のアプリ (接地など) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd35a-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="bd35a-130">メール</span><span class="sxs-lookup"><span data-stu-id="bd35a-130">Mail</span></span> |<span data-ttu-id="bd35a-131">メール</span><span class="sxs-lookup"><span data-stu-id="bd35a-131">Email</span></span> |
|<span data-ttu-id="bd35a-132">**Office**  および **OneDrive For business**</span><span class="sxs-lookup"><span data-stu-id="bd35a-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="bd35a-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="bd35a-133">Outlook</span></span> </br><span data-ttu-id="bd35a-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="bd35a-134">OneDrive</span></span> </br><span data-ttu-id="bd35a-135">Word</span><span class="sxs-lookup"><span data-stu-id="bd35a-135">Word</span></span> </br><span data-ttu-id="bd35a-136">Excel</span><span class="sxs-lookup"><span data-stu-id="bd35a-136">Excel</span></span> </br><span data-ttu-id="bd35a-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bd35a-137">PowerPoint</span></span>|<span data-ttu-id="bd35a-138">**電話とタブレットの**場合:</span><span class="sxs-lookup"><span data-stu-id="bd35a-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="bd35a-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="bd35a-139">Outlook</span></span> <br/> <span data-ttu-id="bd35a-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="bd35a-140">OneDrive</span></span> <br/> <span data-ttu-id="bd35a-141">Word</span><span class="sxs-lookup"><span data-stu-id="bd35a-141">Word</span></span> <br/> <span data-ttu-id="bd35a-142">Excel</span><span class="sxs-lookup"><span data-stu-id="bd35a-142">Excel</span></span> <br/> <span data-ttu-id="bd35a-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bd35a-143">PowerPoint</span></span> <br/> <span data-ttu-id="bd35a-144">**電話のみ:**</span><span class="sxs-lookup"><span data-stu-id="bd35a-144">**On phones only:**</span></span> <br/> <span data-ttu-id="bd35a-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="bd35a-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="bd35a-146">IOS 10.0 以降のバージョンのサポートには、iPhone と iPad デバイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd35a-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="bd35a-147">Microsoft 365 のモバイルデバイス管理では、BlackBerry OS デバイスの管理はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bd35a-147">Management of BlackBerry OS devices isn’t supported by Mobile Device Management for Microsoft 365.</span></span> <span data-ttu-id="bd35a-148">Blackberry のビジネスクラウドサービス (BBCS) を blackberry で使用して BlackBerry OS デバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="bd35a-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="bd35a-149">Android OS を実行している Blackberry デバイスは標準の Android デバイスとしてサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bd35a-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="bd35a-150">ユーザーがモバイルブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online 内のドキュメント、または Outlook Web App 内の電子メールにアクセスした場合、登録を求めるメッセージは表示されず、ブロックされたり、ポリシー違反が報告されることはありません。</span><span class="sxs-lookup"><span data-stu-id="bd35a-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>
    
<span data-ttu-id="bd35a-151">次の図は、新しいデバイスを使用しているユーザーが、基本的なモビリティとセキュリティでアクセス制御をサポートするアプリにサインインしたときの動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd35a-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="bd35a-152">ユーザーは、デバイスを登録するまで、アプリで Microsoft 365 リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティおよびセキュリティアクセス制御":::

<span data-ttu-id="bd35a-154">注: Microsoft 365 Business Standard 用 MDM で作成されるポリシーとアクセスルールは、exchange ActiveSync モバイルデバイスメールボックスポリシーと、Exchange 管理センターで作成されたデバイスアクセスルールより優先されます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-154">Note:Policies and access rules created in MDM for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="bd35a-155">Microsoft 365 Business Standard の MDM にデバイスを登録した後、デバイスに適用された Exchange ActiveSync モバイルデバイスメールボックスポリシーまたはデバイスアクセスルールは無視されます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-155">After a device is enrolled in MDM for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="bd35a-156">Exchange ActiveSync の詳細については、「exchange [activesync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd35a-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="bd35a-157">モバイル デバイス用のポリシー設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="bd35a-158">特定の設定を有効にしてアクセスをブロックするポリシーを作成した場合、 [microsoft 365 の電子メールとドキュメントのアクセス制御](capabilities.md)に記載されているサポートされているアプリを使用すると、ユーザーは microsoft 365 リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="bd35a-159">ユーザーが Microsoft 365 リソースにアクセスできないようにする設定については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd35a-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="bd35a-160">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="bd35a-160">Security</span></span>
    
- <span data-ttu-id="bd35a-161">暗号化</span><span class="sxs-lookup"><span data-stu-id="bd35a-161">Encryption</span></span>
    
- <span data-ttu-id="bd35a-162">脱獄</span><span class="sxs-lookup"><span data-stu-id="bd35a-162">Jail broken</span></span>
    
- <span data-ttu-id="bd35a-163">管理された電子メール プロファイル</span><span class="sxs-lookup"><span data-stu-id="bd35a-163">Managed email profile</span></span>  

<span data-ttu-id="bd35a-164">例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd35a-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="bd35a-165">ユーザーは、基本的なモビリティとセキュリティでアクセス制御をサポートするアプリにサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd35a-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="bd35a-166">デバイスがセキュリティ設定に準拠するまで、アプリ内の Microsoft 365 リソースへのアクセスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="基本的なモビリティおよびセキュリティコンプライアンスメッセージ":::

<span data-ttu-id="bd35a-168">次のセクションでは、Microsoft 365 組織のリソースに接続するモバイルデバイスをセキュリティで保護し、管理するために使用できるポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="bd35a-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="bd35a-169">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-169">Security settings</span></span>

|<span data-ttu-id="bd35a-170">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-170">**Setting name**</span></span>|<span data-ttu-id="bd35a-171">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-172">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-172">**Android 5 and later**</span></span>|<span data-ttu-id="bd35a-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="bd35a-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-174">パスワードを要求</span><span class="sxs-lookup"><span data-stu-id="bd35a-174">Require a password</span></span>|<span data-ttu-id="bd35a-175">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-175">Yes</span></span>|<span data-ttu-id="bd35a-176">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-176">Yes</span></span>|<span data-ttu-id="bd35a-177">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-177">Yes</span></span>|
|<span data-ttu-id="bd35a-178">シンプルなパスワードを禁止</span><span class="sxs-lookup"><span data-stu-id="bd35a-178">Prevent simple password</span></span>|<span data-ttu-id="bd35a-179">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-179">Yes</span></span>|<span data-ttu-id="bd35a-180">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-180">No</span></span>|<span data-ttu-id="bd35a-181">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-181">No</span></span>|
|<span data-ttu-id="bd35a-182">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="bd35a-182">Require an alphanumeric password</span></span>|<span data-ttu-id="bd35a-183">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-183">Yes</span></span>|<span data-ttu-id="bd35a-184">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-184">No</span></span>|<span data-ttu-id="bd35a-185">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-185">No</span></span>|
|<span data-ttu-id="bd35a-186">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="bd35a-186">Minimum password length</span></span> |<span data-ttu-id="bd35a-187">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-187">Yes</span></span>|<span data-ttu-id="bd35a-188">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-188">Yes</span></span>|<span data-ttu-id="bd35a-189">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-189">Yes</span></span>|
|<span data-ttu-id="bd35a-190">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="bd35a-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="bd35a-191">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-191">Yes</span></span>|<span data-ttu-id="bd35a-192">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-192">Yes</span></span>|<span data-ttu-id="bd35a-193">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-193">Yes</span></span>|
|<span data-ttu-id="bd35a-194">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="bd35a-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="bd35a-195">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-195">Yes</span></span>|<span data-ttu-id="bd35a-196">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-196">Yes</span></span>|<span data-ttu-id="bd35a-197">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-197">Yes</span></span>|
|<span data-ttu-id="bd35a-198">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="bd35a-198">Password expiration (days)</span></span> |<span data-ttu-id="bd35a-199">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-199">Yes</span></span>|<span data-ttu-id="bd35a-200">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-200">Yes</span></span>|<span data-ttu-id="bd35a-201">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-201">Yes</span></span>|
|<span data-ttu-id="bd35a-202">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="bd35a-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="bd35a-203">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-203">Yes</span></span>|<span data-ttu-id="bd35a-204">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-204">Yes</span></span>|<span data-ttu-id="bd35a-205">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="bd35a-206">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-206">Encryption settings</span></span> 

|<span data-ttu-id="bd35a-207">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-207">**Setting name**</span></span>|<span data-ttu-id="bd35a-208">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-209">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-209">**Android 5 and later**</span></span>|<span data-ttu-id="bd35a-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="bd35a-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-211">デバイス<sup>1</sup>でデータの暗号化を必須にする</span><span class="sxs-lookup"><span data-stu-id="bd35a-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="bd35a-212">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-212">No</span></span>|<span data-ttu-id="bd35a-213">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-213">Yes</span></span>|<span data-ttu-id="bd35a-214">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-214">Yes</span></span>|

<span data-ttu-id="bd35a-215"><sup>1</sup>Samsung Knox では、ストレージカードの暗号化も要求できます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="bd35a-216">脱獄の設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-216">Jail broken setting</span></span> 

|<span data-ttu-id="bd35a-217">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-217">**Setting name**</span></span>|<span data-ttu-id="bd35a-218">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-219">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-219">**Android 5 and later**</span></span>|<span data-ttu-id="bd35a-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="bd35a-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-221">デバイスの脱獄またはルート化はできません</span><span class="sxs-lookup"><span data-stu-id="bd35a-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="bd35a-222">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-222">Yes</span></span>|<span data-ttu-id="bd35a-223">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-223">Yes</span></span>|<span data-ttu-id="bd35a-224">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="bd35a-225">管理された電子メール プロファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="bd35a-225">Managed email profile option</span></span> 

<span data-ttu-id="bd35a-226">次のオプションを使用すると、ユーザーが手動で作成した電子メールプロファイルを使用している場合に、ユーザーが Microsoft 365 メールにアクセスするのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="bd35a-227">iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd35a-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="bd35a-228">プロファイルを削除した後、新しいプロファイルがデバイスに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="bd35a-229">エンドユーザーが準拠できる方法については、「 [既存の電子メールアカウントが見つかりました](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)。」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd35a-229">For instructions on how end users can get compliant, see [An existing email account was found](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="bd35a-230">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-230">**Setting name**</span></span>|<span data-ttu-id="bd35a-231">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-232">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-232">**Android 5 and later**</span></span>|<span data-ttu-id="bd35a-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="bd35a-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-234">電子メール プロファイルが管理されている</span><span class="sxs-lookup"><span data-stu-id="bd35a-234">Email profile is managed</span></span> |<span data-ttu-id="bd35a-235">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-235">Yes</span></span>|<span data-ttu-id="bd35a-236">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-236">No</span></span>|<span data-ttu-id="bd35a-237">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="bd35a-238">クラウドの設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-238">Cloud settings</span></span> 

|<span data-ttu-id="bd35a-239">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-239">**Setting name**</span></span>|<span data-ttu-id="bd35a-240">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-241">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-241">**Android 5 and later**</span></span>|<span data-ttu-id="bd35a-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="bd35a-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-243">暗号化されたバックアップを要求</span><span class="sxs-lookup"><span data-stu-id="bd35a-243">Require encrypted backup</span></span> |<span data-ttu-id="bd35a-244">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-244">Yes</span></span>|<span data-ttu-id="bd35a-245">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-245">No</span></span>|<span data-ttu-id="bd35a-246">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-246">No</span></span>|
|<span data-ttu-id="bd35a-247">クラウド バックアップの禁止</span><span class="sxs-lookup"><span data-stu-id="bd35a-247">Block cloud backup</span></span> |<span data-ttu-id="bd35a-248">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-248">Yes</span></span>|<span data-ttu-id="bd35a-249">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-249">No</span></span>|<span data-ttu-id="bd35a-250">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-250">No</span></span>|
|<span data-ttu-id="bd35a-251">ドキュメントの同期の禁止</span><span class="sxs-lookup"><span data-stu-id="bd35a-251">Block document synchronization</span></span> |<span data-ttu-id="bd35a-252">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-252">Yes</span></span>|<span data-ttu-id="bd35a-253">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-253">No</span></span>|<span data-ttu-id="bd35a-254">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-254">No</span></span>|
|<span data-ttu-id="bd35a-255">写真の同期の禁止</span><span class="sxs-lookup"><span data-stu-id="bd35a-255">Block photo synchronization</span></span>  |<span data-ttu-id="bd35a-256">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-256">Yes</span></span>|<span data-ttu-id="bd35a-257">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-257">No</span></span>|<span data-ttu-id="bd35a-258">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-258">No</span></span>|
|<span data-ttu-id="bd35a-259">Google バックアップを許可する</span><span class="sxs-lookup"><span data-stu-id="bd35a-259">Allow Google backup</span></span>  |<span data-ttu-id="bd35a-260">該当なし</span><span class="sxs-lookup"><span data-stu-id="bd35a-260">N/A</span></span>|<span data-ttu-id="bd35a-261">いいえ</span><span class="sxs-lookup"><span data-stu-id="bd35a-261">No</span></span>|<span data-ttu-id="bd35a-262">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-262">Yes</span></span>|
|<span data-ttu-id="bd35a-263">Google アカウントの自動同期を許可する</span><span class="sxs-lookup"><span data-stu-id="bd35a-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="bd35a-264">該当なし</span><span class="sxs-lookup"><span data-stu-id="bd35a-264">N/A</span></span>|<span data-ttu-id="bd35a-265">いいえ</span><span class="sxs-lookup"><span data-stu-id="bd35a-265">No</span></span>|<span data-ttu-id="bd35a-266">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="bd35a-267">システムの設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-267">System settings</span></span> 

|<span data-ttu-id="bd35a-268">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-268">**Setting name**</span></span>|<span data-ttu-id="bd35a-269">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-270">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-270">**Android 5 and later**</span></span>|<span data-ttu-id="bd35a-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="bd35a-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-272">画面キャプチャの禁止</span><span class="sxs-lookup"><span data-stu-id="bd35a-272">Block screen capture</span></span> |<span data-ttu-id="bd35a-273">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-273">Yes</span></span>|<span data-ttu-id="bd35a-274">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-274">No</span></span>|<span data-ttu-id="bd35a-275">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-275">Yes</span></span>|
|<span data-ttu-id="bd35a-276">デバイスからの診断データ送信の禁止</span><span class="sxs-lookup"><span data-stu-id="bd35a-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="bd35a-277">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-277">Yes</span></span>|<span data-ttu-id="bd35a-278">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-278">No</span></span>|<span data-ttu-id="bd35a-279">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="bd35a-280">アプリケーションの設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-280">Application settings</span></span> 

|<span data-ttu-id="bd35a-281">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-281">**Setting name**</span></span>|<span data-ttu-id="bd35a-282">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-283">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-283">**Android 5 and later**</span></span>|<span data-ttu-id="bd35a-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="bd35a-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-285">デバイスでのビデオ会議をブロックする</span><span class="sxs-lookup"><span data-stu-id="bd35a-285">Block video conferences on device</span></span> |<span data-ttu-id="bd35a-286">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-286">Yes</span></span>|<span data-ttu-id="bd35a-287">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-287">No</span></span>|<span data-ttu-id="bd35a-288">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-288">No</span></span>|
|<span data-ttu-id="bd35a-289">アプリケーション ストアへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="bd35a-289">Block access to application store</span></span> |<span data-ttu-id="bd35a-290">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-290">Yes</span></span>|<span data-ttu-id="bd35a-291">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-291">No</span></span>|<span data-ttu-id="bd35a-292">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-292">Yes</span></span>|
|<span data-ttu-id="bd35a-293">アプリケーション ストアへアクセスする際にパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="bd35a-293">Require password when accessing application store</span></span> |<span data-ttu-id="bd35a-294">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-294">No</span></span>|<span data-ttu-id="bd35a-295">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-295">Yes</span></span>|<span data-ttu-id="bd35a-296">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="bd35a-297">デバイスの機能の設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-297">Device capabilities settings</span></span> 

|<span data-ttu-id="bd35a-298">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-298">**Setting name**</span></span>|<span data-ttu-id="bd35a-299">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-300">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-300">**Android 5 and later**</span></span>|<span data-ttu-id="bd35a-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="bd35a-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-302">リムーバブル記憶域との接続の禁止</span><span class="sxs-lookup"><span data-stu-id="bd35a-302">Block connection with removable storage</span></span> |<span data-ttu-id="bd35a-303">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-303">Yes</span></span>|<span data-ttu-id="bd35a-304">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-304">Yes</span></span>|<span data-ttu-id="bd35a-305">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-305">No</span></span>|
|<span data-ttu-id="bd35a-306">Bluetooth 接続の禁止</span><span class="sxs-lookup"><span data-stu-id="bd35a-306">Block Bluetooth connection</span></span> |<span data-ttu-id="bd35a-307">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-307">Yes</span></span>|<span data-ttu-id="bd35a-308">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-308">Yes</span></span>|<span data-ttu-id="bd35a-309">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-309">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="bd35a-310">その他の設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-310">Additional settings</span></span>

<span data-ttu-id="bd35a-311">セキュリティ & コンプライアンスセンターの PowerShell コマンドレットを使用して、次の追加のポリシー設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-311">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="bd35a-312">詳細については、「 [Security & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd35a-312">For more information, see [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="bd35a-313">**設定名**</span><span class="sxs-lookup"><span data-stu-id="bd35a-313">**Setting name**</span></span>|<span data-ttu-id="bd35a-314">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="bd35a-315">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="bd35a-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bd35a-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="bd35a-316">CameraEnabled</span></span>|<span data-ttu-id="bd35a-317">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-317">Yes</span></span>|<span data-ttu-id="bd35a-318">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-318">Yes</span></span>|
|<span data-ttu-id="bd35a-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="bd35a-319">RegionRatings</span></span>|<span data-ttu-id="bd35a-320">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-320">Yes</span></span>|<span data-ttu-id="bd35a-321">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-321">No</span></span>|
|<span data-ttu-id="bd35a-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="bd35a-322">MoviesRatings</span></span>|<span data-ttu-id="bd35a-323">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-323">Yes</span></span>|<span data-ttu-id="bd35a-324">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-324">No</span></span>|
|<span data-ttu-id="bd35a-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="bd35a-325">TVShowsRating</span></span> |<span data-ttu-id="bd35a-326">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-326">Yes</span></span>|<span data-ttu-id="bd35a-327">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-327">No</span></span>|
|<span data-ttu-id="bd35a-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="bd35a-328">AppsRatings</span></span> |<span data-ttu-id="bd35a-329">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-329">Yes</span></span>|<span data-ttu-id="bd35a-330">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-330">No</span></span>|
|<span data-ttu-id="bd35a-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="bd35a-331">AllowVoiceDialing</span></span> |<span data-ttu-id="bd35a-332">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-332">Yes</span></span>|<span data-ttu-id="bd35a-333">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-333">No</span></span>|
|<span data-ttu-id="bd35a-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="bd35a-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="bd35a-335">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-335">Yes</span></span>|<span data-ttu-id="bd35a-336">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-336">No</span></span>|
|<span data-ttu-id="bd35a-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="bd35a-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="bd35a-338">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-338">Yes</span></span>|<span data-ttu-id="bd35a-339">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-339">No</span></span>|
|<span data-ttu-id="bd35a-340">Allowpass Booklocked Locked</span><span class="sxs-lookup"><span data-stu-id="bd35a-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="bd35a-341">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-341">Yes</span></span>|<span data-ttu-id="bd35a-342">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-342">No</span></span>|
|<span data-ttu-id="bd35a-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="bd35a-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="bd35a-344">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-344">Yes</span></span>|<span data-ttu-id="bd35a-345">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-345">No</span></span>|
|<span data-ttu-id="bd35a-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="bd35a-346">PasswordQuality</span></span> |<span data-ttu-id="bd35a-347">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-347">No</span></span>|<span data-ttu-id="bd35a-348">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-348">Yes</span></span>|
|<span data-ttu-id="bd35a-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="bd35a-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="bd35a-350">はい</span><span class="sxs-lookup"><span data-stu-id="bd35a-350">Yes</span></span>|<span data-ttu-id="bd35a-351">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-351">No</span></span>|
|<span data-ttu-id="bd35a-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="bd35a-352">WLANEnabled</span></span>  |<span data-ttu-id="bd35a-353">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-353">No</span></span>|<span data-ttu-id="bd35a-354">不要</span><span class="sxs-lookup"><span data-stu-id="bd35a-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="bd35a-355">Windows でサポートされている設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-355">Settings supported by Windows</span></span> 

<span data-ttu-id="bd35a-356">Windows 10 デバイスは、モバイルデバイスとして登録することによって管理できます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="bd35a-357">適用可能なポリシーを展開した後、Windows 10 デバイスを使用しているユーザーは、組み込みの電子メールアプリを使用して Microsoft 365 メールにアクセスするときに、基本的なモビリティとセキュリティに登録する必要があります (Azure AD premium サブスクリプションを必要とします)。</span><span class="sxs-lookup"><span data-stu-id="bd35a-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="bd35a-358">次の設定は、モバイルデバイスとして登録されている Windows 10 デバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bd35a-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="bd35a-359">これらの設定は、ユーザーが Microsoft 365 リソースにアクセスすることをブロックしません。</span><span class="sxs-lookup"><span data-stu-id="bd35a-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="bd35a-360">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-360">Security settings</span></span>

- <span data-ttu-id="bd35a-361">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="bd35a-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="bd35a-362">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="bd35a-362">Minimum password length</span></span>
    
- <span data-ttu-id="bd35a-363">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="bd35a-363">Number of sign-in failures before device is wiped</span></span>
    
- <span data-ttu-id="bd35a-364">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="bd35a-364">Minutes of inactivity before device is locked</span></span>
    
- <span data-ttu-id="bd35a-365">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="bd35a-365">Password expiration (days)</span></span>
    
- <span data-ttu-id="bd35a-366">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="bd35a-366">Remember password history and prevent reuse</span></span>   

>[!NOTE]
><span data-ttu-id="bd35a-367">次の設定は、パスワードを制御するローカル Windows アカウントのみを制御します。</span><span class="sxs-lookup"><span data-stu-id="bd35a-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="bd35a-368">ドメインまたは Azure Active Directory に参加して提供された Windows アカウントは、これらの設定の影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="bd35a-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="bd35a-369">システムの設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-369">System settings</span></span>

<span data-ttu-id="bd35a-370">デバイスから診断データを送信することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="bd35a-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="bd35a-371">その他の設定</span><span class="sxs-lookup"><span data-stu-id="bd35a-371">Additional settings</span></span>

<span data-ttu-id="bd35a-372">PowerShell コマンドレットを使用して、これらの追加のポリシー設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="bd35a-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="bd35a-373">AllowConvenienceLogon</span></span>
    
- <span data-ttu-id="bd35a-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="bd35a-374">UserAccountControlStatus</span></span>
    
- <span data-ttu-id="bd35a-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="bd35a-375">FirewallStatus</span></span>
    
- <span data-ttu-id="bd35a-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="bd35a-376">AutoUpdateStatus</span></span>
    
- <span data-ttu-id="bd35a-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="bd35a-377">AntiVirusStatus</span></span>   

- <span data-ttu-id="bd35a-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="bd35a-378">AntiVirusSignatureStatus</span></span>
    
- <span data-ttu-id="bd35a-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="bd35a-379">SmartScreenEnabled</span></span>
    
- <span data-ttu-id="bd35a-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="bd35a-380">WorkFoldersSyncUrl</span></span>
    

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="bd35a-381">モバイル デバイスをリモートからワイプする</span><span class="sxs-lookup"><span data-stu-id="bd35a-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="bd35a-382">デバイスが紛失または盗難にあった場合は、機密の組織データを削除し、セキュリティ & コンプライアンスセンター >**データ損失防止**  >  **デバイス管理**からのワイプを行って、Microsoft 365 組織のリソースにアクセスできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="bd35a-383">個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="bd35a-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="bd35a-384">詳細については、「 [Basic Mobility And Security でモバイルデバイスをワイプする](wipe-mobile-device.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd35a-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bd35a-385">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bd35a-385">Related topics</span></span>

[<span data-ttu-id="bd35a-386">Microsoft 365 の基本的なモビリティとセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="bd35a-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="bd35a-387">基本的なモビリティとセキュリティでデバイスのセキュリティポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="bd35a-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)