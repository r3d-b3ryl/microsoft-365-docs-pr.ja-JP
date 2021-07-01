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
ms.openlocfilehash: a5f20b2999a1a54070433560904e9535a4d1524a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228281"
---
# <a name="capabilities-of-basic-mobility-and-security"></a><span data-ttu-id="3b189-103">基本的なモビリティとセキュリティの機能</span><span class="sxs-lookup"><span data-stu-id="3b189-103">Capabilities of Basic Mobility and Security</span></span>

<span data-ttu-id="3b189-104">Basic Mobility and Security は、組織内のライセンスを持つ Microsoft 365 ユーザーが使用する iPhone、iPad、Android、Windows Phone など、モバイル デバイスのセキュリティ保護と管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b189-104">Basic Mobility and Security can help you secure and manage mobile devices like iPhones, iPads, Androids, and Windows Phones used by licensed Microsoft 365 users in your organization.</span></span> <span data-ttu-id="3b189-105">モバイル デバイス管理ポリシーを作成し、サポートされているモバイル デバイスとアプリの組織の Microsoft 365 メールやドキュメントへのアクセスを制御するのに役立つ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b189-105">You can create mobile device management policies with settings that can help control access to your organization’s Microsoft 365 email and documents for supported mobile devices and apps.</span></span> <span data-ttu-id="3b189-106">デバイスの紛失または盗難時には、リモートからデバイスをワイプして、組織の機密情報を削除できます。</span><span class="sxs-lookup"><span data-stu-id="3b189-106">If a device is lost or stolen, you can remotely wipe the device to remove sensitive organizational information.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="3b189-107">サポート対象のデバイス</span><span class="sxs-lookup"><span data-stu-id="3b189-107">Supported devices</span></span>

<span data-ttu-id="3b189-108">Basic Mobility and Security を使用すると、次のデバイスをセキュリティで保護および管理できます。</span><span class="sxs-lookup"><span data-stu-id="3b189-108">You can use Basic Mobility and Security to secure and manage the following devices.</span></span>

- <span data-ttu-id="3b189-109">iOS 11.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="3b189-109">iOS 11.0 or later versions</span></span>

- <span data-ttu-id="3b189-110">Android 5.0 以降のバージョン<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="3b189-110">Android 5.0 or later versions<sup>3</sup></span></span>

- <span data-ttu-id="3b189-111">Windows 8.1<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3b189-111">Windows 8.1<sup>1</sup></span></span>

- <span data-ttu-id="3b189-112">Windows 8.1RT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3b189-112">Windows 8.1 RT<sup>1</sup></span></span>

- <span data-ttu-id="3b189-113">Windows 10<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b189-113">Windows 10<sup>2</sup></span></span>

- <span data-ttu-id="3b189-114">Windows 10 Mobile<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b189-114">Windows 10 Mobile<sup>2</sup></span></span>

<span data-ttu-id="3b189-115"><sup>1</sup>RT デバイスWindows 8.1アクセス制御は、1 つの RT デバイスExchange ActiveSync。</span><span class="sxs-lookup"><span data-stu-id="3b189-115"><sup>1</sup>Access control for Windows 8.1 RT devices is limited to Exchange ActiveSync.</span></span>

<span data-ttu-id="3b189-116"><sup>2</sup>ユーザーのアクセス制御Windows 10サブスクリプションが必要で、Azure AD Premiumデバイスをそのサブスクリプションに参加するAzure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="3b189-116"><sup>2</sup>Access control for Windows 10 requires a subscription that includes Azure AD Premium and the device needs to be joined to Azure Active Directory.</span></span>

<span data-ttu-id="3b189-117"><sup>3</sup>2020 年 6 月以降、9 より後の Android バージョンでは、Samsung Knox デバイス以外のパスワード設定を管理できません。</span><span class="sxs-lookup"><span data-stu-id="3b189-117"><sup>3</sup>After June 2020, Android versions later than 9 can't manage password settings except on Samsung Knox devices.</span></span>

> [!NOTE]
> <span data-ttu-id="3b189-118">以前の OS バージョンで既に登録されているデバイスは引き続き機能しますが、機能は予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b189-118">Devices already enrolled with earlier OS versions continue to function although the capabilities might change without notice.</span></span>

<span data-ttu-id="3b189-119">組織内のユーザーが、Basic Mobility and Security でサポートされていないモバイル デバイスを使用している場合は、Exchange ActiveSync アプリによるこれらのデバイスの Microsoft 365 メールへのアクセスをブロックして、組織のデータの安全性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3b189-119">If people in your organization use mobile devices that aren't supported by Basic Mobility and Security, you might want to block Exchange ActiveSync app access to Microsoft 365 email for those devices, to help make your organization's data more secure.</span></span> <span data-ttu-id="3b189-120">デバイスアクセスをブロックするExchange ActiveSync、「Basic Mobility and Security」の「デバイス アクセス設定の[管理」を参照してください](manage-device-access-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3b189-120">For steps to block Exchange ActiveSync, see [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).</span></span>

## <a name="access-control-for-microsoft-365-email-and-documents"></a><span data-ttu-id="3b189-121">電子メールとドキュメントMicrosoft 365アクセス制御</span><span class="sxs-lookup"><span data-stu-id="3b189-121">Access control for Microsoft 365 email and documents</span></span>

