---
title: AutoPilot プロファイルの設定について
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自動操縦プロファイルは、ユーザーデバイスへの Windows のインストール方法を制御するのに役立ちます。 プロファイルには、Cortana のインストールをスキップするなどの、既定の設定とオプションの設定が含まれています。
ms.openlocfilehash: 5c2ec3f4c3e0ebc4ea545d11f819c897f414ad52
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627416"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="d8c77-104">AutoPilot プロファイルの設定について</span><span class="sxs-lookup"><span data-stu-id="d8c77-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="d8c77-105">自動操縦プロファイルの設定</span><span class="sxs-lookup"><span data-stu-id="d8c77-105">AutoPilot profile settings</span></span>

<span data-ttu-id="d8c77-106">自動操縦プロファイルを使用して、ユーザーデバイスへの Windows のインストール方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="d8c77-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="d8c77-107">プロファイルには、次の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8c77-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="d8c77-108">**自動操縦既定の機能 (必須) は、自動的に設定されます。**</span><span class="sxs-lookup"><span data-stu-id="d8c77-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="d8c77-109">**設定**</span><span class="sxs-lookup"><span data-stu-id="d8c77-109">**Setting**</span></span>|<span data-ttu-id="d8c77-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="d8c77-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8c77-111">Cortana、OneDrive、OEM 登録をスキップする</span><span class="sxs-lookup"><span data-stu-id="d8c77-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="d8c77-112">Cortana や個人用 OneDrive のようなコンシューマーアプリのインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="d8c77-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="d8c77-113">デバイスユーザーは、ユーザーがデバイスのローカル管理者である限り、これらを後でインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c77-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="d8c77-114">デバイスは Microsoft 365 Business Premium で管理されるため、元の製造元の登録はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="d8c77-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="d8c77-115">会社のブランドが表示されたサインイン画面</span><span class="sxs-lookup"><span data-stu-id="d8c77-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="d8c77-116">会社で[Microsoft 365 サインインページに会社のブランドを追加](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)すると、デバイスのユーザーはサインインしたときにそのような操作を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="d8c77-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="d8c77-117">構成済み AAD アカウントを使用した MDM 自動登録</span><span class="sxs-lookup"><span data-stu-id="d8c77-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="d8c77-118">ユーザー id は Azure Active Directory によって管理され、ユーザーは Microsoft 365 Business Premium 資格情報を使用して Windows と Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d8c77-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="d8c77-119">**オプションの設定:**</span><span class="sxs-lookup"><span data-stu-id="d8c77-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="d8c77-120">**設定**</span><span class="sxs-lookup"><span data-stu-id="d8c77-120">**Setting**</span></span>|<span data-ttu-id="d8c77-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="d8c77-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8c77-122">プライバシーの設定のスキップ (既定ではオフ)</span><span class="sxs-lookup"><span data-stu-id="d8c77-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="d8c77-123">このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。</span><span class="sxs-lookup"><span data-stu-id="d8c77-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="d8c77-124">ユーザーがローカル管理者になることを許可しない</span><span class="sxs-lookup"><span data-stu-id="d8c77-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="d8c77-125">このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="d8c77-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
