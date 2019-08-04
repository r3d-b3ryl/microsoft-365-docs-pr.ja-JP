---
title: モバイル デバイスの紛失または盗難時の作業ファイルの保護
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c12164c7-6190-4294-b88a-590580c9869a
description: ユーザーのデバイスが紛失したり盗難にあった場合に、作業ファイルを保護するために使用できる設定について説明します。
ms.openlocfilehash: 505b85dabfdd27a9da8b7bcfdf7741dbb22b0ba3
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074452"
---
# <a name="protect-work-files-when-a-mobile-device-is-lost-or-stolen"></a><span data-ttu-id="e9821-103">モバイル デバイスの紛失または盗難時の作業ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="e9821-103">Protect work files when a mobile device is lost or stolen</span></span>

<span data-ttu-id="e9821-p101">ポリシーの設定では、紛失したり盗難されたデバイスを保護するために、発生している問題を自動的に判断します。セットアップ時に既定値を受け入れて、すべてのユーザーに適用される、Android、iOS、Windows 10 のアプリケーション ポリシーを作成することをお勧めします。セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e9821-p101">The policy settings determine what happens automatically to protect a device that is lost or stolen. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span>
  
## <a name="settings-that-protect-work-files"></a><span data-ttu-id="e9821-107">作業ファイルを保護する設定</span><span class="sxs-lookup"><span data-stu-id="e9821-107">Settings that protect work files</span></span>

<span data-ttu-id="e9821-108">次の設定は、ユーザーのデバイスが紛失したり盗難された場合に、作業ファイルを保護するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9821-108">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e9821-109">Setting</span><span class="sxs-lookup"><span data-stu-id="e9821-109">Setting</span></span>  <br/> |<span data-ttu-id="e9821-110">説明</span><span class="sxs-lookup"><span data-stu-id="e9821-110">Description</span></span>  <br/> |
|<span data-ttu-id="e9821-111">この日数後、非アクティブなデバイスから作業ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="e9821-111">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="e9821-112">ここで指定した日数の間デバイスが使用されなかった場合、デバイスに保存されているすべての作業ファイルは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e9821-112">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="e9821-113">ユーザーにすべての作業ファイルを OneDrive for Business に強制的に保存させる</span><span class="sxs-lookup"><span data-stu-id="e9821-113">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="e9821-114">この設定を **オン**にすると、作業ファイルの使用可能な保存場所は OneDrive for Business のみになります。</span><span class="sxs-lookup"><span data-stu-id="e9821-114">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="e9821-115">作業ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="e9821-115">Encrypt work files</span></span>  <br/> |<span data-ttu-id="e9821-p102">作業ファイルが暗号化によって保護されるように、この設定は常に **オン**にします。デバイスが紛失したり盗難された場合でも、企業データが読まれることはありません。  </span><span class="sxs-lookup"><span data-stu-id="e9821-p102">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   