<span data-ttu-id="3b189-122">次の表に示すさまざまな種類のモバイル デバイスでサポートされているアプリは、ユーザーのデバイスに適用される新しいモバイル デバイス管理ポリシーが作成され、ユーザーがデバイスを以前に登録しなかった場合に、Basic Mobility and Security に登録するようユーザーに求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b189-122">The supported apps for the different types of mobile devices in the following table prompt users to enroll in Basic Mobility and Security where there is a new mobile device management policy that applies to a user’s device and the user hasn’t previously enrolled the device.</span></span> <span data-ttu-id="3b189-123">ポリシーの設定方法によっては、ユーザーのデバイスがポリシーに準拠しない場合、ユーザーがこれらのアプリの Microsoft 365 リソースにアクセスできないか、アクセス権を持っている可能性がありますが、Microsoft 365 はポリシー違反を報告します。</span><span class="sxs-lookup"><span data-stu-id="3b189-123">If a user’s device doesn’t comply with a policy, depending on how you set the policy up, a user might be blocked from accessing Microsoft 365 resources in these apps, or they might have access but Microsoft 365 reports a policy violation.</span></span>

|<span data-ttu-id="3b189-124">**Product**</span><span class="sxs-lookup"><span data-stu-id="3b189-124">**Product**</span></span>|<span data-ttu-id="3b189-125">**iOS 10.0 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-125">**iOS 10.0 or later**</span></span>|<span data-ttu-id="3b189-126">**Android 5.0 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-126">**Android 5.0 or later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b189-127">**Exchange Exchange ActiveSync** バージョン 14.1 以降を使用する、組み込みの電子 Exchange ActiveSyncメールアプリとサードパーティ製アプリ (TouchDown など) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b189-127">**Exchange** Exchange ActiveSync includes built-in email and third-party apps, like TouchDown, that use Exchange ActiveSync Version 14.1 or later.</span></span> |<span data-ttu-id="3b189-128">メール</span><span class="sxs-lookup"><span data-stu-id="3b189-128">Mail</span></span> |<span data-ttu-id="3b189-129">メール</span><span class="sxs-lookup"><span data-stu-id="3b189-129">Email</span></span> |
|<span data-ttu-id="3b189-130">**Office**  と  **OneDrive for Business**</span><span class="sxs-lookup"><span data-stu-id="3b189-130">**Office** and **OneDrive for Business**</span></span> |<span data-ttu-id="3b189-131">Outlook</span><span class="sxs-lookup"><span data-stu-id="3b189-131">Outlook</span></span> </br><span data-ttu-id="3b189-132">OneDrive</span><span class="sxs-lookup"><span data-stu-id="3b189-132">OneDrive</span></span> </br><span data-ttu-id="3b189-133">Word</span><span class="sxs-lookup"><span data-stu-id="3b189-133">Word</span></span> </br><span data-ttu-id="3b189-134">Excel</span><span class="sxs-lookup"><span data-stu-id="3b189-134">Excel</span></span> </br><span data-ttu-id="3b189-135">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="3b189-135">PowerPoint</span></span>|<span data-ttu-id="3b189-136">**電話とタブレットの場合**:</span><span class="sxs-lookup"><span data-stu-id="3b189-136">**On phones and tablets**:</span></span><br/><span data-ttu-id="3b189-137">Outlook</span><span class="sxs-lookup"><span data-stu-id="3b189-137">Outlook</span></span> <br/> <span data-ttu-id="3b189-138">OneDrive</span><span class="sxs-lookup"><span data-stu-id="3b189-138">OneDrive</span></span> <br/> <span data-ttu-id="3b189-139">Word</span><span class="sxs-lookup"><span data-stu-id="3b189-139">Word</span></span> <br/> <span data-ttu-id="3b189-140">Excel</span><span class="sxs-lookup"><span data-stu-id="3b189-140">Excel</span></span> <br/> <span data-ttu-id="3b189-141">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="3b189-141">PowerPoint</span></span> <br/> <span data-ttu-id="3b189-142">**電話のみ:**</span><span class="sxs-lookup"><span data-stu-id="3b189-142">**On phones only:**</span></span> <br/> <span data-ttu-id="3b189-143">Office Mobile</span><span class="sxs-lookup"><span data-stu-id="3b189-143">Office Mobile</span></span> |

> [!NOTE]
>
> - <span data-ttu-id="3b189-144">iOS 10.0 以降のバージョンのサポートには、iPhoneデバイスiPadがあります。</span><span class="sxs-lookup"><span data-stu-id="3b189-144">Support for iOS 10.0 and later versions includes iPhone and iPad devices.</span></span>
> - <span data-ttu-id="3b189-145">BlackBerry OS デバイスの管理は、Basic Security および Mobility ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3b189-145">Management of BlackBerry OS devices isn’t supported by Basic Security and Mobility.</span></span> <span data-ttu-id="3b189-146">BlackBerry の BlackBerry Business Cloud Services (BBCS) を使用して、BlackBerry OS デバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="3b189-146">Use BlackBerry Business Cloud Services (BBCS) from BlackBerry to manage BlackBerry OS devices.</span></span> <span data-ttu-id="3b189-147">Android OS を実行している Blackberry デバイスは、標準の Android デバイスとしてサポートされています</span><span class="sxs-lookup"><span data-stu-id="3b189-147">Blackberry devices running Android OS are supported as standard Android devices</span></span>
> - <span data-ttu-id="3b189-148">モバイル ブラウザーを使用して Microsoft 365 SharePoint サイト、Office Online のドキュメント、Outlook Web App の電子メールにアクセスする場合、ユーザーは登録を求めるメッセージが表示され、ポリシー違反に対してブロックまたは報告されません。</span><span class="sxs-lookup"><span data-stu-id="3b189-148">Users won’t be prompted to enroll and won’t be blocked or reported for policy violation if they use the mobile browser to access Microsoft 365 SharePoint sites, documents in Office Online, or email in Outlook Web App.</span></span>

