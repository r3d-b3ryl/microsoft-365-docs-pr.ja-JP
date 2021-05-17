---
title: AutoPilot プロファイルの設定について
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot プロファイルは、ユーザー デバイスにインストールWindows方法を制御するのに役立ちます。 プロファイルには、Cortana のインストールをスキップするなど、既定とオプションの設定が含まれる。
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578509"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="9e81f-104">AutoPilot プロファイルの設定について</span><span class="sxs-lookup"><span data-stu-id="9e81f-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="9e81f-105">AutoPilot プロファイルの設定</span><span class="sxs-lookup"><span data-stu-id="9e81f-105">AutoPilot profile settings</span></span>

<span data-ttu-id="9e81f-106">AutoPilot プロファイルを使用して、ユーザー デバイスWindows方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="9e81f-107">プロファイルには、次の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e81f-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="9e81f-108">**自動で設定される AutoPilot の既定の機能 (必須)。**</span><span class="sxs-lookup"><span data-stu-id="9e81f-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="9e81f-109">**設定**</span><span class="sxs-lookup"><span data-stu-id="9e81f-109">**Setting**</span></span>|<span data-ttu-id="9e81f-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="9e81f-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e81f-111">Cortana、OneDrive、OEM 登録をスキップする</span><span class="sxs-lookup"><span data-stu-id="9e81f-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="9e81f-112">Cortana や個人用アプリなど、コンシューマー アプリのインストールOneDrive。</span><span class="sxs-lookup"><span data-stu-id="9e81f-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="9e81f-113">デバイスユーザーは、ユーザーがデバイスのローカル管理者である限り、後でこれらをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="9e81f-114">デバイスはユーザーによって管理されるので、元の製造元の登録はスキップMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="9e81f-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="9e81f-115">会社のブランドが表示されたサインイン画面</span><span class="sxs-lookup"><span data-stu-id="9e81f-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="9e81f-116">会社に [会社[](../admin/setup/customize-sign-in-page.md)のブランドをサインインに追加Microsoft 365] ページがある場合、デバイス ユーザーはサインイン時にそのエクスペリエンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9e81f-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](../admin/setup/customize-sign-in-page.md), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="9e81f-117">構成済み AAD アカウントを使用した MDM 自動登録</span><span class="sxs-lookup"><span data-stu-id="9e81f-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="9e81f-118">ユーザー ID は Azure Active Directory によって管理され、ユーザーは自分の資格情報を使用して WindowsおよびMicrosoft 365にサインインMicrosoft 365 Business Premiumされます。</span><span class="sxs-lookup"><span data-stu-id="9e81f-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="9e81f-119">**オプションの設定:**</span><span class="sxs-lookup"><span data-stu-id="9e81f-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="9e81f-120">**設定**</span><span class="sxs-lookup"><span data-stu-id="9e81f-120">**Setting**</span></span>|<span data-ttu-id="9e81f-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="9e81f-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e81f-122">プライバシーの設定のスキップ (既定ではオフ)</span><span class="sxs-lookup"><span data-stu-id="9e81f-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="9e81f-123">このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。</span><span class="sxs-lookup"><span data-stu-id="9e81f-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="9e81f-124">ユーザーがローカル管理者になることを許可しない</span><span class="sxs-lookup"><span data-stu-id="9e81f-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="9e81f-125">このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="9e81f-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
