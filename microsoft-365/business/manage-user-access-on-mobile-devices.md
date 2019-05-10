---
title: ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: b49ec33f4899a25f92ffd9d7a25d3e435016749e
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660340"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="3520c-103">ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する</span><span class="sxs-lookup"><span data-stu-id="3520c-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="3520c-p101">ユーザーがモバイル デバイスから Office ファイルにアクセスする方法を制御するポリシーの設定は、既定では **オフ**になっています。セットアップ時に既定値を受け入れて、すべてのユーザーに適用される、Android、iOS、Windows 10 のアプリケーション ポリシーを作成することをお勧めします。セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3520c-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="3520c-107">ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定</span><span class="sxs-lookup"><span data-stu-id="3520c-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="3520c-108">次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3520c-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3520c-109">Setting</span><span class="sxs-lookup"><span data-stu-id="3520c-109">Setting</span></span>  <br/> |<span data-ttu-id="3520c-110">説明</span><span class="sxs-lookup"><span data-stu-id="3520c-110">Description</span></span>  <br/> |
|<span data-ttu-id="3520c-111">Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="3520c-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="3520c-112">この設定を **オン**にすると、ユーザーは、ユーザー名とパスワードの他に、別の認証フォームを提供しないと、モバイル デバイスで Office アプリを使用できません。</span><span class="sxs-lookup"><span data-stu-id="3520c-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="3520c-113">ログインに指定の回数失敗した場合に PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="3520c-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="3520c-114">承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="3520c-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="3520c-115">次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある</span><span class="sxs-lookup"><span data-stu-id="3520c-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="3520c-116">この設定は、もう一度サインインを求められるまで、どのくらいユーザーをアイドル状態にできるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3520c-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="3520c-117">脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="3520c-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="3520c-p102">賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。これは、ユーザーがオペレーティング システムを変更できるため、デバイスがマルウェアの危険にさらされる可能性が高くなることを意味します。この設定を **オン**にすると、これらのデバイスはブロックされます。  </span><span class="sxs-lookup"><span data-stu-id="3520c-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="3520c-121">ユーザーが Office アプリから個人用アプリにコンテンツをコピーすることを許可しない</span><span class="sxs-lookup"><span data-stu-id="3520c-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="3520c-122">この設定が**オン**の場合、ユーザーは作業ファイル内の情報を個人用ファイルにコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3520c-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="3520c-123">この設定が**オフ**の場合、ユーザーは作業ファイルから個人のアプリまたは個人のアカウントに情報をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="3520c-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