<span data-ttu-id="3b189-149">次の図は、新しいデバイスを持つユーザーが、Basic Mobility and Security によるアクセス制御をサポートするアプリにサインインした場合の処理を示しています。</span><span class="sxs-lookup"><span data-stu-id="3b189-149">The following diagram shows what happens when a user with a new device signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="3b189-150">ユーザーは、デバイスを登録するまでMicrosoft 365リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3b189-150">The user is blocked from accessing Microsoft 365 resources in the app until they enroll their device.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="基本的なモビリティとセキュリティ アクセス制御":::

> [!NOTE]
> <span data-ttu-id="3b189-152">Microsoft 365 Business Standard の Basic Mobility and Security で作成されたポリシーとアクセス ルールは、Exchange ActiveSync 管理センターで作成された Exchange ActiveSync Exchange モバイル デバイス メールボックス ポリシーとデバイス アクセス ルールを上書きします。</span><span class="sxs-lookup"><span data-stu-id="3b189-152">Policies and access rules created in Basic Mobility and Security for Microsoft 365 Business Standard will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center.</span></span> <span data-ttu-id="3b189-153">デバイスが Basic Mobility and Security for Microsoft 365 Business Standard に登録されると、Exchange ActiveSync に適用されたモバイル デバイス メールボックス ポリシーまたはデバイス アクセス ルールは無視されます。</span><span class="sxs-lookup"><span data-stu-id="3b189-153">After a device is enrolled in Basic Mobility and Security for Microsoft 365 Business Standard, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored.</span></span> <span data-ttu-id="3b189-154">詳細については、「Exchange ActiveSync」の [Exchange ActiveSyncをExchange Online。](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)</span><span class="sxs-lookup"><span data-stu-id="3b189-154">To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).</span></span>

## <a name="policy-settings-for-mobile-devices"></a><span data-ttu-id="3b189-155">モバイル デバイス用のポリシー設定</span><span class="sxs-lookup"><span data-stu-id="3b189-155">Policy settings for mobile devices</span></span>

<span data-ttu-id="3b189-156">特定の設定を有効にした状態でアクセスをブロックするポリシーを作成すると[、Microsoft 365](capabilities.md)の電子メールとドキュメントのアクセス制御に記載されているサポートされているアプリを使用している場合、ユーザーは Microsoft 365 リソースへのアクセスをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3b189-156">If you create a policy to block access with certain settings turned on, users are blocked from accessing Microsoft 365 resources when using a supported app that is listed in [Access control for Microsoft 365 email and documents](capabilities.md).</span></span>

<span data-ttu-id="3b189-157">ユーザーがリソースにアクセスMicrosoft 365できる設定は、次のセクションに示されています。</span><span class="sxs-lookup"><span data-stu-id="3b189-157">The settings that can block users from accessing Microsoft 365 resources are in these sections:</span></span>

- <span data-ttu-id="3b189-158">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="3b189-158">Security</span></span>

- <span data-ttu-id="3b189-159">暗号化</span><span class="sxs-lookup"><span data-stu-id="3b189-159">Encryption</span></span>

- <span data-ttu-id="3b189-160">脱獄</span><span class="sxs-lookup"><span data-stu-id="3b189-160">Jail broken</span></span>

- <span data-ttu-id="3b189-161">管理された電子メール プロファイル</span><span class="sxs-lookup"><span data-stu-id="3b189-161">Managed email profile</span></span>

<span data-ttu-id="3b189-162">例として次の図は、登録済みデバイスを使用しているユーザーが、そのデバイスに適用されるモバイル デバイス管理ポリシーのセキュリティ設定を満たしていない場合の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="3b189-162">For example, the following diagram shows what happens when a user with an enrolled device isn’t compliant with a security setting in a mobile device management policy that applies to their device.</span></span> <span data-ttu-id="3b189-163">ユーザーは、Basic Mobility and Security を使用してアクセス制御をサポートするアプリにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3b189-163">The user signs in to an app that supports access control with Basic Mobility and Security.</span></span> <span data-ttu-id="3b189-164">デバイスがセキュリティ設定に準拠するまでMicrosoft 365リソースへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="3b189-164">They are blocked from accessing Microsoft 365 resources in the app until their device complies with the security setting.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Basic Mobility and Security compliance message":::

<span data-ttu-id="3b189-166">以下のセクションでは、組織のリソースに接続するモバイル デバイスのセキュリティ保護と管理に使用できるポリシー Microsoft 365示します。</span><span class="sxs-lookup"><span data-stu-id="3b189-166">The following sections list the policy settings you can use to help secure and manage mobile devices that connect to your Microsoft 365 organization resources.</span></span>

