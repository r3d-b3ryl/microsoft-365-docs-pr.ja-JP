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
description: 基本的なモビリティとセキュリティは、モバイル デバイスのセキュリティ保護と管理に役立ちます。
ms.openlocfilehash: 468f06edf16eb6ea00fd4d26c716bc145474dd25
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904278"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="f77d9-103">基本的なモビリティとセキュリティの機能</span><span class="sxs-lookup"><span data-stu-id="f77d9-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="f77d9-104">Basic Mobility and Security は、組織内のライセンスを取得した Microsoft 365 ユーザーが使用する iPhone、iPad、Android、Windows Phone など、モバイル デバイスのセキュリティ保護と管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="f77d9-105">組織の Microsoft 365 メールへのアクセスを制御するのに役立つ設定と、サポートされているモバイル デバイスとアプリのドキュメントを使用して、モバイル デバイス管理ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="f77d9-106">デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="f77d9-107">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="f77d9-107">Supported devices</span></span>

<span data-ttu-id="f77d9-108">Basic Mobility and Security を使用すると、次のデバイスをセキュリティで保護および管理できます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="f77d9-109">iOS 11.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="f77d9-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="f77d9-110">Android 5.0 以降のバージョン<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f77d9-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="f77d9-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f77d9-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="f77d9-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f77d9-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="f77d9-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f77d9-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="f77d9-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f77d9-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="f77d9-115"><sup>1</sup>Windows 8.1 RT デバイスのアクセス制御は、1 つの RT デバイスExchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="f77d9-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="f77d9-116"><sup>2</sup>Windows 8.1 RT デバイスのアクセス制御は、1 つの RT デバイスExchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="f77d9-116"><sup>2</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="f77d9-117">Windows 10 のアクセス制御には、Azure AD Premium を含むサブスクリプションが必要で、デバイスを Azure Active Directory に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f77d9-117">Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="f77d9-118"><sup>3</sup>Windows 8.1 RT デバイスのアクセス制御は、1 つの RT デバイスExchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="f77d9-118"><sup>3</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>
<span data-ttu-id="f77d9-119">2020 年 6 月以降、9 より後の Android バージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。</span><span class="sxs-lookup"><span data-stu-id="f77d9-119">After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="f77d9-120">以前の OS バージョンで既に登録されているデバイスは引き続き機能しますが、機能は予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f77d9-120">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="f77d9-121">組織内のユーザーが基本モビリティとセキュリティでサポートされていないモバイル デバイスを使用している場合は、組織のデータをより安全にするために、これらのデバイスの Microsoft 365 メールへの Exchange ActiveSync アプリアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-121">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="f77d9-122">デバイスアクセスをブロックするExchange ActiveSync、「Basic Mobility and Security」の「デバイス アクセス設定の [管理」を参照してください](manage-device-access-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="f77d9-122">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="f77d9-123">Microsoft 365 の電子メールとドキュメントのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="f77d9-123">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="f77d9-124">次の表に示すさまざまな種類のモバイル デバイスでサポートされているアプリは、ユーザーのデバイスに適用される新しいモバイル デバイス管理ポリシーが作成され、ユーザーがデバイスを以前に登録しなかった場合に、Basic Mobility and Security に登録するようユーザーに求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f77d9-124">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="f77d9-125">ポリシーの設定方法によっては、ユーザーのデバイスがポリシーに準拠しない場合、ユーザーがこれらのアプリの Microsoft 365 リソースにアクセスできないか、アクセス権を持っている可能性がありますが、Microsoft 365 はポリシー違反を報告します。</span><span class="sxs-lookup"><span data-stu-id="f77d9-125">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="f77d9-126">**製品**</span><span class="sxs-lookup"><span data-stu-id="f77d9-126">**Product**</span></span>|<span data-ttu-id="f77d9-127">**iOS 10.0 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-127">**iOS 10.0 or later**</span></span>|<span data-ttu-id="f77d9-128">**Android 5.0 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-128">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-129">**Exchange** Exchange ActiveSyncには、バージョン 14.1 以降を使用する組み込みの電子メールアプリと、TouchDown Exchange ActiveSyncサード パーティ製アプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-129">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="f77d9-130">メール</span><span class="sxs-lookup"><span data-stu-id="f77d9-130">Mail</span></span> |<span data-ttu-id="f77d9-131">メール</span><span class="sxs-lookup"><span data-stu-id="f77d9-131">Email</span></span> |
|<span data-ttu-id="f77d9-132">**Office**   **および OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="f77d9-132">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="f77d9-133">Outlook</span><span class="sxs-lookup"><span data-stu-id="f77d9-133">Outlook</span></span> </br><span data-ttu-id="f77d9-134">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f77d9-134">OneDrive</span></span> </br><span data-ttu-id="f77d9-135">Word</span><span class="sxs-lookup"><span data-stu-id="f77d9-135">Word</span></span> </br><span data-ttu-id="f77d9-136">Excel</span><span class="sxs-lookup"><span data-stu-id="f77d9-136">Excel</span></span> </br><span data-ttu-id="f77d9-137">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f77d9-137">PowerPoint</span></span>|<span data-ttu-id="f77d9-138">**電話とタブレットの場合**:</span><span class="sxs-lookup"><span data-stu-id="f77d9-138">**On phones and tablets**:</span></span><br/><span data-ttu-id="f77d9-139">Outlook</span><span class="sxs-lookup"><span data-stu-id="f77d9-139">Outlook</span></span> <br/> <span data-ttu-id="f77d9-140">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f77d9-140">OneDrive</span></span> <br/> <span data-ttu-id="f77d9-141">Word</span><span class="sxs-lookup"><span data-stu-id="f77d9-141">Word</span></span> <br/> <span data-ttu-id="f77d9-142">Excel</span><span class="sxs-lookup"><span data-stu-id="f77d9-142">Excel</span></span> <br/> <span data-ttu-id="f77d9-143">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f77d9-143">PowerPoint</span></span> <br/> <span data-ttu-id="f77d9-144">**電話のみ:**</span><span class="sxs-lookup"><span data-stu-id="f77d9-144">**On phones only:**</span></span> <br/> <span data-ttu-id="f77d9-145">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="f77d9-145">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="f77d9-146">iOS 10.0 以降のバージョンのサポートには、iPhone デバイスと iPad デバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-146">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="f77d9-147">BlackBerry OS デバイスの管理は、Basic Security および Mobility ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f77d9-147">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="f77d9-148">BlackBerry の BlackBerry Business Cloud Services (BBCS) を使用して、BlackBerry OS デバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="f77d9-148">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="f77d9-149">Android OS を実行している Blackberry デバイスは、標準の Android デバイスとしてサポートされています</span><span class="sxs-lookup"><span data-stu-id="f77d9-149">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="f77d9-150">モバイル ブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online のドキュメント、または Outlook Web App の電子メールにアクセスする場合、ユーザーは登録を求めるメッセージが表示され、ポリシー違反に対してブロックまたは報告されません。</span><span class="sxs-lookup"><span data-stu-id="f77d9-150">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="f77d9-151">次の図は、新しいデバイスを持つユーザーが、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインした場合の処理を示しています。</span><span class="sxs-lookup"><span data-stu-id="f77d9-151">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="f77d9-152">ユーザーがデバイスを登録するまで、アプリ内の Microsoft 365 リソースへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-152">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティとセキュリティ アクセス制御":::

> [!NOTE]
> <span data-ttu-id="f77d9-154">Microsoft 365 Business Standard の Basic Mobility and Security で作成されたポリシーとアクセス ルールは、Exchange 管理センターで作成された Exchange ActiveSync モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールを上書きします。</span><span class="sxs-lookup"><span data-stu-id="f77d9-154">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="f77d9-155">デバイスが Microsoft 365 Business Standard の Basic Mobility and Security に登録されると、デバイスに適用される Exchange ActiveSync モバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-155">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="f77d9-156">このページの詳細については、「Exchange ActiveSync Exchange [Online Exchange ActiveSync」を参照してください](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)。</span><span class="sxs-lookup"><span data-stu-id="f77d9-156">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="f77d9-157">モバイル デバイス用のポリシー設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-157">Policy settings for mobile devices</span></span>

<span data-ttu-id="f77d9-158">特定の設定を有効にした状態でアクセスをブロックするポリシーを作成すると [、Microsoft 365](capabilities.md)の電子メールとドキュメントのアクセス制御に記載されているサポートされているアプリを使用すると、ユーザーは Microsoft 365 リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-158">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="f77d9-159">ユーザーが Microsoft 365 リソースにアクセスをブロックできる設定は、次のセクションに示されています。</span><span class="sxs-lookup"><span data-stu-id="f77d9-159">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="f77d9-160">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f77d9-160">Security</span></span>

- <span data-ttu-id="f77d9-161">暗号化</span><span class="sxs-lookup"><span data-stu-id="f77d9-161">Encryption</span></span>

- <span data-ttu-id="f77d9-162">脱獄</span><span class="sxs-lookup"><span data-stu-id="f77d9-162">Jail broken</span></span>

- <span data-ttu-id="f77d9-163">管理された電子メール プロファイル</span><span class="sxs-lookup"><span data-stu-id="f77d9-163">Managed email profile</span></span>  

<span data-ttu-id="f77d9-164">例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="f77d9-164">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="f77d9-165">ユーザーは、Basic Mobility and Security を使用してアクセス制御をサポートするアプリにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f77d9-165">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="f77d9-166">デバイスがセキュリティ設定に準拠するまで、アプリ内の Microsoft 365 リソースへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-166">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Basic Mobility and Security compliance message":::

<span data-ttu-id="f77d9-168">次のセクションでは、Microsoft 365 組織リソースに接続するモバイル デバイスのセキュリティ保護と管理に使用できるポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="f77d9-168">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="f77d9-169">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-169">Security settings</span></span>

|<span data-ttu-id="f77d9-170">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-170">**Setting name**</span></span>|<span data-ttu-id="f77d9-171">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-171">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-172">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-172">**Android 5 and later**</span></span>|<span data-ttu-id="f77d9-173">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="f77d9-173">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-174">パスワードを要求</span><span class="sxs-lookup"><span data-stu-id="f77d9-174">Require a password</span></span>|<span data-ttu-id="f77d9-175">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-175">Yes</span></span>|<span data-ttu-id="f77d9-176">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-176">Yes</span></span>|<span data-ttu-id="f77d9-177">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-177">Yes</span></span>|
|<span data-ttu-id="f77d9-178">シンプルなパスワードを禁止</span><span class="sxs-lookup"><span data-stu-id="f77d9-178">Prevent simple password</span></span>|<span data-ttu-id="f77d9-179">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-179">Yes</span></span>|<span data-ttu-id="f77d9-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-180">No</span></span>|<span data-ttu-id="f77d9-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-181">No</span></span>|
|<span data-ttu-id="f77d9-182">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="f77d9-182">Require an alphanumeric password</span></span>|<span data-ttu-id="f77d9-183">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-183">Yes</span></span>|<span data-ttu-id="f77d9-184">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-184">No</span></span>|<span data-ttu-id="f77d9-185">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-185">No</span></span>|
|<span data-ttu-id="f77d9-186">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="f77d9-186">Minimum password length</span></span> |<span data-ttu-id="f77d9-187">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-187">Yes</span></span>|<span data-ttu-id="f77d9-188">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-188">Yes</span></span>|<span data-ttu-id="f77d9-189">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-189">Yes</span></span>|
|<span data-ttu-id="f77d9-190">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="f77d9-190">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="f77d9-191">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-191">Yes</span></span>|<span data-ttu-id="f77d9-192">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-192">Yes</span></span>|<span data-ttu-id="f77d9-193">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-193">Yes</span></span>|
|<span data-ttu-id="f77d9-194">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="f77d9-194">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="f77d9-195">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-195">Yes</span></span>|<span data-ttu-id="f77d9-196">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-196">Yes</span></span>|<span data-ttu-id="f77d9-197">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-197">Yes</span></span>|
|<span data-ttu-id="f77d9-198">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="f77d9-198">Password expiration (days)</span></span> |<span data-ttu-id="f77d9-199">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-199">Yes</span></span>|<span data-ttu-id="f77d9-200">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-200">Yes</span></span>|<span data-ttu-id="f77d9-201">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-201">Yes</span></span>|
|<span data-ttu-id="f77d9-202">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="f77d9-202">Remember password history and prevent reuse</span></span> |<span data-ttu-id="f77d9-203">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-203">Yes</span></span>|<span data-ttu-id="f77d9-204">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-204">Yes</span></span>|<span data-ttu-id="f77d9-205">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-205">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="f77d9-206">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-206">Encryption settings</span></span>

|<span data-ttu-id="f77d9-207">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-207">**Setting name**</span></span>|<span data-ttu-id="f77d9-208">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-208">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-209">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-209">**Android 5 and later**</span></span>|<span data-ttu-id="f77d9-210">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="f77d9-210">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-211">デバイスでデータ暗号化を要求<sup>する 1</sup></span><span class="sxs-lookup"><span data-stu-id="f77d9-211">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="f77d9-212">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-212">No</span></span>|<span data-ttu-id="f77d9-213">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-213">Yes</span></span>|<span data-ttu-id="f77d9-214">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-214">Yes</span></span>|

<span data-ttu-id="f77d9-215"><sup>1</sup>Samsung Knox を使用すると、ストレージ カードで暗号化を要求できます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-215"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="f77d9-216">脱獄の設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-216">Jail broken setting</span></span> 

|<span data-ttu-id="f77d9-217">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-217">**Setting name**</span></span>|<span data-ttu-id="f77d9-218">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-218">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-219">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-219">**Android 5 and later**</span></span>|<span data-ttu-id="f77d9-220">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="f77d9-220">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-221">デバイスの脱獄またはルート化はできません</span><span class="sxs-lookup"><span data-stu-id="f77d9-221">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="f77d9-222">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-222">Yes</span></span>|<span data-ttu-id="f77d9-223">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-223">Yes</span></span>|<span data-ttu-id="f77d9-224">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-224">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="f77d9-225">管理された電子メール プロファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="f77d9-225">Managed email profile option</span></span> 

<span data-ttu-id="f77d9-226">次のオプションは、手動で作成したメール プロファイルを使用している場合、ユーザーが Microsoft 365 メールにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="f77d9-226">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="f77d9-227">iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f77d9-227">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="f77d9-228">プロファイルを削除すると、新しいプロファイルがデバイスに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-228">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="f77d9-229">エンド ユーザーが準拠を取得する方法については、「既存の電子メール アカウントが見つかりました [」を参照してください](/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="f77d9-229">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="f77d9-230">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-230">**Setting name**</span></span>|<span data-ttu-id="f77d9-231">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-231">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-232">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-232">**Android 5 and later**</span></span>|<span data-ttu-id="f77d9-233">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="f77d9-233">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-234">電子メール プロファイルが管理されている</span><span class="sxs-lookup"><span data-stu-id="f77d9-234">Email profile is managed</span></span> |<span data-ttu-id="f77d9-235">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-235">Yes</span></span>|<span data-ttu-id="f77d9-236">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-236">No</span></span>|<span data-ttu-id="f77d9-237">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-237">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="f77d9-238">クラウドの設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-238">Cloud settings</span></span>

|<span data-ttu-id="f77d9-239">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-239">**Setting name**</span></span>|<span data-ttu-id="f77d9-240">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-240">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-241">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-241">**Android 5 and later**</span></span>|<span data-ttu-id="f77d9-242">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="f77d9-242">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-243">暗号化されたバックアップを要求</span><span class="sxs-lookup"><span data-stu-id="f77d9-243">Require encrypted backup</span></span> |<span data-ttu-id="f77d9-244">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-244">Yes</span></span>|<span data-ttu-id="f77d9-245">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-245">No</span></span>|<span data-ttu-id="f77d9-246">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-246">No</span></span>|
|<span data-ttu-id="f77d9-247">クラウド バックアップの禁止</span><span class="sxs-lookup"><span data-stu-id="f77d9-247">Block cloud backup</span></span> |<span data-ttu-id="f77d9-248">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-248">Yes</span></span>|<span data-ttu-id="f77d9-249">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-249">No</span></span>|<span data-ttu-id="f77d9-250">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-250">No</span></span>|
|<span data-ttu-id="f77d9-251">ドキュメントの同期の禁止</span><span class="sxs-lookup"><span data-stu-id="f77d9-251">Block document synchronization</span></span> |<span data-ttu-id="f77d9-252">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-252">Yes</span></span>|<span data-ttu-id="f77d9-253">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-253">No</span></span>|<span data-ttu-id="f77d9-254">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-254">No</span></span>|
|<span data-ttu-id="f77d9-255">写真の同期の禁止</span><span class="sxs-lookup"><span data-stu-id="f77d9-255">Block photo synchronization</span></span>  |<span data-ttu-id="f77d9-256">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-256">Yes</span></span>|<span data-ttu-id="f77d9-257">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-257">No</span></span>|<span data-ttu-id="f77d9-258">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-258">No</span></span>|
|<span data-ttu-id="f77d9-259">Google バックアップを許可する</span><span class="sxs-lookup"><span data-stu-id="f77d9-259">Allow Google backup</span></span>  |<span data-ttu-id="f77d9-260">該当なし</span><span class="sxs-lookup"><span data-stu-id="f77d9-260">N/A</span></span>|<span data-ttu-id="f77d9-261">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-261">No</span></span>|<span data-ttu-id="f77d9-262">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-262">Yes</span></span>|
|<span data-ttu-id="f77d9-263">Google アカウントの自動同期を許可する</span><span class="sxs-lookup"><span data-stu-id="f77d9-263">Allow Google account auto sync</span></span>  |<span data-ttu-id="f77d9-264">該当なし</span><span class="sxs-lookup"><span data-stu-id="f77d9-264">N/A</span></span>|<span data-ttu-id="f77d9-265">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-265">No</span></span>|<span data-ttu-id="f77d9-266">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-266">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="f77d9-267">システムの設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-267">System settings</span></span>

|<span data-ttu-id="f77d9-268">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-268">**Setting name**</span></span>|<span data-ttu-id="f77d9-269">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-269">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-270">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-270">**Android 5 and later**</span></span>|<span data-ttu-id="f77d9-271">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="f77d9-271">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-272">画面キャプチャの禁止</span><span class="sxs-lookup"><span data-stu-id="f77d9-272">Block screen capture</span></span> |<span data-ttu-id="f77d9-273">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-273">Yes</span></span>|<span data-ttu-id="f77d9-274">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-274">No</span></span>|<span data-ttu-id="f77d9-275">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-275">Yes</span></span>|
|<span data-ttu-id="f77d9-276">デバイスからの診断データ送信の禁止</span><span class="sxs-lookup"><span data-stu-id="f77d9-276">Block sending diagnostic data from device</span></span> |<span data-ttu-id="f77d9-277">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-277">Yes</span></span>|<span data-ttu-id="f77d9-278">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-278">No</span></span>|<span data-ttu-id="f77d9-279">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-279">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="f77d9-280">アプリケーションの設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-280">Application settings</span></span>

|<span data-ttu-id="f77d9-281">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-281">**Setting name**</span></span>|<span data-ttu-id="f77d9-282">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-282">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-283">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-283">**Android 5 and later**</span></span>|<span data-ttu-id="f77d9-284">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="f77d9-284">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-285">デバイスでのビデオ会議をブロックする</span><span class="sxs-lookup"><span data-stu-id="f77d9-285">Block video conferences on device</span></span> |<span data-ttu-id="f77d9-286">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-286">Yes</span></span>|<span data-ttu-id="f77d9-287">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-287">No</span></span>|<span data-ttu-id="f77d9-288">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-288">No</span></span>|
|<span data-ttu-id="f77d9-289">アプリケーション ストアへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="f77d9-289">Block access to application store</span></span> |<span data-ttu-id="f77d9-290">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-290">Yes</span></span>|<span data-ttu-id="f77d9-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-291">No</span></span>|<span data-ttu-id="f77d9-292">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-292">Yes</span></span>|
|<span data-ttu-id="f77d9-293">アプリケーション ストアへアクセスする際にパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="f77d9-293">Require password when accessing application store</span></span> |<span data-ttu-id="f77d9-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-294">No</span></span>|<span data-ttu-id="f77d9-295">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-295">Yes</span></span>|<span data-ttu-id="f77d9-296">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-296">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="f77d9-297">デバイスの機能の設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-297">Device capabilities settings</span></span>

|<span data-ttu-id="f77d9-298">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-298">**Setting name**</span></span>|<span data-ttu-id="f77d9-299">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-299">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-300">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-300">**Android 5 and later**</span></span>|<span data-ttu-id="f77d9-301">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="f77d9-301">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-302">リムーバブル記憶域との接続の禁止</span><span class="sxs-lookup"><span data-stu-id="f77d9-302">Block connection with removable storage</span></span> |<span data-ttu-id="f77d9-303">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-303">Yes</span></span>|<span data-ttu-id="f77d9-304">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-304">Yes</span></span>|<span data-ttu-id="f77d9-305">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-305">No</span></span>|
|<span data-ttu-id="f77d9-306">Bluetooth 接続の禁止</span><span class="sxs-lookup"><span data-stu-id="f77d9-306">Block Bluetooth connection</span></span> |<span data-ttu-id="f77d9-307">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-307">Yes</span></span>|<span data-ttu-id="f77d9-308">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-308">Yes</span></span>|<span data-ttu-id="f77d9-309">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-309">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="f77d9-310">その他の設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-310">Additional settings</span></span>

<span data-ttu-id="f77d9-311">コンプライアンス センター PowerShell コマンドレットを使用して、次の&ポリシー設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-311">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="f77d9-312">詳細については、「Security [& コンプライアンス センター PowerShell」を参照してください](/powershell/exchange/scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f77d9-312">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="f77d9-313">**設定名**</span><span class="sxs-lookup"><span data-stu-id="f77d9-313">**Setting name**</span></span>|<span data-ttu-id="f77d9-314">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-314">**iOS 7.1 and later**</span></span>|<span data-ttu-id="f77d9-315">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="f77d9-315">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f77d9-316">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="f77d9-316">CameraEnabled</span></span>|<span data-ttu-id="f77d9-317">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-317">Yes</span></span>|<span data-ttu-id="f77d9-318">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-318">Yes</span></span>|
|<span data-ttu-id="f77d9-319">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="f77d9-319">RegionRatings</span></span>|<span data-ttu-id="f77d9-320">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-320">Yes</span></span>|<span data-ttu-id="f77d9-321">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-321">No</span></span>|
|<span data-ttu-id="f77d9-322">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="f77d9-322">MoviesRatings</span></span>|<span data-ttu-id="f77d9-323">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-323">Yes</span></span>|<span data-ttu-id="f77d9-324">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-324">No</span></span>|
|<span data-ttu-id="f77d9-325">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="f77d9-325">TVShowsRating</span></span> |<span data-ttu-id="f77d9-326">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-326">Yes</span></span>|<span data-ttu-id="f77d9-327">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-327">No</span></span>|
|<span data-ttu-id="f77d9-328">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="f77d9-328">AppsRatings</span></span> |<span data-ttu-id="f77d9-329">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-329">Yes</span></span>|<span data-ttu-id="f77d9-330">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-330">No</span></span>|
|<span data-ttu-id="f77d9-331">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="f77d9-331">AllowVoiceDialing</span></span> |<span data-ttu-id="f77d9-332">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-332">Yes</span></span>|<span data-ttu-id="f77d9-333">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-333">No</span></span>|
|<span data-ttu-id="f77d9-334">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="f77d9-334">AllowVoiceAssistant</span></span> |<span data-ttu-id="f77d9-335">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-335">Yes</span></span>|<span data-ttu-id="f77d9-336">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-336">No</span></span>|
|<span data-ttu-id="f77d9-337">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="f77d9-337">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="f77d9-338">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-338">Yes</span></span>|<span data-ttu-id="f77d9-339">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-339">No</span></span>|
|<span data-ttu-id="f77d9-340">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="f77d9-340">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="f77d9-341">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-341">Yes</span></span>|<span data-ttu-id="f77d9-342">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-342">No</span></span>|
|<span data-ttu-id="f77d9-343">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="f77d9-343">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="f77d9-344">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-344">Yes</span></span>|<span data-ttu-id="f77d9-345">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-345">No</span></span>|
|<span data-ttu-id="f77d9-346">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="f77d9-346">PasswordQuality</span></span> |<span data-ttu-id="f77d9-347">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-347">No</span></span>|<span data-ttu-id="f77d9-348">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-348">Yes</span></span>|
|<span data-ttu-id="f77d9-349">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="f77d9-349">SystemSecurityTLS</span></span>  |<span data-ttu-id="f77d9-350">はい</span><span class="sxs-lookup"><span data-stu-id="f77d9-350">Yes</span></span>|<span data-ttu-id="f77d9-351">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-351">No</span></span>|
|<span data-ttu-id="f77d9-352">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="f77d9-352">WLANEnabled</span></span>  |<span data-ttu-id="f77d9-353">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-353">No</span></span>|<span data-ttu-id="f77d9-354">いいえ</span><span class="sxs-lookup"><span data-stu-id="f77d9-354">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="f77d9-355">Windows でサポートされる設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-355">Settings supported by Windows</span></span>

<span data-ttu-id="f77d9-356">Windows 10 デバイスは、モバイル デバイスとして登録することで管理できます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-356">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="f77d9-357">該当するポリシーが展開された後、Windows 10 デバイスを使用するユーザーは、組み込みの電子メール アプリを初めて使用して Microsoft 365 メールにアクセスする際に、Basic Mobility and Security に登録する必要があります (Azure AD プレミアム サブスクリプションが必要です)。</span><span class="sxs-lookup"><span data-stu-id="f77d9-357">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="f77d9-358">モバイル デバイスとして登録されている Windows 10 デバイスでは、次の設定がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f77d9-358">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="f77d9-359">これらの設定では、ユーザーが Microsoft 365 リソースにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f77d9-359">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="f77d9-360">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-360">Security settings</span></span>

- <span data-ttu-id="f77d9-361">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="f77d9-361">Require an alphanumeric password</span></span>

- <span data-ttu-id="f77d9-362">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="f77d9-362">Minimum password length</span></span>

- <span data-ttu-id="f77d9-363">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="f77d9-363">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="f77d9-364">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="f77d9-364">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="f77d9-365">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="f77d9-365">Password expiration (days)</span></span>

- <span data-ttu-id="f77d9-366">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="f77d9-366">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="f77d9-367">パスワードを調整する次の設定では、ローカル Windows アカウントのみを制御します。</span><span class="sxs-lookup"><span data-stu-id="f77d9-367">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="f77d9-368">ドメインまたは Azure Active Directory に参加して提供される Windows アカウントは、これらの設定の影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="f77d9-368">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="f77d9-369">システムの設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-369">System settings</span></span>

<span data-ttu-id="f77d9-370">デバイスからの診断データの送信をブロックします。</span><span class="sxs-lookup"><span data-stu-id="f77d9-370">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="f77d9-371">その他の設定</span><span class="sxs-lookup"><span data-stu-id="f77d9-371">Additional settings</span></span>

<span data-ttu-id="f77d9-372">PowerShell コマンドレットを使用して、次の追加のポリシー設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-372">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="f77d9-373">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="f77d9-373">AllowConvenienceLogon</span></span>

- <span data-ttu-id="f77d9-374">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="f77d9-374">UserAccountControlStatus</span></span>

- <span data-ttu-id="f77d9-375">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="f77d9-375">FirewallStatus</span></span>

- <span data-ttu-id="f77d9-376">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="f77d9-376">AutoUpdateStatus</span></span>

- <span data-ttu-id="f77d9-377">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="f77d9-377">AntiVirusStatus</span></span>

- <span data-ttu-id="f77d9-378">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="f77d9-378">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="f77d9-379">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="f77d9-379">SmartScreenEnabled</span></span>

- <span data-ttu-id="f77d9-380">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="f77d9-380">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="f77d9-381">モバイル デバイスをリモートからワイプする</span><span class="sxs-lookup"><span data-stu-id="f77d9-381">Remotely wipe a mobile device</span></span>

<span data-ttu-id="f77d9-382">デバイスが紛失または盗難に遭った場合は、機密の組織データを削除し、セキュリティ & コンプライアンス センター > データ損失防止デバイス管理からワイプを行って、Microsoft 365 組織リソースへのアクセスを防止できます。   >  </span><span class="sxs-lookup"><span data-stu-id="f77d9-382">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="f77d9-383">個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f77d9-383">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="f77d9-384">詳細については、「Basic [Mobility and Security」でモバイル デバイスをワイプするを参照してください](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="f77d9-384">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f77d9-385">関連項目</span><span class="sxs-lookup"><span data-stu-id="f77d9-385">Related topics</span></span>

[<span data-ttu-id="f77d9-386">Microsoft 365 の基本モビリティとセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="f77d9-386">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="f77d9-387">Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f77d9-387">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)