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
ms.openlocfilehash: 60de4e3f36427a69ecf0bf52e5dfd34f089991f3
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994975"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="a7c44-103">基本的なモビリティとセキュリティの機能</span><span class="sxs-lookup"><span data-stu-id="a7c44-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="a7c44-104">Basic Mobility and Security は、組織内のライセンスを取得した Microsoft 365 ユーザーが使用する iPhone、iPad、Android、Windows Phone など、モバイル デバイスのセキュリティ保護と管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="a7c44-105">組織の Microsoft 365 メールへのアクセスを制御するのに役立つ設定と、サポートされているモバイル デバイスとアプリのドキュメントを使用して、モバイル デバイス管理ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="a7c44-106">デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="a7c44-107">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="a7c44-107">Supported devices</span></span>

<span data-ttu-id="a7c44-108">Basic Mobility and Security を使用すると、次のデバイスをセキュリティで保護および管理できます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="a7c44-109">iOS 11.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="a7c44-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="a7c44-110">Android 5.0 以降のバージョン<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a7c44-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="a7c44-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7c44-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="a7c44-112">Windows 8.1 RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a7c44-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="a7c44-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7c44-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="a7c44-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a7c44-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="a7c44-115"><sup>1</sup>Windows 8.1 RT デバイスのアクセス制御は、1 つの RT デバイスExchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="a7c44-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="a7c44-116"><sup>2</sup>Windows 10 のアクセス制御には、Azure AD Premium を含むサブスクリプションが必要で、デバイスを Azure Active Directory に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c44-116"><sup>2</sup>Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="a7c44-117"><sup>3</sup>2020 年 6 月以降、9 より後の Android バージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。</span><span class="sxs-lookup"><span data-stu-id="a7c44-117"><sup>3</sup>After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

