---
title: Canvas でMicrosoft Teams会議を使用する
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: キャンバスMicrosoft Teams会議を統合する
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454675"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="0b3c0-103">Canvas でMicrosoft Teams会議を使用する</span><span class="sxs-lookup"><span data-stu-id="0b3c0-103">Use Microsoft Teams meetings with Canvas</span></span>

<span data-ttu-id="0b3c0-104">Microsoft Teamsは、ラーニング ツール相互運用性 (LTI) アプリであり、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-104">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="0b3c0-105">ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="0b3c0-106">Microsoft Office 365管理者</span><span class="sxs-lookup"><span data-stu-id="0b3c0-106">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="0b3c0-107">Instructure Canvas 内の Microsoft Teams 統合を管理する前に、Canvas の管理セットアップを完了する前に、キャンバスの **microsoft-Teams-Sync-for-Canvas** Azure アプリを Microsoft Azure テナントの教育機関の Microsoft Office 365 管理者によって承認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-107">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="0b3c0-108">Canvas にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-108">Sign in to Canvas.</span></span>

2. <span data-ttu-id="0b3c0-109">グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-109">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="0b3c0-110">管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-110">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="0b3c0-111">Microsoft テナント名とログイン属性を入力します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-111">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="0b3c0-112">login 属性は、Canvas ユーザーをユーザーに関連付Azure Active Directoryされます。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-112">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="0b3c0-113">[完了 **したら設定** 更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-113">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="0b3c0-114">Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-114">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="0b3c0-115">Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-115">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissions](media/permissions.png)

7. <span data-ttu-id="0b3c0-117">**[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-117">Select **Accept**.</span></span>

8. <span data-ttu-id="0b3c0-118">トグルをオンにしてMicrosoft Teams同期を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-118">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="0b3c0-120">Canvas Admin</span><span class="sxs-lookup"><span data-stu-id="0b3c0-120">Canvas Admin</span></span>

<span data-ttu-id="0b3c0-121">LTI 1.3 Microsoft Teamsをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-121">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="0b3c0-122">Canvas Admin として、環境内に会議 LTI Microsoft Teamsを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-122">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="0b3c0-123">アプリの LTI クライアント ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-123">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="0b3c0-124">Microsoft Teams会議 - 17000000000000703</span><span class="sxs-lookup"><span data-stu-id="0b3c0-124">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="0b3c0-125">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="0b3c0-125">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="0b3c0-126">[+**アプリ] を** 選択して、LTI Teamsを追加します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-126">Select **+ App** to add the Teams LTI apps.</span></span>

   ![外部アプリ](media/external-apps.png)

3. <span data-ttu-id="0b3c0-128">構成 **の種類として [クライアント ID 別** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-128">Select **By Client ID** for configuration type.</span></span>

   ![アプリの追加](media/add-app.png)

4. <span data-ttu-id="0b3c0-130">指定されたクライアント ID を入力し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-130">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="0b3c0-131">確認のためにクライアント ID のMicrosoft Teams LTI アプリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-131">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="0b3c0-132">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-132">Select **Install**.</span></span>

   <span data-ttu-id="0b3c0-133">会議Microsoft Teams LTI アプリが外部アプリの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-133">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="0b3c0-134">キャンバス コースを有効にする</span><span class="sxs-lookup"><span data-stu-id="0b3c0-134">Enable for Canvas Courses</span></span>

<span data-ttu-id="0b3c0-135">コース内で LTI を使用するには、Canvas コースの講師が統合同期を有効にする必要があります。各コースは、作成する対応するTeams教員が有効にする必要があります。作成のグローバルメカニズムTeamsはありません。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-135">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="0b3c0-136">これは、不要なデータが作成されるのを防ぐためにTeams設計されています。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-136">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="0b3c0-137">各コースで LTI[](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)を有効にし、統合セットアップを完了するには、教員のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b3c0-137">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
