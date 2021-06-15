---
title: ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: ユーザーがモバイル デバイスからアプリや作業ファイルにアクセスする方法Office保護ポリシーについて説明します。
ms.openlocfilehash: 7602b712f2dfc3ba369fd76979baaaa8d5da5c5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925281"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="97432-103">ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する</span><span class="sxs-lookup"><span data-stu-id="97432-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="97432-104">この記事は、このMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="97432-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="97432-105">ユーザーがモバイル デバイスから Office ファイルにアクセスする方法を制御するポリシーの設定は、既定では **オフ** になっています。</span><span class="sxs-lookup"><span data-stu-id="97432-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="97432-106">セットアップ時に既定値を受け入れて、すべてのユーザーに適用される Android、iOS、および Windows 10アプリケーション ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="97432-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="97432-107">セットアップが完了したら、追加のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="97432-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="97432-108">ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定</span><span class="sxs-lookup"><span data-stu-id="97432-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="97432-109">次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="97432-109">The following settings are available to manage how users access Office work files:</span></span>

|<span data-ttu-id="97432-110">Setting</span><span class="sxs-lookup"><span data-stu-id="97432-110">Setting</span></span>  <br/> |<span data-ttu-id="97432-111">説明</span><span class="sxs-lookup"><span data-stu-id="97432-111">Description</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="97432-112">Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある</span><span class="sxs-lookup"><span data-stu-id="97432-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="97432-113">この設定が **[オン**] の場合、ユーザーはモバイル デバイスでアプリを使用する前に、ユーザー名とパスワードに加えて、別の形式の認証Office必要があります。</span><span class="sxs-lookup"><span data-stu-id="97432-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="97432-114">ログインに指定の回数失敗した場合に PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="97432-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="97432-115">承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="97432-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="97432-116">次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある</span><span class="sxs-lookup"><span data-stu-id="97432-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="97432-117">この設定は、ユーザーが再度サインインするように求めるメッセージが表示されるまでアイドル状態にできる期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="97432-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="97432-118">脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="97432-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="97432-119">賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="97432-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="97432-120">つまり、ユーザーはオペレーティング システムを変更できます。これにより、デバイスがマルウェアの影響を受けやすくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="97432-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="97432-121">この設定を **オン** にすると、これらのデバイスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="97432-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="97432-122">ユーザーがアプリから個人用アプリにコンテンツをコピー Office許可しない</span><span class="sxs-lookup"><span data-stu-id="97432-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="97432-123">この設定が **[オン] の** 場合、ユーザーは作業ファイル内の情報を個人用ファイルにコピーできない。</span><span class="sxs-lookup"><span data-stu-id="97432-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="97432-124">この設定が **[オフ] の場合**、ユーザーは作業ファイルから個人アプリまたは個人アカウントに情報をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="97432-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

