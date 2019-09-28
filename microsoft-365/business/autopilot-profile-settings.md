---
title: AutoPilot プロファイルの設定について
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自動操縦プロファイルは、ユーザーデバイスへの Windows のインストール方法を制御するのに役立ちます。 プロファイルには、Cortana のインストールをスキップするなどの、既定の設定とオプションの設定が含まれています。
ms.openlocfilehash: cd66627943301f4a4f2410bafeff6074919ec29d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287477"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="a9b68-104">AutoPilot プロファイルの設定について</span><span class="sxs-lookup"><span data-stu-id="a9b68-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="a9b68-105">AutoPilot プロファイルの設定について</span><span class="sxs-lookup"><span data-stu-id="a9b68-105">AutoPilot profile settings</span></span>

<span data-ttu-id="a9b68-106">自動操縦プロファイルを使用して、ユーザーのデバイスに Windows をインストールする方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a9b68-106">You can control how Windows gets installed on user devices by using the AutoPilot profiles.</span></span> <span data-ttu-id="a9b68-107">プロファイルには、次の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9b68-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="a9b68-108">**自動操縦既定の機能 (必須) は、自動的に設定されます。**</span><span class="sxs-lookup"><span data-stu-id="a9b68-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="a9b68-109">**設定**</span><span class="sxs-lookup"><span data-stu-id="a9b68-109">**Setting**</span></span>|<span data-ttu-id="a9b68-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="a9b68-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9b68-111">Cortana、OneDrive、OEM の登録のスキップ</span><span class="sxs-lookup"><span data-stu-id="a9b68-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="a9b68-112">Cortana や個人用 OneDrive のようなコンシューマーアプリのインストールをスキップします。</span><span class="sxs-lookup"><span data-stu-id="a9b68-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="a9b68-113">デバイスのユーザーがデバイスのローカル管理者である場合は、後でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a9b68-113">The device user can install these later as long as he or she is a local admin on the device.</span></span> <span data-ttu-id="a9b68-114">デバイスは Microsoft 365 Business によって管理されるため、元の製造元の登録はスキップされます。</span><span class="sxs-lookup"><span data-stu-id="a9b68-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="a9b68-115">会社のブランドが表示されたサインイン画面</span><span class="sxs-lookup"><span data-stu-id="a9b68-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="a9b68-116">会社に[Office 365 のサインインページに会社のブランドを追加](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)することがある場合、デバイスユーザーはサインインしたときにそのような操作を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9b68-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="a9b68-117">構成済み AAD アカウントを使用した MDM 自動登録</span><span class="sxs-lookup"><span data-stu-id="a9b68-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="a9b68-118">ユーザー ID は Azure Active Directory によって管理され、ユーザーは Microsoft 365 Business 資格情報を使って Windows と Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a9b68-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="a9b68-119">**オプションの設定:**</span><span class="sxs-lookup"><span data-stu-id="a9b68-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="a9b68-120">**設定**</span><span class="sxs-lookup"><span data-stu-id="a9b68-120">**Setting**</span></span>|<span data-ttu-id="a9b68-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="a9b68-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9b68-122">プライバシーの設定のスキップ (既定ではオフ)</span><span class="sxs-lookup"><span data-stu-id="a9b68-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="a9b68-123">このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。</span><span class="sxs-lookup"><span data-stu-id="a9b68-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="a9b68-124">ユーザーがローカル管理者になることを許可しない</span><span class="sxs-lookup"><span data-stu-id="a9b68-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="a9b68-125">このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="a9b68-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