## <a name="security-settings"></a><span data-ttu-id="3b189-167">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="3b189-167">Security settings</span></span>

|<span data-ttu-id="3b189-168">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-168">**Setting name**</span></span>|<span data-ttu-id="3b189-169">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-169">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-170">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-170">**Android 5 and later**</span></span>|<span data-ttu-id="3b189-171">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="3b189-171">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b189-172">パスワードを要求</span><span class="sxs-lookup"><span data-stu-id="3b189-172">Require a password</span></span>|<span data-ttu-id="3b189-173">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-173">Yes</span></span>|<span data-ttu-id="3b189-174">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-174">Yes</span></span>|<span data-ttu-id="3b189-175">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-175">Yes</span></span>|
|<span data-ttu-id="3b189-176">シンプルなパスワードを禁止</span><span class="sxs-lookup"><span data-stu-id="3b189-176">Prevent simple password</span></span>|<span data-ttu-id="3b189-177">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-177">Yes</span></span>|<span data-ttu-id="3b189-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-178">No</span></span>|<span data-ttu-id="3b189-179">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-179">No</span></span>|
|<span data-ttu-id="3b189-180">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="3b189-180">Require an alphanumeric password</span></span>|<span data-ttu-id="3b189-181">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-181">Yes</span></span>|<span data-ttu-id="3b189-182">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-182">No</span></span>|<span data-ttu-id="3b189-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-183">No</span></span>|
|<span data-ttu-id="3b189-184">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="3b189-184">Minimum password length</span></span> |<span data-ttu-id="3b189-185">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-185">Yes</span></span>|<span data-ttu-id="3b189-186">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-186">Yes</span></span>|<span data-ttu-id="3b189-187">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-187">Yes</span></span>|
|<span data-ttu-id="3b189-188">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="3b189-188">Number of sign-in failures before device is wiped</span></span> |<span data-ttu-id="3b189-189">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-189">Yes</span></span>|<span data-ttu-id="3b189-190">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-190">Yes</span></span>|<span data-ttu-id="3b189-191">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-191">Yes</span></span>|
|<span data-ttu-id="3b189-192">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="3b189-192">Minutes of inactivity before device is locked</span></span> |<span data-ttu-id="3b189-193">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-193">Yes</span></span>|<span data-ttu-id="3b189-194">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-194">Yes</span></span>|<span data-ttu-id="3b189-195">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-195">Yes</span></span>|
|<span data-ttu-id="3b189-196">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="3b189-196">Password expiration (days)</span></span> |<span data-ttu-id="3b189-197">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-197">Yes</span></span>|<span data-ttu-id="3b189-198">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-198">Yes</span></span>|<span data-ttu-id="3b189-199">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-199">Yes</span></span>|
|<span data-ttu-id="3b189-200">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="3b189-200">Remember password history and prevent reuse</span></span> |<span data-ttu-id="3b189-201">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-201">Yes</span></span>|<span data-ttu-id="3b189-202">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-202">Yes</span></span>|<span data-ttu-id="3b189-203">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-203">Yes</span></span>|

## <a name="encryption-settings"></a><span data-ttu-id="3b189-204">暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="3b189-204">Encryption settings</span></span>

|<span data-ttu-id="3b189-205">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-205">**Setting name**</span></span>|<span data-ttu-id="3b189-206">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-206">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-207">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-207">**Android 5 and later**</span></span>|<span data-ttu-id="3b189-208">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="3b189-208">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b189-209">デバイスでデータ暗号化を要求<sup>する 1</sup></span><span class="sxs-lookup"><span data-stu-id="3b189-209">Require data encryption on devices<sup>1</sup></span></span> |<span data-ttu-id="3b189-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-210">No</span></span>|<span data-ttu-id="3b189-211">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-211">Yes</span></span>|<span data-ttu-id="3b189-212">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-212">Yes</span></span>|

<span data-ttu-id="3b189-213"><sup>1</sup>Samsung Knox を使用すると、ストレージ カードで暗号化を要求できます。</span><span class="sxs-lookup"><span data-stu-id="3b189-213"><sup>1</sup>With Samsung Knox, you can also require encryption on storage cards.</span></span>

## <a name="jail-broken-setting"></a><span data-ttu-id="3b189-214">脱獄の設定</span><span class="sxs-lookup"><span data-stu-id="3b189-214">Jail broken setting</span></span>

|<span data-ttu-id="3b189-215">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-215">**Setting name**</span></span>|<span data-ttu-id="3b189-216">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-216">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-217">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-217">**Android 5 and later**</span></span>|<span data-ttu-id="3b189-218">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="3b189-218">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b189-219">デバイスの脱獄またはルート化はできません</span><span class="sxs-lookup"><span data-stu-id="3b189-219">Device cannot be jail broken or rooted</span></span> |<span data-ttu-id="3b189-220">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-220">Yes</span></span>|<span data-ttu-id="3b189-221">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-221">Yes</span></span>|<span data-ttu-id="3b189-222">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-222">Yes</span></span>|

## <a name="managed-email-profile-option"></a><span data-ttu-id="3b189-223">管理された電子メール プロファイルのオプション</span><span class="sxs-lookup"><span data-stu-id="3b189-223">Managed email profile option</span></span>

