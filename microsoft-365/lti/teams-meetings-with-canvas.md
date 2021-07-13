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
ms.openlocfilehash: 7e13052cb029fef369f6386c2039785e40acc4ff
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409094"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="b402a-103">Canvas でMicrosoft Teams会議を使用する</span><span class="sxs-lookup"><span data-stu-id="b402a-103">Use Microsoft Teams meetings with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b402a-104">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="b402a-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b402a-105">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="b402a-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b402a-106">Microsoft Teamsは、ラーニング ツール相互運用性 (LTI) アプリであり、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b402a-106">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="b402a-107">ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b402a-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="b402a-108">Microsoft Office 365管理者</span><span class="sxs-lookup"><span data-stu-id="b402a-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="b402a-109">Instructure Canvas 内の Microsoft Teams 統合を管理する前に、Canvas の管理セットアップを完了する前に、キャンバスの **microsoft-Teams-Sync-for-Canvas** Azure アプリを Microsoft Azure テナントの教育機関の Microsoft Office 365 管理者によって承認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b402a-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="b402a-110">Canvas にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b402a-110">Sign in to Canvas.</span></span>

2. <span data-ttu-id="b402a-111">グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="b402a-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="b402a-112">管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="b402a-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="b402a-113">Microsoft テナント名とログイン属性を入力します。</span><span class="sxs-lookup"><span data-stu-id="b402a-113">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="b402a-114">login 属性は、Canvas ユーザーをユーザーに関連付Azure Active Directoryされます。</span><span class="sxs-lookup"><span data-stu-id="b402a-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="b402a-115">[完了 **したら設定** 更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b402a-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="b402a-116">Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="b402a-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="b402a-117">Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="b402a-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissions](media/permissions.png)

7. <span data-ttu-id="b402a-119">**[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b402a-119">Select **Accept**.</span></span>

8. <span data-ttu-id="b402a-120">トグルをオンにしてMicrosoft Teams同期を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b402a-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="b402a-122">Canvas Admin</span><span class="sxs-lookup"><span data-stu-id="b402a-122">Canvas Admin</span></span>

<span data-ttu-id="b402a-123">LTI 1.3 Microsoft Teamsをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="b402a-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="b402a-124">Canvas Admin として、環境内に会議 LTI Microsoft Teamsを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b402a-124">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="b402a-125">アプリの LTI クライアント ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="b402a-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="b402a-126">Microsoft Teams会議 - 17000000000000703</span><span class="sxs-lookup"><span data-stu-id="b402a-126">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="b402a-127">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="b402a-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="b402a-128">[+**アプリ] を** 選択して、LTI Teamsを追加します。</span><span class="sxs-lookup"><span data-stu-id="b402a-128">Select **+ App** to add the Teams LTI apps.</span></span>

   ![外部アプリ](media/external-apps.png)

3. <span data-ttu-id="b402a-130">構成 **の種類として [クライアント ID 別** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b402a-130">Select **By Client ID** for configuration type.</span></span>

   ![アプリの追加](media/add-app.png)

4. <span data-ttu-id="b402a-132">指定されたクライアント ID を入力し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b402a-132">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="b402a-133">確認のためにクライアント ID のMicrosoft Teams LTI アプリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b402a-133">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="b402a-134">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b402a-134">Select **Install**.</span></span>

   <span data-ttu-id="b402a-135">会議Microsoft Teams LTI アプリが外部アプリの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b402a-135">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="b402a-136">キャンバス コースを有効にする</span><span class="sxs-lookup"><span data-stu-id="b402a-136">Enable for Canvas Courses</span></span>

<span data-ttu-id="b402a-137">コース内で LTI を使用するには、Canvas コースの講師が統合同期を有効にする必要があります。各コースは、作成する対応するTeams教員が有効にする必要があります。作成のグローバルメカニズムTeamsはありません。</span><span class="sxs-lookup"><span data-stu-id="b402a-137">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="b402a-138">これは、不要なデータが作成されるのを防ぐためにTeams設計されています。</span><span class="sxs-lookup"><span data-stu-id="b402a-138">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="b402a-139">各コースで LTI[](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)を有効にし、統合セットアップを完了するには、教員のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b402a-139">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
