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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: ユーザーがモバイルデバイスから Office アプリや作業ファイルにアクセスする方法を管理できる保護ポリシーについて説明します。
ms.openlocfilehash: b2b828cf2e201360f12b8fadcb395e72958230f6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471069"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="8cc6a-103">ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する</span><span class="sxs-lookup"><span data-stu-id="8cc6a-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="8cc6a-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="8cc6a-105">ユーザーがモバイル デバイスから Office ファイルにアクセスする方法を制御するポリシーの設定は、既定では **オフ**になっています。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="8cc6a-106">すべてのユーザーに適用される Android、iOS、Windows 10 のアプリケーションポリシーを作成するには、セットアップ時に既定値を受け入れることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="8cc6a-107">セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="8cc6a-108">ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定</span><span class="sxs-lookup"><span data-stu-id="8cc6a-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="8cc6a-109">次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8cc6a-110">設定</span><span class="sxs-lookup"><span data-stu-id="8cc6a-110">Setting</span></span>  <br/> |<span data-ttu-id="8cc6a-111">説明</span><span class="sxs-lookup"><span data-stu-id="8cc6a-111">Description</span></span>  <br/> |
|<span data-ttu-id="8cc6a-112">Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="8cc6a-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="8cc6a-113">この設定が**オンになって**いる場合は、ユーザーのモバイルデバイスで Office アプリを使用できるようにするために、ユーザー名とパスワードに加えて、別の形式の認証を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="8cc6a-114">ログインに指定の回数失敗した場合に PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="8cc6a-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="8cc6a-115">承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="8cc6a-116">次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある</span><span class="sxs-lookup"><span data-stu-id="8cc6a-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="8cc6a-117">この設定により、ユーザーがもう一度サインインするように求めるメッセージが表示されるまでの待機時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="8cc6a-118">脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="8cc6a-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="8cc6a-119">賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="8cc6a-120">これは、ユーザーがオペレーティングシステムを変更できるため、デバイスがマルウェアに対してより脆弱になる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="8cc6a-121">この設定を **オン**にすると、これらのデバイスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="8cc6a-122">ユーザーが Office アプリから個人用アプリにコンテンツをコピーすることを許可しない</span><span class="sxs-lookup"><span data-stu-id="8cc6a-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="8cc6a-123">この設定が**オン**の場合、ユーザーは作業ファイル内の情報を個人用ファイルにコピーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="8cc6a-124">この設定が**オフ**の場合、ユーザーは作業ファイルから個人のアプリまたは個人のアカウントに情報をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="8cc6a-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

