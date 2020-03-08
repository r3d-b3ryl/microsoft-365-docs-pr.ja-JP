---
title: モバイル デバイスの紛失または盗難時の作業ファイルの保護
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4StolenDevice
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c12164c7-6190-4294-b88a-590580c9869a
description: ユーザーのデバイスが紛失したり盗難にあった場合に、作業ファイルを保護するために Microsoft 365 Business で使用可能な設定について説明します。
ms.openlocfilehash: 4371acd53da902aa4dea93e7b8bd087d1cf27100
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561652"
---
# <a name="protect-work-files-when-a-mobile-device-is-lost-or-stolen"></a><span data-ttu-id="1fbfe-103">モバイル デバイスの紛失または盗難時の作業ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="1fbfe-103">Protect work files when a mobile device is lost or stolen</span></span>

<span data-ttu-id="1fbfe-104">ポリシーの設定では、紛失したり盗難されたデバイスを保護するために、発生している問題を自動的に判断します。</span><span class="sxs-lookup"><span data-stu-id="1fbfe-104">The policy settings determine what happens automatically to protect a device that is lost or stolen.</span></span> <span data-ttu-id="1fbfe-105">すべてのユーザーに適用される Android、iOS、Windows 10 のアプリケーションポリシーを作成するには、セットアップ時に既定値を受け入れることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1fbfe-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="1fbfe-106">セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1fbfe-106">You can create more policies after setup completes.</span></span>
  
## <a name="settings-that-protect-work-files"></a><span data-ttu-id="1fbfe-107">作業ファイルを保護する設定</span><span class="sxs-lookup"><span data-stu-id="1fbfe-107">Settings that protect work files</span></span>

<span data-ttu-id="1fbfe-108">次の設定は、ユーザーのデバイスが紛失したり盗難された場合に、作業ファイルを保護するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="1fbfe-108">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1fbfe-109">設定</span><span class="sxs-lookup"><span data-stu-id="1fbfe-109">Setting</span></span>  <br/> |<span data-ttu-id="1fbfe-110">説明</span><span class="sxs-lookup"><span data-stu-id="1fbfe-110">Description</span></span>  <br/> |
|<span data-ttu-id="1fbfe-111">この日数後、非アクティブなデバイスから作業ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="1fbfe-111">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="1fbfe-112">指定した日数にデバイスが使用されていない場合は、デバイスに保存されているすべての作業ファイルが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="1fbfe-112">If a device isn't used for the number of days that you specify here, any work files stored on the device are automatically deleted.</span></span>  <br/> |
|<span data-ttu-id="1fbfe-113">ユーザーにすべての作業ファイルを OneDrive for Business に強制的に保存させる</span><span class="sxs-lookup"><span data-stu-id="1fbfe-113">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="1fbfe-114">この設定が**オンに**なっている場合、作業ファイルの保存場所として使用できるのは、OneDrive for business のみです。</span><span class="sxs-lookup"><span data-stu-id="1fbfe-114">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="1fbfe-115">作業ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="1fbfe-115">Encrypt work files</span></span>  <br/> |<span data-ttu-id="1fbfe-116">作業ファイルが暗号化によって保護されるように、この設定は常に **オン**にします。</span><span class="sxs-lookup"><span data-stu-id="1fbfe-116">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="1fbfe-117">デバイスが紛失または盗難にあった場合でも、会社のデータを読み取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="1fbfe-117">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   

