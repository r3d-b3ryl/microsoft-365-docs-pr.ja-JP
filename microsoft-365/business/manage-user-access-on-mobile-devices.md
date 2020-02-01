---
title: ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: モバイルデバイスから Office アプリへのアクセスを保護するのに役立つ保護ポリシーについて説明します。
ms.openlocfilehash: 39d28a3a78fb06d0020c484b1782b544f6a8c656
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593823"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="838bf-103">ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する</span><span class="sxs-lookup"><span data-stu-id="838bf-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="838bf-104">ユーザーがモバイル デバイスから Office ファイルにアクセスする方法を制御するポリシーの設定は、既定では **オフ**になっています。</span><span class="sxs-lookup"><span data-stu-id="838bf-104">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="838bf-105">すべてのユーザーに適用される Android、iOS、Windows 10 のアプリケーションポリシーを作成するには、セットアップ時に既定値を受け入れることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="838bf-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="838bf-106">セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="838bf-106">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="838bf-107">ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定</span><span class="sxs-lookup"><span data-stu-id="838bf-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="838bf-108">次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="838bf-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="838bf-109">Setting</span><span class="sxs-lookup"><span data-stu-id="838bf-109">Setting</span></span>  <br/> |<span data-ttu-id="838bf-110">説明</span><span class="sxs-lookup"><span data-stu-id="838bf-110">Description</span></span>  <br/> |
|<span data-ttu-id="838bf-111">Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="838bf-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="838bf-112">この設定が**オンになって**いる場合は、ユーザーのモバイルデバイスで Office アプリを使用できるようにするために、ユーザー名とパスワードに加えて、別の形式の認証を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="838bf-112">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="838bf-113">ログインに指定の回数失敗した場合に PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="838bf-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="838bf-114">承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="838bf-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="838bf-115">次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある</span><span class="sxs-lookup"><span data-stu-id="838bf-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="838bf-116">この設定により、ユーザーがもう一度サインインするように求めるメッセージが表示されるまでの待機時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="838bf-116">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="838bf-117">脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="838bf-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="838bf-118">賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="838bf-118">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="838bf-119">これは、ユーザーがオペレーティングシステムを変更できるため、デバイスがマルウェアに対してより脆弱になる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="838bf-119">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="838bf-120">この設定を **オン**にすると、これらのデバイスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="838bf-120">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="838bf-121">ユーザーが Office アプリから個人用アプリにコンテンツをコピーすることを許可しない</span><span class="sxs-lookup"><span data-stu-id="838bf-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="838bf-122">この設定が**オン**の場合、ユーザーは作業ファイル内の情報を個人用ファイルにコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="838bf-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="838bf-123">この設定が**オフ**の場合、ユーザーは作業ファイルから個人のアプリまたは個人のアカウントに情報をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="838bf-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

