---
title: AutoPilot プロファイルの設定について
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自動操縦装置のプロファイルを使用して、ユーザーのデバイス上の Windows のインストール方法を制御できます。プロファイルには、既定値が含まれているし、オプションの設定は、Cortana のインストールをスキップするように。
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869025"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="a9f54-104">AutoPilot プロファイルの設定について</span><span class="sxs-lookup"><span data-stu-id="a9f54-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="a9f54-105">AutoPilot プロファイルの設定について</span><span class="sxs-lookup"><span data-stu-id="a9f54-105">AutoPilot profile settings</span></span>

<span data-ttu-id="a9f54-p102">Windows の自動操縦装置のプロファイルを使用してユーザー デバイス上インストール取得方法を制御できます。プロファイルには、次の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a9f54-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="a9f54-108">**自動操縦既定の機能 (必須) に自動的に設定されています。**</span><span class="sxs-lookup"><span data-stu-id="a9f54-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="a9f54-109">**設定**</span><span class="sxs-lookup"><span data-stu-id="a9f54-109">**Setting**</span></span>|<span data-ttu-id="a9f54-110">**説明**</span><span class="sxs-lookup"><span data-stu-id="a9f54-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9f54-111">Cortana、OneDrive、OEM の登録のスキップ</span><span class="sxs-lookup"><span data-stu-id="a9f54-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="a9f54-p103">Cortana および個人の OneDrive のようなコンシューマー アプリケーションのインストールをスキップします。デバイス ユーザーは、彼または彼女は、デバイス上のローカル管理者として、後でインストールできます。元の製造元の登録は、マイクロソフトの 365 のビジネスが、デバイスを管理するためにスキップされます。</span><span class="sxs-lookup"><span data-stu-id="a9f54-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="a9f54-115">会社のブランドが表示されたサインイン画面</span><span class="sxs-lookup"><span data-stu-id="a9f54-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="a9f54-116">会社は、 [Office 365 のサインイン ページを追加、会社のブランド](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)には、デバイスのユーザーは、サインイン時に、その経験を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9f54-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="a9f54-117">構成済み AAD アカウントを使用した MDM 自動登録</span><span class="sxs-lookup"><span data-stu-id="a9f54-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="a9f54-118">ユーザー ID は Azure Active Directory によって管理され、ユーザーは Microsoft 365 Business 資格情報を使って Windows と Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a9f54-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="a9f54-119">**オプションの設定:**</span><span class="sxs-lookup"><span data-stu-id="a9f54-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="a9f54-120">**設定**</span><span class="sxs-lookup"><span data-stu-id="a9f54-120">**Setting**</span></span>|<span data-ttu-id="a9f54-121">**説明**</span><span class="sxs-lookup"><span data-stu-id="a9f54-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9f54-122">プライバシーの設定のスキップ (既定ではオフ)</span><span class="sxs-lookup"><span data-stu-id="a9f54-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="a9f54-123">このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。</span><span class="sxs-lookup"><span data-stu-id="a9f54-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="a9f54-124">ユーザーがローカル管理者になることを許可しない</span><span class="sxs-lookup"><span data-stu-id="a9f54-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="a9f54-125">このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="a9f54-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
