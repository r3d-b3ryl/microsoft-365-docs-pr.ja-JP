---
title: Canvas でMicrosoft Teamsクラスを使用する
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: キャンバスMicrosoft Teamsクラスを統合する
ms.openlocfilehash: 1a16d6a4f5e0cfbb592c335163bb4e33fd3c1301
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821902"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="bedc5-103">Canvas でMicrosoft Teamsクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="bedc5-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bedc5-104">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="bedc5-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bedc5-105">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="bedc5-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="bedc5-106">Microsoft Teamsはラーニング ツール相互運用性 (LTI) アプリで、教育者と学生が学習管理システム (LMS) と学生の間を簡単に移動Teams。</span><span class="sxs-lookup"><span data-stu-id="bedc5-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="bedc5-107">ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bedc5-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="bedc5-108">Microsoft Office 365管理者</span><span class="sxs-lookup"><span data-stu-id="bedc5-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="bedc5-109">Instructure Canvas 内の Microsoft Teams 統合を管理する前に、Canvas の管理セットアップを完了する前に、キャンバスの **microsoft-Teams-Sync-for-Canvas** Azure アプリを Microsoft Azure テナントの教育機関の Microsoft Office 365 管理者によって承認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="bedc5-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="bedc5-110">Canvas にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bedc5-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="bedc5-111">グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="bedc5-112">管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="bedc5-113">Microsoft テナント名とログイン属性を入力します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="bedc5-114">login 属性は、Canvas ユーザーをユーザーに関連付Azure Active Directoryされます。</span><span class="sxs-lookup"><span data-stu-id="bedc5-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="bedc5-115">[完了 **したら設定** 更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="bedc5-116">Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="bedc5-117">Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="bedc5-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissions](media/permissions.png)

7. <span data-ttu-id="bedc5-119">**[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="bedc5-120">トグルをオンにしてMicrosoft Teams同期を有効にします。</span><span class="sxs-lookup"><span data-stu-id="bedc5-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="bedc5-122">Canvas Admin</span><span class="sxs-lookup"><span data-stu-id="bedc5-122">Canvas Admin</span></span>

<span data-ttu-id="bedc5-123">LTI 1.3 Microsoft Teamsをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="bedc5-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="bedc5-124">Canvas 管理者として、環境内に LTI Microsoft Teamsクラスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bedc5-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="bedc5-125">アプリの LTI クライアント ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="bedc5-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="bedc5-126">Microsoft Teamsクラス - 17000000000000570</span><span class="sxs-lookup"><span data-stu-id="bedc5-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="bedc5-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="bedc5-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="bedc5-128">[+**アプリ] を** 選択して、LTI Teamsを追加します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![外部アプリ](media/external-apps.png)

3. <span data-ttu-id="bedc5-130">構成 **の種類として [クライアント ID 別** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-130">Select **By Client ID** for configuration type.</span></span>

   ![アプリの追加](media/add-app.png)

4. <span data-ttu-id="bedc5-132">指定されたクライアント ID を入力し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bedc5-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="bedc5-133">確認のためにクライアント ID Microsoft Teamsクラス LTI アプリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bedc5-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="bedc5-134">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bedc5-134">Select **Install**.</span></span>

   <span data-ttu-id="bedc5-135">LTI Microsoft Teamsクラスは、外部アプリの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="bedc5-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