<span data-ttu-id="3b189-224">次のオプションは、手動で作成されたメール プロファイルをMicrosoft 365ユーザーが自分のメールにアクセスするのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="3b189-224">The following option can block users from accessing their Microsoft 365 email if they’re using a manually created email profile.</span></span> <span data-ttu-id="3b189-225">iOS デバイスを使用しているユーザーは、電子メールにアクセスする前に、手動で作成した電子メール プロファイルを削除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b189-225">Users on iOS devices must delete their manually created email profile before they can access their email.</span></span> <span data-ttu-id="3b189-226">プロファイルを削除すると、新しいプロファイルがデバイスに自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="3b189-226">After they delete the profile, a new profile is automatically created on the device.</span></span> <span data-ttu-id="3b189-227">エンド ユーザーが準拠を取得する方法については、「既存の電子メール アカウントが見つかりました [」を参照してください](/intune-user-help/existing-company-email-account-found)。</span><span class="sxs-lookup"><span data-stu-id="3b189-227">For instructions on how end users can get compliant, see [An existing email account was found](/intune-user-help/existing-company-email-account-found).</span></span>

|<span data-ttu-id="3b189-228">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-228">**Setting name**</span></span>|<span data-ttu-id="3b189-229">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-229">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-230">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-230">**Android 5 and later**</span></span>|<span data-ttu-id="3b189-231">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="3b189-231">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b189-232">電子メール プロファイルが管理されている</span><span class="sxs-lookup"><span data-stu-id="3b189-232">Email profile is managed</span></span> |<span data-ttu-id="3b189-233">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-233">Yes</span></span>|<span data-ttu-id="3b189-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-234">No</span></span>|<span data-ttu-id="3b189-235">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-235">No</span></span>|

## <a name="cloud-settings"></a><span data-ttu-id="3b189-236">クラウドの設定</span><span class="sxs-lookup"><span data-stu-id="3b189-236">Cloud settings</span></span>

|<span data-ttu-id="3b189-237">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-237">**Setting name**</span></span>|<span data-ttu-id="3b189-238">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-238">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-239">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-239">**Android 5 and later**</span></span>|<span data-ttu-id="3b189-240">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="3b189-240">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b189-241">暗号化されたバックアップを要求</span><span class="sxs-lookup"><span data-stu-id="3b189-241">Require encrypted backup</span></span> |<span data-ttu-id="3b189-242">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-242">Yes</span></span>|<span data-ttu-id="3b189-243">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-243">No</span></span>|<span data-ttu-id="3b189-244">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-244">No</span></span>|
|<span data-ttu-id="3b189-245">クラウド バックアップの禁止</span><span class="sxs-lookup"><span data-stu-id="3b189-245">Block cloud backup</span></span> |<span data-ttu-id="3b189-246">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-246">Yes</span></span>|<span data-ttu-id="3b189-247">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-247">No</span></span>|<span data-ttu-id="3b189-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-248">No</span></span>|
|<span data-ttu-id="3b189-249">ドキュメントの同期の禁止</span><span class="sxs-lookup"><span data-stu-id="3b189-249">Block document synchronization</span></span> |<span data-ttu-id="3b189-250">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-250">Yes</span></span>|<span data-ttu-id="3b189-251">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-251">No</span></span>|<span data-ttu-id="3b189-252">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-252">No</span></span>|
|<span data-ttu-id="3b189-253">写真の同期の禁止</span><span class="sxs-lookup"><span data-stu-id="3b189-253">Block photo synchronization</span></span>  |<span data-ttu-id="3b189-254">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-254">Yes</span></span>|<span data-ttu-id="3b189-255">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-255">No</span></span>|<span data-ttu-id="3b189-256">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-256">No</span></span>|
|<span data-ttu-id="3b189-257">Google バックアップを許可する</span><span class="sxs-lookup"><span data-stu-id="3b189-257">Allow Google backup</span></span>  |<span data-ttu-id="3b189-258">該当なし</span><span class="sxs-lookup"><span data-stu-id="3b189-258">N/A</span></span>|<span data-ttu-id="3b189-259">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-259">No</span></span>|<span data-ttu-id="3b189-260">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-260">Yes</span></span>|
|<span data-ttu-id="3b189-261">Google アカウントの自動同期を許可する</span><span class="sxs-lookup"><span data-stu-id="3b189-261">Allow Google account auto sync</span></span>  |<span data-ttu-id="3b189-262">該当なし</span><span class="sxs-lookup"><span data-stu-id="3b189-262">N/A</span></span>|<span data-ttu-id="3b189-263">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-263">No</span></span>|<span data-ttu-id="3b189-264">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-264">Yes</span></span>|

## <a name="system-settings"></a><span data-ttu-id="3b189-265">システムの設定</span><span class="sxs-lookup"><span data-stu-id="3b189-265">System settings</span></span>

