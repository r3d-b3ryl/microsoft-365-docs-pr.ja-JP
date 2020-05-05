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
description: 統合アプリについて、およびサードパーティ製アプリがユーザーの Microsoft 365 情報にアクセスできるようにする方法について説明します。
ms.openlocfilehash: 2e292afc4ab33eef1ace91808f93588b9cec4702
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022110"
---
# <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="91091-103">統合アプリをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="91091-103">Turning Integrated Apps on or off</span></span>

<span data-ttu-id="91091-104">統合アプリが有効になっている場合、組織内のユーザーは、サードパーティ製アプリで Microsoft 365 の情報にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="91091-104">When Integrated Apps is turned on, users in your organization can allow third-party apps to access their Microsoft 365 information.</span></span> <span data-ttu-id="91091-105">たとえば、サードパーティ アプリを使用している場合、そのアプリが予定表へのアクセスと OneDrive フォルダーにあるファイルの編集のために権限を与えるように求めてくることがあります。</span><span class="sxs-lookup"><span data-stu-id="91091-105">For example, when someone uses a third-party app, that app might ask for permission to access their calendar and to edit files that are in a OneDrive folder.</span></span>

## <a name="turning-integrated-apps-on-or-off"></a><span data-ttu-id="91091-106">統合アプリをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="91091-106">Turning Integrated Apps on or off</span></span>
<span data-ttu-id="91091-107"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="91091-107"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="91091-108">ここでは、統合アプリをオンまたはオフにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91091-108">Here's how to turn Integrated Apps on or off.</span></span>

1. <span data-ttu-id="91091-109">Microsoft 365 管理センターで、[**設定** \>の**設定**] \>ページの [**サービス**] タブに移動し、[**統合アプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="91091-109">In the Microsoft 365 admin center, go to the **Settings** \> **Settings** page, \> **Services** tab, and then select **Integrated apps**.</span></span>

2. <span data-ttu-id="91091-110">[**統合アプリ**] ページで、[統合アプリをオンまたはオフにする] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="91091-110">On the **Integrated Apps** page, select the option to turn Integrated Apps on or off.</span></span>

## <a name="more-info-on-integrated-apps"></a><span data-ttu-id="91091-111">統合アプリの詳細情報</span><span class="sxs-lookup"><span data-stu-id="91091-111">More info on Integrated Apps</span></span>
<span data-ttu-id="91091-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="91091-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="91091-113">統合アプリは、自分の組織内から作成することも、別の組織またはサードパーティから入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="91091-113">An integrated app can be created from within your own organization, or it can come from another organization or a third-party.</span></span>

<span data-ttu-id="91091-114">統合アプリをオンにしている場合、統合されるアプリをユーザーが使おうとすると、ユーザー情報へのアクセスに必要なアクセス レベルを設定できるように、そのアプリが権限を求めてきます。</span><span class="sxs-lookup"><span data-stu-id="91091-114">When Integrated Apps is turned on and an app is used, the app asks for permission to set the level of access it needs when it accesses the user's information.</span></span> <span data-ttu-id="91091-115">ユーザーは、Microsoft 365 の情報にアクセスする、自分が所有しているアプリにのみアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="91091-115">A user can give access only to apps they own that access their Microsoft 365 information.</span></span> <span data-ttu-id="91091-116">他のユーザーの情報に対して、アプリにアクセス権を与えることはできません。</span><span class="sxs-lookup"><span data-stu-id="91091-116">They can't give an app access to any other user's information.</span></span>

<span data-ttu-id="91091-117">Microsoft 365 で統合アプリを使用するときに使用されるアクセス許可には、ユーザー権限と管理者権限の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="91091-117">There are two kinds of permissions that are used when using Integrated Apps in Microsoft 365: user permissions and admin permissions.</span></span> <span data-ttu-id="91091-118">たとえば、統合アプリに対して組織を有効にしており、ユーザーがサードパーティ アプリを使用する場合、ユーザー プロファイルの詳細の読み取り、ファイルの編集または削除、サイト コレクションに含まれているアイテムの読み取り、そのユーザーとしてのメール送信などのために、アプリがユーザーの権限を求めてくることがあります。</span><span class="sxs-lookup"><span data-stu-id="91091-118">For example, when your organization is enabled for Integrated Apps and a user uses a third-party app, the app might ask for the user's permission to read their user profile details, edit or delete their files, read items contained in site collections, and send email as that user.</span></span>

![統合アプリのユーザーの権限](../../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)

<span data-ttu-id="91091-120">管理者が組織内のすべてのユーザーに対してアプリを登録すると、そのアプリが組織内の情報とリソースにアクセスできるようにするためのアクセス許可を求められます。</span><span class="sxs-lookup"><span data-stu-id="91091-120">If an admin registers an app for all users in an organization, he or she is asked for permission to let that app access information and resources in the organization.</span></span> <span data-ttu-id="91091-121">管理者がアプリにアクセス権を与えたら、それ以降、組織内の他のユーザーがそのアプリを使用するときに、アクセス権を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="91091-121">After this, when other users in the organization use that app, they won't be asked for permission.</span></span> <span data-ttu-id="91091-122">管理者がアプリを登録する場合、その管理者はアプリの開発者が信頼できる相手であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91091-122">When an admin registers an app, that admin must make sure that they trust that app's publisher.</span></span> <span data-ttu-id="91091-123">アプリの登録の詳細については、「[アプリケーションの追加、更新、および削除](https://go.microsoft.com/fwlink/p/?LinkID=518600)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91091-123">For details on registering an app, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/p/?LinkID=518600).</span></span>

![統合アプリの管理者権限](../../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)

<span data-ttu-id="91091-p105">統合アプリがオフになった場合でも、既にインストールされており、情報へのアクセス権が与えられたアプリはアンインストールされません。アクセス権も削除されません。 統合アプリがオフになっていても、管理者はまだ、ユーザーが使用できるようにアプリを登録して、これらのアプリにユーザー情報へのアクセスを許可することができます。 登録済みアプリを削除する方法とその権限の詳細については、「[アプリケーションの追加、更新、および削除](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91091-p105">If Integrated Apps is turned off, apps that have already been installed and have permission to access information won't be uninstalled, and the permissions won't be removed. Even though Integrated Apps is turned off, admins can still register apps to make them available to their users and allow those apps access to the users' information. For details on removing a registered application and it's permissions, see [Adding, Updating and Removing an Application](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409).</span></span>