>[!NOTE]
><span data-ttu-id="a7c44-118">以前の OS バージョンで既に登録されているデバイスは引き続き機能しますが、機能は予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7c44-118">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="a7c44-119">組織内のユーザーが基本モビリティとセキュリティでサポートされていないモバイル デバイスを使用している場合は、組織のデータをより安全にするために、これらのデバイスの Microsoft 365 メールへの Exchange ActiveSync アプリアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-119">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="a7c44-120">デバイスアクセスをブロックするExchange ActiveSync、「Basic Mobility and Security」の「デバイス アクセス設定の [管理」を参照してください](manage-device-access-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="a7c44-120">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="a7c44-121">Microsoft 365 の電子メールとドキュメントのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="a7c44-121">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="a7c44-122">次の表に示すさまざまな種類のモバイル デバイスでサポートされているアプリは、ユーザーのデバイスに適用される新しいモバイル デバイス管理ポリシーが作成され、ユーザーがデバイスを以前に登録しなかった場合に、Basic Mobility and Security に登録するようユーザーに求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="a7c44-122">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="a7c44-123">ポリシーの設定方法によっては、ユーザーのデバイスがポリシーに準拠しない場合、ユーザーがこれらのアプリの Microsoft 365 リソースにアクセスできないか、アクセス権を持っている可能性がありますが、Microsoft 365 はポリシー違反を報告します。</span><span class="sxs-lookup"><span data-stu-id="a7c44-123">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="a7c44-124">**Product**</span><span class="sxs-lookup"><span data-stu-id="a7c44-124">**Product**</span></span>|<span data-ttu-id="a7c44-125">**iOS 10.0 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-125">**iOS 10.0 or later**</span></span>|<span data-ttu-id="a7c44-126">**Android 5.0 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-126">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-127">**Exchange** Exchange ActiveSyncには、バージョン 14.1 以降を使用する組み込みの電子メールアプリと、TouchDown Exchange ActiveSyncサード パーティ製アプリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-127">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="a7c44-128">メール</span><span class="sxs-lookup"><span data-stu-id="a7c44-128">Mail</span></span> |<span data-ttu-id="a7c44-129">メール</span><span class="sxs-lookup"><span data-stu-id="a7c44-129">Email</span></span> |
|<span data-ttu-id="a7c44-130">**Office**   **および OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="a7c44-130">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="a7c44-131">Outlook</span><span class="sxs-lookup"><span data-stu-id="a7c44-131">Outlook</span></span> </br><span data-ttu-id="a7c44-132">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a7c44-132">OneDrive</span></span> </br><span data-ttu-id="a7c44-133">Word</span><span class="sxs-lookup"><span data-stu-id="a7c44-133">Word</span></span> </br><span data-ttu-id="a7c44-134">Excel</span><span class="sxs-lookup"><span data-stu-id="a7c44-134">Excel</span></span> </br><span data-ttu-id="a7c44-135">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a7c44-135">PowerPoint</span></span>|<span data-ttu-id="a7c44-136">**電話とタブレットの場合**:</span><span class="sxs-lookup"><span data-stu-id="a7c44-136">**On phones and tablets**:</span></span><br/><span data-ttu-id="a7c44-137">Outlook</span><span class="sxs-lookup"><span data-stu-id="a7c44-137">Outlook</span></span> <br/> <span data-ttu-id="a7c44-138">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a7c44-138">OneDrive</span></span> <br/> <span data-ttu-id="a7c44-139">Word</span><span class="sxs-lookup"><span data-stu-id="a7c44-139">Word</span></span> <br/> <span data-ttu-id="a7c44-140">Excel</span><span class="sxs-lookup"><span data-stu-id="a7c44-140">Excel</span></span> <br/> <span data-ttu-id="a7c44-141">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a7c44-141">PowerPoint</span></span> <br/> <span data-ttu-id="a7c44-142">**電話のみ:**</span><span class="sxs-lookup"><span data-stu-id="a7c44-142">**On phones only:**</span></span> <br/> <span data-ttu-id="a7c44-143">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="a7c44-143">Office Mobile</span></span> |

>[!NOTE]
- ><span data-ttu-id="a7c44-144">iOS 10.0 以降のバージョンのサポートには、iPhone デバイスと iPad デバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-144">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
- ><span data-ttu-id="a7c44-145">BlackBerry OS デバイスの管理は、Basic Security および Mobility ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a7c44-145">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="a7c44-146">BlackBerry の BlackBerry Business Cloud Services (BBCS) を使用して、BlackBerry OS デバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="a7c44-146">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="a7c44-147">Android OS を実行している Blackberry デバイスは、標準の Android デバイスとしてサポートされています</span><span class="sxs-lookup"><span data-stu-id="a7c44-147">Blackberry devices running Android OS are supported as standard Android devices</span></span>
- ><span data-ttu-id="a7c44-148">モバイル ブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online のドキュメント、または Outlook Web App の電子メールにアクセスする場合、ユーザーは登録を求めるメッセージが表示され、ポリシー違反に対してブロックまたは報告されません。</span><span class="sxs-lookup"><span data-stu-id="a7c44-148">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="a7c44-149">次の図は、新しいデバイスを持つユーザーが、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインした場合の処理を示しています。</span><span class="sxs-lookup"><span data-stu-id="a7c44-149">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="a7c44-150">ユーザーがデバイスを登録するまで、アプリ内の Microsoft 365 リソースへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-150">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティとセキュリティ アクセス制御":::

> [!NOTE]
> <span data-ttu-id="a7c44-152">Microsoft 365 Business Standard の Basic Mobility and Security で作成されたポリシーとアクセス ルールは、Exchange 管理センターで作成された Exchange ActiveSync モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールを上書きします。</span><span class="sxs-lookup"><span data-stu-id="a7c44-152">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="a7c44-153">デバイスが Microsoft 365 Business Standard の Basic Mobility and Security に登録されると、デバイスに適用される Exchange ActiveSync モバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-153">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="a7c44-154">このページの詳細については、「Exchange ActiveSync Exchange [Online Exchange ActiveSync」を参照してください](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)。</span><span class="sxs-lookup"><span data-stu-id="a7c44-154">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="a7c44-155">モバイル デバイス用のポリシー設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-155">Policy settings for mobile devices</span></span>

<span data-ttu-id="a7c44-156">特定の設定を有効にした状態でアクセスをブロックするポリシーを作成すると [、Microsoft 365](capabilities.md)の電子メールとドキュメントのアクセス制御に記載されているサポートされているアプリを使用すると、ユーザーは Microsoft 365 リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-156">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span> 

<span data-ttu-id="a7c44-157">ユーザーが Microsoft 365 リソースにアクセスをブロックできる設定は、次のセクションに示されています。</span><span class="sxs-lookup"><span data-stu-id="a7c44-157">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="a7c44-158">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="a7c44-158">Security</span></span>

- <span data-ttu-id="a7c44-159">暗号化</span><span class="sxs-lookup"><span data-stu-id="a7c44-159">Encryption</span></span>

- <span data-ttu-id="a7c44-160">脱獄</span><span class="sxs-lookup"><span data-stu-id="a7c44-160">Jail broken</span></span>

- <span data-ttu-id="a7c44-161">管理された電子メール プロファイル</span><span class="sxs-lookup"><span data-stu-id="a7c44-161">Managed email profile</span></span>  

<span data-ttu-id="a7c44-162">例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="a7c44-162">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="a7c44-163">ユーザーは、Basic Mobility and Security を使用してアクセス制御をサポートするアプリにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a7c44-163">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="a7c44-164">デバイスがセキュリティ設定に準拠するまで、アプリ内の Microsoft 365 リソースへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-164">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Basic Mobility and Security compliance message":::

<span data-ttu-id="a7c44-166">次のセクションでは、Microsoft 365 組織リソースに接続するモバイル デバイスのセキュリティ保護と管理に使用できるポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="a7c44-166">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="a7c44-167">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-167">Security settings</span></span>

|<span data-ttu-id="a7c44-168">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-168">**Setting name**</span></span>|<span data-ttu-id="a7c44-169">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-169">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-170">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-170">**Android 5 and later**</span></span>|<span data-ttu-id="a7c44-171">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="a7c44-171">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-172">パスワードを要求</span><span class="sxs-lookup"><span data-stu-id="a7c44-172">Require a password</span></span>|<span data-ttu-id="a7c44-173">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-173">Yes</span></span>|<span data-ttu-id="a7c44-174">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-174">Yes</span></span>|<span data-ttu-id="a7c44-175">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-175">Yes</span></span>|
|<span data-ttu-id="a7c44-176">シンプルなパスワードを禁止</span><span class="sxs-lookup"><span data-stu-id="a7c44-176">Prevent simple password</span></span>|<span data-ttu-id="a7c44-177">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-177">Yes</span></span>|<span data-ttu-id="a7c44-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-178">No</span></span>|<span data-ttu-id="a7c44-179">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-179">No</span></span>|
|<span data-ttu-id="a7c44-180">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="a7c44-180">Require an alphanumeric password</span></span>|<span data-ttu-id="a7c44-181">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-181">Yes</span></span>|<span data-ttu-id="a7c44-182">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-182">No</span></span>|<span data-ttu-id="a7c44-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-183">No</span></span>|
|<span data-ttu-id="a7c44-184">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="a7c44-184">Minimum password length</span></span> |<span data-ttu-id="a7c44-185">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-185">Yes</span></span>|<span data-ttu-id="a7c44-186">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-186">Yes</span></span>|<span data-ttu-id="a7c44-187">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-187">Yes</span></span>|
|<span data-ttu-id="a7c44-188">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="a7c44-188">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="a7c44-189">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-189">Yes</span></span>|<span data-ttu-id="a7c44-190">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-190">Yes</span></span>|<span data-ttu-id="a7c44-191">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-191">Yes</span></span>|
|<span data-ttu-id="a7c44-192">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="a7c44-192">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="a7c44-193">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-193">Yes</span></span>|<span data-ttu-id="a7c44-194">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-194">Yes</span></span>|<span data-ttu-id="a7c44-195">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-195">Yes</span></span>|
|<span data-ttu-id="a7c44-196">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="a7c44-196">Password expiration (days)</span></span> |<span data-ttu-id="a7c44-197">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-197">Yes</span></span>|<span data-ttu-id="a7c44-198">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-198">Yes</span></span>|<span data-ttu-id="a7c44-199">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-199">Yes</span></span>|
|<span data-ttu-id="a7c44-200">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="a7c44-200">Remember password history and prevent reuse</span></span> |<span data-ttu-id="a7c44-201">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-201">Yes</span></span>|<span data-ttu-id="a7c44-202">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-202">Yes</span></span>|<span data-ttu-id="a7c44-203">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-203">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="a7c44-204">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-204">Encryption settings</span></span>

|<span data-ttu-id="a7c44-205">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-205">**Setting name**</span></span>|<span data-ttu-id="a7c44-206">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-206">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-207">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-207">**Android 5 and later**</span></span>|<span data-ttu-id="a7c44-208">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="a7c44-208">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-209">デバイスでデータ暗号化を要求<sup>する 1</sup></span><span class="sxs-lookup"><span data-stu-id="a7c44-209">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="a7c44-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-210">No</span></span>|<span data-ttu-id="a7c44-211">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-211">Yes</span></span>|<span data-ttu-id="a7c44-212">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-212">Yes</span></span>|

<span data-ttu-id="a7c44-213"><sup>1</sup>Samsung Knox を使用すると、ストレージ カードで暗号化を要求できます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-213"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span> 

## <a name="jail-broken-setting"></a><span data-ttu-id="a7c44-214">脱獄の設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-214">Jail broken setting</span></span> 

|<span data-ttu-id="a7c44-215">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-215">**Setting name**</span></span>|<span data-ttu-id="a7c44-216">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-216">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-217">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-217">**Android 5 and later**</span></span>|<span data-ttu-id="a7c44-218">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="a7c44-218">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-219">デバイスの脱獄またはルート化はできません</span><span class="sxs-lookup"><span data-stu-id="a7c44-219">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="a7c44-220">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-220">Yes</span></span>|<span data-ttu-id="a7c44-221">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-221">Yes</span></span>|<span data-ttu-id="a7c44-222">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-222">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="a7c44-223">管理された電子メール プロファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="a7c44-223">Managed email profile option</span></span> 

<span data-ttu-id="a7c44-224">次のオプションは、手動で作成したメール プロファイルを使用している場合、ユーザーが Microsoft 365 メールにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a7c44-224">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="a7c44-225">iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c44-225">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="a7c44-226">プロファイルを削除すると、新しいプロファイルがデバイスに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-226">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="a7c44-227">エンド ユーザーが準拠を取得する方法については、「既存の電子メール アカウントが見つかりました [」を参照してください](/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="a7c44-227">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="a7c44-228">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-228">**Setting name**</span></span>|<span data-ttu-id="a7c44-229">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-229">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-230">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-230">**Android 5 and later**</span></span>|<span data-ttu-id="a7c44-231">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="a7c44-231">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-232">電子メール プロファイルが管理されている</span><span class="sxs-lookup"><span data-stu-id="a7c44-232">Email profile is managed</span></span> |<span data-ttu-id="a7c44-233">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-233">Yes</span></span>|<span data-ttu-id="a7c44-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-234">No</span></span>|<span data-ttu-id="a7c44-235">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-235">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="a7c44-236">クラウドの設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-236">Cloud settings</span></span>

|<span data-ttu-id="a7c44-237">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-237">**Setting name**</span></span>|<span data-ttu-id="a7c44-238">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-238">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-239">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-239">**Android 5 and later**</span></span>|<span data-ttu-id="a7c44-240">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="a7c44-240">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-241">暗号化されたバックアップを要求</span><span class="sxs-lookup"><span data-stu-id="a7c44-241">Require encrypted backup</span></span> |<span data-ttu-id="a7c44-242">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-242">Yes</span></span>|<span data-ttu-id="a7c44-243">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-243">No</span></span>|<span data-ttu-id="a7c44-244">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-244">No</span></span>|
|<span data-ttu-id="a7c44-245">クラウド バックアップの禁止</span><span class="sxs-lookup"><span data-stu-id="a7c44-245">Block cloud backup</span></span> |<span data-ttu-id="a7c44-246">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-246">Yes</span></span>|<span data-ttu-id="a7c44-247">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-247">No</span></span>|<span data-ttu-id="a7c44-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-248">No</span></span>|
|<span data-ttu-id="a7c44-249">ドキュメントの同期の禁止</span><span class="sxs-lookup"><span data-stu-id="a7c44-249">Block document synchronization</span></span> |<span data-ttu-id="a7c44-250">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-250">Yes</span></span>|<span data-ttu-id="a7c44-251">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-251">No</span></span>|<span data-ttu-id="a7c44-252">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-252">No</span></span>|
|<span data-ttu-id="a7c44-253">写真の同期の禁止</span><span class="sxs-lookup"><span data-stu-id="a7c44-253">Block photo synchronization</span></span>  |<span data-ttu-id="a7c44-254">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-254">Yes</span></span>|<span data-ttu-id="a7c44-255">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-255">No</span></span>|<span data-ttu-id="a7c44-256">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-256">No</span></span>|
|<span data-ttu-id="a7c44-257">Google バックアップを許可する</span><span class="sxs-lookup"><span data-stu-id="a7c44-257">Allow Google backup</span></span>  |<span data-ttu-id="a7c44-258">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7c44-258">N/A</span></span>|<span data-ttu-id="a7c44-259">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-259">No</span></span>|<span data-ttu-id="a7c44-260">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-260">Yes</span></span>|
|<span data-ttu-id="a7c44-261">Google アカウントの自動同期を許可する</span><span class="sxs-lookup"><span data-stu-id="a7c44-261">Allow Google account auto sync</span></span>  |<span data-ttu-id="a7c44-262">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7c44-262">N/A</span></span>|<span data-ttu-id="a7c44-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-263">No</span></span>|<span data-ttu-id="a7c44-264">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-264">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="a7c44-265">システムの設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-265">System settings</span></span>

|<span data-ttu-id="a7c44-266">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-266">**Setting name**</span></span>|<span data-ttu-id="a7c44-267">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-267">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-268">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-268">**Android 5 and later**</span></span>|<span data-ttu-id="a7c44-269">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="a7c44-269">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-270">画面キャプチャの禁止</span><span class="sxs-lookup"><span data-stu-id="a7c44-270">Block screen capture</span></span> |<span data-ttu-id="a7c44-271">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-271">Yes</span></span>|<span data-ttu-id="a7c44-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-272">No</span></span>|<span data-ttu-id="a7c44-273">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-273">Yes</span></span>|
|<span data-ttu-id="a7c44-274">デバイスからの診断データ送信の禁止</span><span class="sxs-lookup"><span data-stu-id="a7c44-274">Block sending diagnostic data from device</span></span> |<span data-ttu-id="a7c44-275">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-275">Yes</span></span>|<span data-ttu-id="a7c44-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-276">No</span></span>|<span data-ttu-id="a7c44-277">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-277">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="a7c44-278">アプリケーションの設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-278">Application settings</span></span>

|<span data-ttu-id="a7c44-279">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-279">**Setting name**</span></span>|<span data-ttu-id="a7c44-280">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-280">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-281">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-281">**Android 5 and later**</span></span>|<span data-ttu-id="a7c44-282">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="a7c44-282">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-283">デバイスでのビデオ会議をブロックする</span><span class="sxs-lookup"><span data-stu-id="a7c44-283">Block video conferences on device</span></span> |<span data-ttu-id="a7c44-284">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-284">Yes</span></span>|<span data-ttu-id="a7c44-285">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-285">No</span></span>|<span data-ttu-id="a7c44-286">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-286">No</span></span>|
|<span data-ttu-id="a7c44-287">アプリケーション ストアへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="a7c44-287">Block access to application store</span></span> |<span data-ttu-id="a7c44-288">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-288">Yes</span></span>|<span data-ttu-id="a7c44-289">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-289">No</span></span>|<span data-ttu-id="a7c44-290">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-290">Yes</span></span>|
|<span data-ttu-id="a7c44-291">アプリケーション ストアへアクセスする際にパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="a7c44-291">Require password when accessing application store</span></span> |<span data-ttu-id="a7c44-292">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-292">No</span></span>|<span data-ttu-id="a7c44-293">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-293">Yes</span></span>|<span data-ttu-id="a7c44-294">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-294">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="a7c44-295">デバイスの機能の設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-295">Device capabilities settings</span></span>

|<span data-ttu-id="a7c44-296">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-296">**Setting name**</span></span>|<span data-ttu-id="a7c44-297">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-297">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-298">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-298">**Android 5 and later**</span></span>|<span data-ttu-id="a7c44-299">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="a7c44-299">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-300">リムーバブル記憶域との接続の禁止</span><span class="sxs-lookup"><span data-stu-id="a7c44-300">Block connection with removable storage</span></span> |<span data-ttu-id="a7c44-301">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-301">Yes</span></span>|<span data-ttu-id="a7c44-302">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-302">Yes</span></span>|<span data-ttu-id="a7c44-303">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-303">No</span></span>|
|<span data-ttu-id="a7c44-304">Bluetooth 接続の禁止</span><span class="sxs-lookup"><span data-stu-id="a7c44-304">Block Bluetooth connection</span></span> |<span data-ttu-id="a7c44-305">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-305">Yes</span></span>|<span data-ttu-id="a7c44-306">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-306">Yes</span></span>|<span data-ttu-id="a7c44-307">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-307">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="a7c44-308">その他の設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-308">Additional settings</span></span>

<span data-ttu-id="a7c44-309">コンプライアンス センター PowerShell コマンドレットを使用して、次の&ポリシー設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-309">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="a7c44-310">詳細については、「Security [& コンプライアンス センター PowerShell」を参照してください](/powershell/exchange/scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a7c44-310">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="a7c44-311">**設定名**</span><span class="sxs-lookup"><span data-stu-id="a7c44-311">**Setting name**</span></span>|<span data-ttu-id="a7c44-312">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-312">**iOS 7.1 and later**</span></span>|<span data-ttu-id="a7c44-313">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="a7c44-313">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7c44-314">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="a7c44-314">CameraEnabled</span></span>|<span data-ttu-id="a7c44-315">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-315">Yes</span></span>|<span data-ttu-id="a7c44-316">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-316">Yes</span></span>|
|<span data-ttu-id="a7c44-317">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="a7c44-317">RegionRatings</span></span>|<span data-ttu-id="a7c44-318">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-318">Yes</span></span>|<span data-ttu-id="a7c44-319">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-319">No</span></span>|
|<span data-ttu-id="a7c44-320">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="a7c44-320">MoviesRatings</span></span>|<span data-ttu-id="a7c44-321">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-321">Yes</span></span>|<span data-ttu-id="a7c44-322">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-322">No</span></span>|
|<span data-ttu-id="a7c44-323">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="a7c44-323">TVShowsRating</span></span> |<span data-ttu-id="a7c44-324">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-324">Yes</span></span>|<span data-ttu-id="a7c44-325">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-325">No</span></span>|
|<span data-ttu-id="a7c44-326">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="a7c44-326">AppsRatings</span></span> |<span data-ttu-id="a7c44-327">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-327">Yes</span></span>|<span data-ttu-id="a7c44-328">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-328">No</span></span>|
|<span data-ttu-id="a7c44-329">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="a7c44-329">AllowVoiceDialing</span></span> |<span data-ttu-id="a7c44-330">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-330">Yes</span></span>|<span data-ttu-id="a7c44-331">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-331">No</span></span>|
|<span data-ttu-id="a7c44-332">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="a7c44-332">AllowVoiceAssistant</span></span> |<span data-ttu-id="a7c44-333">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-333">Yes</span></span>|<span data-ttu-id="a7c44-334">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-334">No</span></span>|
|<span data-ttu-id="a7c44-335">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="a7c44-335">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="a7c44-336">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-336">Yes</span></span>|<span data-ttu-id="a7c44-337">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-337">No</span></span>|
|<span data-ttu-id="a7c44-338">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="a7c44-338">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="a7c44-339">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-339">Yes</span></span>|<span data-ttu-id="a7c44-340">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-340">No</span></span>|
|<span data-ttu-id="a7c44-341">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="a7c44-341">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="a7c44-342">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-342">Yes</span></span>|<span data-ttu-id="a7c44-343">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-343">No</span></span>|
|<span data-ttu-id="a7c44-344">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="a7c44-344">PasswordQuality</span></span> |<span data-ttu-id="a7c44-345">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-345">No</span></span>|<span data-ttu-id="a7c44-346">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-346">Yes</span></span>|
|<span data-ttu-id="a7c44-347">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="a7c44-347">SystemSecurityTLS</span></span>  |<span data-ttu-id="a7c44-348">はい</span><span class="sxs-lookup"><span data-stu-id="a7c44-348">Yes</span></span>|<span data-ttu-id="a7c44-349">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-349">No</span></span>|
|<span data-ttu-id="a7c44-350">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="a7c44-350">WLANEnabled</span></span>  |<span data-ttu-id="a7c44-351">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-351">No</span></span>|<span data-ttu-id="a7c44-352">いいえ</span><span class="sxs-lookup"><span data-stu-id="a7c44-352">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="a7c44-353">Windows でサポートされる設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-353">Settings supported by Windows</span></span>

<span data-ttu-id="a7c44-354">Windows 10 デバイスは、モバイル デバイスとして登録することで管理できます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-354">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="a7c44-355">該当するポリシーが展開された後、Windows 10 デバイスを使用するユーザーは、組み込みの電子メール アプリを初めて使用して Microsoft 365 メールにアクセスする際に、Basic Mobility and Security に登録する必要があります (Azure AD プレミアム サブスクリプションが必要です)。</span><span class="sxs-lookup"><span data-stu-id="a7c44-355">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="a7c44-356">モバイル デバイスとして登録されている Windows 10 デバイスでは、次の設定がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a7c44-356">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="a7c44-357">これらの設定では、ユーザーが Microsoft 365 リソースにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7c44-357">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="a7c44-358">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-358">Security settings</span></span>

- <span data-ttu-id="a7c44-359">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="a7c44-359">Require an alphanumeric password</span></span>

- <span data-ttu-id="a7c44-360">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="a7c44-360">Minimum password length</span></span>

- <span data-ttu-id="a7c44-361">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="a7c44-361">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="a7c44-362">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="a7c44-362">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="a7c44-363">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="a7c44-363">Password expiration (days)</span></span>

- <span data-ttu-id="a7c44-364">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="a7c44-364">Remember password history and prevent reuse</span></span>

>[!NOTE]
><span data-ttu-id="a7c44-365">パスワードを調整する次の設定では、ローカル Windows アカウントのみを制御します。</span><span class="sxs-lookup"><span data-stu-id="a7c44-365">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="a7c44-366">ドメインまたは Azure Active Directory に参加して提供される Windows アカウントは、これらの設定の影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="a7c44-366">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="a7c44-367">システムの設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-367">System settings</span></span>

<span data-ttu-id="a7c44-368">デバイスからの診断データの送信をブロックします。</span><span class="sxs-lookup"><span data-stu-id="a7c44-368">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="a7c44-369">その他の設定</span><span class="sxs-lookup"><span data-stu-id="a7c44-369">Additional settings</span></span>

<span data-ttu-id="a7c44-370">PowerShell コマンドレットを使用して、次の追加のポリシー設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-370">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="a7c44-371">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="a7c44-371">AllowConvenienceLogon</span></span>

- <span data-ttu-id="a7c44-372">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="a7c44-372">UserAccountControlStatus</span></span>

- <span data-ttu-id="a7c44-373">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="a7c44-373">FirewallStatus</span></span>

- <span data-ttu-id="a7c44-374">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="a7c44-374">AutoUpdateStatus</span></span>

- <span data-ttu-id="a7c44-375">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="a7c44-375">AntiVirusStatus</span></span>

- <span data-ttu-id="a7c44-376">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="a7c44-376">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="a7c44-377">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="a7c44-377">SmartScreenEnabled</span></span>

- <span data-ttu-id="a7c44-378">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="a7c44-378">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="a7c44-379">モバイル デバイスをリモートからワイプする</span><span class="sxs-lookup"><span data-stu-id="a7c44-379">Remotely wipe a mobile device</span></span>

<span data-ttu-id="a7c44-380">デバイスが紛失または盗難に遭った場合は、機密の組織データを削除し、セキュリティ & コンプライアンス センター > データ損失防止デバイス管理からワイプを行って、Microsoft 365 組織リソースへのアクセスを防止できます。   >  </span><span class="sxs-lookup"><span data-stu-id="a7c44-380">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="a7c44-381">個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a7c44-381">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="a7c44-382">詳細については、「Basic [Mobility and Security」でモバイル デバイスをワイプするを参照してください](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="a7c44-382">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a7c44-383">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7c44-383">Related topics</span></span>

[<span data-ttu-id="a7c44-384">Microsoft 365 の基本モビリティとセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="a7c44-384">Overview of Basic Mobility and Security for Microsoft 365</span></span>](overview.md)

[<span data-ttu-id="a7c44-385">Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a7c44-385">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)