|<span data-ttu-id="3b189-266">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-266">**Setting name**</span></span>|<span data-ttu-id="3b189-267">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-267">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-268">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-268">**Android 5 and later**</span></span>|<span data-ttu-id="3b189-269">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="3b189-269">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b189-270">画面キャプチャの禁止</span><span class="sxs-lookup"><span data-stu-id="3b189-270">Block screen capture</span></span> |<span data-ttu-id="3b189-271">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-271">Yes</span></span>|<span data-ttu-id="3b189-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-272">No</span></span>|<span data-ttu-id="3b189-273">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-273">Yes</span></span>|
|<span data-ttu-id="3b189-274">デバイスからの診断データ送信の禁止</span><span class="sxs-lookup"><span data-stu-id="3b189-274">Block sending diagnostic data from device</span></span> |<span data-ttu-id="3b189-275">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-275">Yes</span></span>|<span data-ttu-id="3b189-276">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-276">No</span></span>|<span data-ttu-id="3b189-277">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-277">Yes</span></span>|

## <a name="application-settings"></a><span data-ttu-id="3b189-278">アプリケーションの設定</span><span class="sxs-lookup"><span data-stu-id="3b189-278">Application settings</span></span>

|<span data-ttu-id="3b189-279">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-279">**Setting name**</span></span>|<span data-ttu-id="3b189-280">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-280">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-281">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-281">**Android 5 and later**</span></span>|<span data-ttu-id="3b189-282">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="3b189-282">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b189-283">デバイスでのビデオ会議をブロックする</span><span class="sxs-lookup"><span data-stu-id="3b189-283">Block video conferences on device</span></span> |<span data-ttu-id="3b189-284">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-284">Yes</span></span>|<span data-ttu-id="3b189-285">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-285">No</span></span>|<span data-ttu-id="3b189-286">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-286">No</span></span>|
|<span data-ttu-id="3b189-287">アプリケーション ストアへのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="3b189-287">Block access to application store</span></span> |<span data-ttu-id="3b189-288">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-288">Yes</span></span>|<span data-ttu-id="3b189-289">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-289">No</span></span>|<span data-ttu-id="3b189-290">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-290">Yes</span></span>|
|<span data-ttu-id="3b189-291">アプリケーション ストアへアクセスする際にパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="3b189-291">Require password when accessing application store</span></span> |<span data-ttu-id="3b189-292">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-292">No</span></span>|<span data-ttu-id="3b189-293">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-293">Yes</span></span>|<span data-ttu-id="3b189-294">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-294">Yes</span></span>|

## <a name="device-capabilities-settings"></a><span data-ttu-id="3b189-295">デバイスの機能の設定</span><span class="sxs-lookup"><span data-stu-id="3b189-295">Device capabilities settings</span></span>

|<span data-ttu-id="3b189-296">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-296">**Setting name**</span></span>|<span data-ttu-id="3b189-297">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-297">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-298">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-298">**Android 5 and later**</span></span>|<span data-ttu-id="3b189-299">**Samsung Knox**</span><span class="sxs-lookup"><span data-stu-id="3b189-299">**Samsung Knox**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b189-300">リムーバブル記憶域との接続の禁止</span><span class="sxs-lookup"><span data-stu-id="3b189-300">Block connection with removable storage</span></span> |<span data-ttu-id="3b189-301">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-301">Yes</span></span>|<span data-ttu-id="3b189-302">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-302">Yes</span></span>|<span data-ttu-id="3b189-303">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-303">No</span></span>|
|<span data-ttu-id="3b189-304">Bluetooth 接続の禁止</span><span class="sxs-lookup"><span data-stu-id="3b189-304">Block Bluetooth connection</span></span> |<span data-ttu-id="3b189-305">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-305">Yes</span></span>|<span data-ttu-id="3b189-306">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-306">Yes</span></span>|<span data-ttu-id="3b189-307">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-307">No</span></span>|

## <a name="additional-settings"></a><span data-ttu-id="3b189-308">その他の設定</span><span class="sxs-lookup"><span data-stu-id="3b189-308">Additional settings</span></span>

