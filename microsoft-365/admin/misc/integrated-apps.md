---
title: 統合アプリをオンまたはオフにする
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 統合アプリについて、およびサードパーティ製アプリがユーザーの Office 365 情報にアクセスできるようにする方法について説明します。
ms.openlocfilehash: 3c7c92e16b375fc374563e87ea2f6166c7384a29
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361388"
---
# <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="f8c20-103">統合アプリをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="f8c20-103">Turning Integrated Apps on or off</span></span>

<span data-ttu-id="f8c20-p101">統合アプリをオンにすると、組織のユーザーはサードパーティ アプリに Office 365 情報へのアクセスを許可することができます。 たとえば、サードパーティ アプリを使用している場合、そのアプリが予定表へのアクセスと OneDrive フォルダーにあるファイルの編集のために権限を与えるように求めてくることがあります。</span><span class="sxs-lookup"><span data-stu-id="f8c20-p101">When Integrated Apps is turned on, users in your organization can allow third-party apps to access their Office 365 information. For example, when someone uses a third-party app, that app might ask for permission to access their calendar and to edit files that are in a OneDrive folder.</span></span>

## <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="f8c20-106">統合アプリをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="f8c20-106">Turning Integrated Apps on or off</span></span>
<span data-ttu-id="f8c20-107"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c20-107"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="f8c20-108">ここでは、統合アプリをオンまたはオフにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8c20-108">Here's how to turn Integrated Apps on or off.</span></span>

1. <span data-ttu-id="f8c20-109">管理センターで、[**設定** \> [サービス&amp;のアドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページに移動し、[**統合アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8c20-109">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **Integrated apps**.</span></span>

2. <span data-ttu-id="f8c20-110">[**統合アプリ**] ページで、[統合アプリをオンまたはオフにする] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8c20-110">On the **Integrated Apps** page, select the option to turn Integrated Apps on or off.</span></span>

## <a name="more-info-on-integrated-apps"></a><span data-ttu-id="f8c20-111">統合アプリの詳細情報</span><span class="sxs-lookup"><span data-stu-id="f8c20-111">More info on Integrated Apps</span></span>
<span data-ttu-id="f8c20-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="f8c20-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="f8c20-113">統合するアプリとしては、組織内で開発したアプリ、または別の Office 365 の組織やサードパーティが開発したアプリを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f8c20-113">An integrated app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="f8c20-p102">統合アプリをオンにしている場合、統合されるアプリをユーザーが使おうとすると、ユーザー情報へのアクセスに必要なアクセス レベルを設定できるように、そのアプリが権限を求めてきます。 ユーザーは、Office 365 情報に対して自分自身が持っているアクセス権のみをアプリに与えることができます。 他のユーザーの情報に対して、アプリにアクセス権を与えることはできません。</span><span class="sxs-lookup"><span data-stu-id="f8c20-p102">When Integrated Apps is turned on and an app is used, the app asks for permission to set the level of access it needs when it accesses the user's information. A user can give access only to apps they own that access their Office 365 information. They can't give an app access to any other user's information.</span></span>

<span data-ttu-id="f8c20-p103">Office 365 で統合アプリを使用する場合、ユーザー権限と管理者権限の 2 種類の権限を使用します。 たとえば、統合アプリに対して組織を有効にしており、ユーザーがサードパーティ アプリを使用する場合、ユーザー プロファイルの詳細の読み取り、ファイルの編集または削除、サイト コレクションに含まれているアイテムの読み取り、そのユーザーとしてのメール送信などのために、アプリがユーザーの権限を求めてくることがあります。</span><span class="sxs-lookup"><span data-stu-id="f8c20-p103">There are two kinds of permissions that are used when using Integrated Apps in Office 365: user permissions and admin permissions. For example, when your organization is enabled for Integrated Apps and a user uses a third-party app, the app might ask for the user's permission to read their user profile details, edit or delete their files, read items contained in site collections, and send email as that user.</span></span>

![統合アプリのユーザーの権限](../../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)

<span data-ttu-id="f8c20-120">管理者が組織内のすべてのユーザーに対してアプリを登録すると、そのアプリが組織内の情報とリソースにアクセスできるようにするためのアクセス許可を求められます。</span><span class="sxs-lookup"><span data-stu-id="f8c20-120">If an admin registers an app for all users in an organization, he or she is asked for permission to let that app access information and resources in the organization.</span></span> <span data-ttu-id="f8c20-121">管理者がアプリにアクセス権を与えたら、それ以降、組織内の他のユーザーがそのアプリを使用するときに、アクセス権を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="f8c20-121">After this, when other users in the organization use that app, they won't be asked for permission.</span></span> <span data-ttu-id="f8c20-122">管理者がアプリを登録する場合、その管理者はアプリの開発者が信頼できる相手であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8c20-122">When an admin registers an app, that admin must make sure that they trust that app's publisher.</span></span> <span data-ttu-id="f8c20-123">アプリの登録の詳細については、「[アプリケーションの追加、更新、および削除](https://go.microsoft.com/fwlink/p/?LinkID=518600)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8c20-123">For details on registering an app, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/p/?LinkID=518600).</span></span>

![統合アプリの管理者権限](../../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)

<span data-ttu-id="f8c20-p105">統合アプリがオフになった場合でも、既にインストールされており、情報へのアクセス権が与えられたアプリはアンインストールされません。アクセス権も削除されません。 統合アプリがオフになっていても、管理者はまだ、ユーザーが使用できるようにアプリを登録して、これらのアプリにユーザー情報へのアクセスを許可することができます。 登録済みアプリを削除する方法とその権限の詳細については、「[アプリケーションの追加、更新、および削除](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8c20-p105">If Integrated Apps is turned off, apps that have already been installed and have permission to access information won't be uninstalled, and the permissions won't be removed. Even though Integrated Apps is turned off, admins can still register apps to make them available to their users and allow those apps access to the users' information. For details on removing a registered application and it's permissions, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).</span></span>


