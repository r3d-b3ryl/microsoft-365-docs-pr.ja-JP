---
title: モバイル デバイスの紛失または盗難時の作業ファイルの保護
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c12164c7-6190-4294-b88a-590580c9869a
description: ユーザーのデバイスが紛失または盗難Microsoft 365作業ファイルを保護するために、ビジネス向けアプリで使用できる設定について説明します。
ms.openlocfilehash: 6b10ce73d3ebe936d3878724783d6076455a3552
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578249"
---
# <a name="protect-work-files-when-a-mobile-device-is-lost-or-stolen"></a><span data-ttu-id="81752-103">モバイル デバイスの紛失または盗難時の作業ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="81752-103">Protect work files when a mobile device is lost or stolen</span></span>

<span data-ttu-id="81752-104">ポリシーの設定では、紛失したり盗難されたデバイスを保護するために、発生している問題を自動的に判断します。</span><span class="sxs-lookup"><span data-stu-id="81752-104">The policy settings determine what happens automatically to protect a device that is lost or stolen.</span></span> <span data-ttu-id="81752-105">セットアップ時に既定値を受け入れて、すべてのユーザーに適用される Android、iOS、および Windows 10アプリケーション ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="81752-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="81752-106">セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="81752-106">You can create more policies after setup completes.</span></span>
  
## <a name="settings-that-protect-work-files"></a><span data-ttu-id="81752-107">作業ファイルを保護する設定</span><span class="sxs-lookup"><span data-stu-id="81752-107">Settings that protect work files</span></span>

<span data-ttu-id="81752-108">次の設定は、ユーザーのデバイスが紛失したり盗難された場合に、作業ファイルを保護するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="81752-108">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="81752-109">Setting</span><span class="sxs-lookup"><span data-stu-id="81752-109">Setting</span></span>  <br/> |<span data-ttu-id="81752-110">説明</span><span class="sxs-lookup"><span data-stu-id="81752-110">Description</span></span>  <br/> |
|<span data-ttu-id="81752-111">この日数後、非アクティブなデバイスから作業ファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="81752-111">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="81752-112">ここで指定した日数のデバイスを使用しない場合、デバイスに保存されている作業ファイルは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="81752-112">If a device isn't used for the number of days that you specify here, any work files stored on the device are automatically deleted.</span></span>  <br/> |
|<span data-ttu-id="81752-113">ユーザーにすべての作業ファイルを OneDrive for Business に強制的に保存させる</span><span class="sxs-lookup"><span data-stu-id="81752-113">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="81752-114">この設定が **[オン] の場合**、作業ファイルに使用できる保存場所は、OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="81752-114">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="81752-115">作業ファイルの暗号化</span><span class="sxs-lookup"><span data-stu-id="81752-115">Encrypt work files</span></span>  <br/> |<span data-ttu-id="81752-116">作業ファイルが暗号化によって保護されるように、この設定は常に **オン** にします。</span><span class="sxs-lookup"><span data-stu-id="81752-116">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="81752-117">デバイスが紛失または盗まれた場合でも、誰も会社のデータを読み取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="81752-117">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   