<span data-ttu-id="3b189-309">コンプライアンス センター PowerShell コマンドレットを使用して、次の&ポリシー設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3b189-309">You can set the following additional policy settings by using Security & Compliance Center PowerShell cmdlets.</span></span> <span data-ttu-id="3b189-310">詳細については、「Security [& コンプライアンス センター PowerShell」を参照してください](/powershell/exchange/scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3b189-310">For more information, see [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

|<span data-ttu-id="3b189-311">**設定名**</span><span class="sxs-lookup"><span data-stu-id="3b189-311">**Setting name**</span></span>|<span data-ttu-id="3b189-312">**iOS 7.1 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-312">**iOS 7.1 and later**</span></span>|<span data-ttu-id="3b189-313">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="3b189-313">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b189-314">CameraEnabled</span><span class="sxs-lookup"><span data-stu-id="3b189-314">CameraEnabled</span></span>|<span data-ttu-id="3b189-315">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-315">Yes</span></span>|<span data-ttu-id="3b189-316">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-316">Yes</span></span>|
|<span data-ttu-id="3b189-317">RegionRatings</span><span class="sxs-lookup"><span data-stu-id="3b189-317">RegionRatings</span></span>|<span data-ttu-id="3b189-318">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-318">Yes</span></span>|<span data-ttu-id="3b189-319">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-319">No</span></span>|
|<span data-ttu-id="3b189-320">MoviesRatings</span><span class="sxs-lookup"><span data-stu-id="3b189-320">MoviesRatings</span></span>|<span data-ttu-id="3b189-321">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-321">Yes</span></span>|<span data-ttu-id="3b189-322">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-322">No</span></span>|
|<span data-ttu-id="3b189-323">TVShowsRating</span><span class="sxs-lookup"><span data-stu-id="3b189-323">TVShowsRating</span></span> |<span data-ttu-id="3b189-324">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-324">Yes</span></span>|<span data-ttu-id="3b189-325">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-325">No</span></span>|
|<span data-ttu-id="3b189-326">AppsRatings</span><span class="sxs-lookup"><span data-stu-id="3b189-326">AppsRatings</span></span> |<span data-ttu-id="3b189-327">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-327">Yes</span></span>|<span data-ttu-id="3b189-328">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-328">No</span></span>|
|<span data-ttu-id="3b189-329">AllowVoiceDialing</span><span class="sxs-lookup"><span data-stu-id="3b189-329">AllowVoiceDialing</span></span> |<span data-ttu-id="3b189-330">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-330">Yes</span></span>|<span data-ttu-id="3b189-331">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-331">No</span></span>|
|<span data-ttu-id="3b189-332">AllowVoiceAssistant</span><span class="sxs-lookup"><span data-stu-id="3b189-332">AllowVoiceAssistant</span></span> |<span data-ttu-id="3b189-333">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-333">Yes</span></span>|<span data-ttu-id="3b189-334">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-334">No</span></span>|
|<span data-ttu-id="3b189-335">AllowAssistantWhileLocked</span><span class="sxs-lookup"><span data-stu-id="3b189-335">AllowAssistantWhileLocked</span></span>  |<span data-ttu-id="3b189-336">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-336">Yes</span></span>|<span data-ttu-id="3b189-337">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-337">No</span></span>|
|<span data-ttu-id="3b189-338">AllowPassbookWhileLocked</span><span class="sxs-lookup"><span data-stu-id="3b189-338">AllowPassbookWhileLocked</span></span> |<span data-ttu-id="3b189-339">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-339">Yes</span></span>|<span data-ttu-id="3b189-340">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-340">No</span></span>|
|<span data-ttu-id="3b189-341">MaxPasswordGracePeriod</span><span class="sxs-lookup"><span data-stu-id="3b189-341">MaxPasswordGracePeriod</span></span> |<span data-ttu-id="3b189-342">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-342">Yes</span></span>|<span data-ttu-id="3b189-343">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-343">No</span></span>|
|<span data-ttu-id="3b189-344">PasswordQuality</span><span class="sxs-lookup"><span data-stu-id="3b189-344">PasswordQuality</span></span> |<span data-ttu-id="3b189-345">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-345">No</span></span>|<span data-ttu-id="3b189-346">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-346">Yes</span></span>|
|<span data-ttu-id="3b189-347">SystemSecurityTLS</span><span class="sxs-lookup"><span data-stu-id="3b189-347">SystemSecurityTLS</span></span>  |<span data-ttu-id="3b189-348">はい</span><span class="sxs-lookup"><span data-stu-id="3b189-348">Yes</span></span>|<span data-ttu-id="3b189-349">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-349">No</span></span>|
|<span data-ttu-id="3b189-350">WLANEnabled</span><span class="sxs-lookup"><span data-stu-id="3b189-350">WLANEnabled</span></span>  |<span data-ttu-id="3b189-351">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-351">No</span></span>|<span data-ttu-id="3b189-352">いいえ</span><span class="sxs-lookup"><span data-stu-id="3b189-352">No</span></span>|

## <a name="settings-supported-by-windows"></a><span data-ttu-id="3b189-353">設定によってサポートWindows</span><span class="sxs-lookup"><span data-stu-id="3b189-353">Settings supported by Windows</span></span>

<span data-ttu-id="3b189-354">モバイル デバイスとして登録Windows 10デバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3b189-354">You can manage Windows 10 devices by enrolling them as mobile devices.</span></span> <span data-ttu-id="3b189-355">該当するポリシーが展開された後、Windows 10 デバイスを持つユーザーは、組み込みの電子メール アプリを初めて使用して Microsoft 365 メールにアクセスする際に、Basic Mobility and Security に登録する必要があります (Azure AD プレミアム サブスクリプションが必要です)。</span><span class="sxs-lookup"><span data-stu-id="3b189-355">After an applicable policy is deployed, users with Windows 10 devices will be required to enroll in Basic Mobility and Security the first time they use the built-in email app to access their Microsoft 365 email (requires Azure AD premium subscription).</span></span>

<span data-ttu-id="3b189-356">次の設定は、モバイル Windows 10登録されているデバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3b189-356">The following settings are supported for Windows 10 devices that are enrolled as mobile devices.</span></span> <span data-ttu-id="3b189-357">これらの設定では、ユーザーがリソースにアクセスMicrosoft 365は使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b189-357">These setting won’t block users from accessing Microsoft 365 resources.</span></span>

### <a name="security-settings"></a><span data-ttu-id="3b189-358">セキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="3b189-358">Security settings</span></span>

- <span data-ttu-id="3b189-359">英数字のパスワードを要求</span><span class="sxs-lookup"><span data-stu-id="3b189-359">Require an alphanumeric password</span></span>

- <span data-ttu-id="3b189-360">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="3b189-360">Minimum password length</span></span>

- <span data-ttu-id="3b189-361">デバイスがワイプされるまでのサインイン失敗回数</span><span class="sxs-lookup"><span data-stu-id="3b189-361">Number of sign-in failures before device is wiped</span></span>

- <span data-ttu-id="3b189-362">デバイスがロックされるまでのアイドル時間 (分)</span><span class="sxs-lookup"><span data-stu-id="3b189-362">Minutes of inactivity before device is locked</span></span>

- <span data-ttu-id="3b189-363">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="3b189-363">Password expiration (days)</span></span>

- <span data-ttu-id="3b189-364">パスワードの履歴を記憶して再利用を防止</span><span class="sxs-lookup"><span data-stu-id="3b189-364">Remember password history and prevent reuse</span></span>

> [!NOTE]
> <span data-ttu-id="3b189-365">パスワードを調整する次の設定では、ローカル アカウントWindows制御します。</span><span class="sxs-lookup"><span data-stu-id="3b189-365">The following settings regulating passwords only control local Windows accounts.</span></span> <span data-ttu-id="3b189-366">Windowsまたはドメインに参加して提供Azure Active Directoryアカウントは、これらの設定の影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="3b189-366">Windows accounts provided through join a domain or Azure Active Directory aren't affected by these settings.</span></span>

### <a name="system-settings"></a><span data-ttu-id="3b189-367">システムの設定</span><span class="sxs-lookup"><span data-stu-id="3b189-367">System settings</span></span>

<span data-ttu-id="3b189-368">デバイスからの診断データの送信をブロックします。</span><span class="sxs-lookup"><span data-stu-id="3b189-368">Block sending diagnostic data from device.</span></span>

### <a name="additional-settings"></a><span data-ttu-id="3b189-369">その他の設定</span><span class="sxs-lookup"><span data-stu-id="3b189-369">Additional settings</span></span>

<span data-ttu-id="3b189-370">PowerShell コマンドレットを使用して、次の追加のポリシー設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3b189-370">You can set these additional policy settings by using PowerShell cmdlets:</span></span>

- <span data-ttu-id="3b189-371">AllowConvenienceLogon</span><span class="sxs-lookup"><span data-stu-id="3b189-371">AllowConvenienceLogon</span></span>

- <span data-ttu-id="3b189-372">UserAccountControlStatus</span><span class="sxs-lookup"><span data-stu-id="3b189-372">UserAccountControlStatus</span></span>

- <span data-ttu-id="3b189-373">FirewallStatus</span><span class="sxs-lookup"><span data-stu-id="3b189-373">FirewallStatus</span></span>

- <span data-ttu-id="3b189-374">AutoUpdateStatus</span><span class="sxs-lookup"><span data-stu-id="3b189-374">AutoUpdateStatus</span></span>

- <span data-ttu-id="3b189-375">AntiVirusStatus</span><span class="sxs-lookup"><span data-stu-id="3b189-375">AntiVirusStatus</span></span>

- <span data-ttu-id="3b189-376">AntiVirusSignatureStatus</span><span class="sxs-lookup"><span data-stu-id="3b189-376">AntiVirusSignatureStatus</span></span>

- <span data-ttu-id="3b189-377">SmartScreenEnabled</span><span class="sxs-lookup"><span data-stu-id="3b189-377">SmartScreenEnabled</span></span>

- <span data-ttu-id="3b189-378">WorkFoldersSyncUrl</span><span class="sxs-lookup"><span data-stu-id="3b189-378">WorkFoldersSyncUrl</span></span>

## <a name="remotely-wipe-a-mobile-device"></a><span data-ttu-id="3b189-379">モバイル デバイスをリモートからワイプする</span><span class="sxs-lookup"><span data-stu-id="3b189-379">Remotely wipe a mobile device</span></span>

<span data-ttu-id="3b189-380">デバイスが紛失または盗難に遭った場合は、機密の組織データを削除し、セキュリティ & コンプライアンス センター > データ損失防止デバイス管理からワイプを行って、Microsoft 365 組織リソースへのアクセスを防ぐのに役立ちます。  >  </span><span class="sxs-lookup"><span data-stu-id="3b189-380">If a device is lost or stolen, you can remove sensitive organizational data and help prevent access to your Microsoft 365 organization resources by doing a wipe from Security & Compliance center > **Data loss prevention** > **Device management**.</span></span> <span data-ttu-id="3b189-381">個別のワイプで組織のデータのみを削除することも、全体のワイプでデバイスからすべての情報を削除して出荷時の設定に戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3b189-381">You can do a selective wipe to remove only organizational data or a full wipe to delete all information from a device and restore it to its factory settings.</span></span>

<span data-ttu-id="3b189-382">詳細については、「Basic [Mobility and Security」でモバイル デバイスをワイプするを参照してください](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="3b189-382">For more information, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="3b189-383">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="3b189-383">Related content</span></span>

<span data-ttu-id="3b189-384">[基本モビリティとセキュリティの](overview.md)概要 (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="3b189-384">[Overview of Basic Mobility and Security for Microsoft 365](overview.md) (article)</span></span>\
<span data-ttu-id="3b189-385">[Basic Mobility and Security でデバイス セキュリティ ポリシーを作成する](create-device-security-policies.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="3b189-385">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article)</span></span>