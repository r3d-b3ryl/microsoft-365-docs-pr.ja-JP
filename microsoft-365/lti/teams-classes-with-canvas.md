---
title: Canvas でMicrosoft Teamsクラスを使用する
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
description: キャンバスMicrosoft Teamsクラスを統合する
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454687"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="ef8c4-103">Canvas でMicrosoft Teamsクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="ef8c4-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="ef8c4-104">Microsoft Teamsクラスは、ラーニング ツール相互運用性 (LTI) アプリで、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="ef8c4-105">ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="ef8c4-106">展開前の前提条件</span><span class="sxs-lookup"><span data-stu-id="ef8c4-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="ef8c4-107">LTI の現在Teamsクラスは、キャンバス ユーザーと制限されたスコープ内Microsoft Azure Active Directory (AAD) の同期のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="ef8c4-108">テナントは、Microsoft AAD のキャンバス フィールド (電子メール、ユーザー ID、または SIS ID) と UPN の間で完全に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="ef8c4-109">同期機能に柔軟に対応するために取り組み中ですが、その間、Canvas のユーザーが AAD の UPN と一致しない場合、Canvas と同期された Teams クラスには追加されません。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="ef8c4-110">Canvas と Microsoft の間でユーザーをマッピングするには、1 つの Microsoft テナントのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="ef8c4-111">グループの重複を回避するには、LTI クラスを使用する前Teams SDS をオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="ef8c4-112">Microsoft Office 365管理者</span><span class="sxs-lookup"><span data-stu-id="ef8c4-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="ef8c4-113">Instructure Canvas 内の Microsoft Teams 統合を管理する前に、Canvas の管理セットアップを完了する前に、キャンバスの **microsoft-Teams-Sync-for-Canvas** Azure アプリを Microsoft Azure テナントの教育機関の Microsoft Office 365 管理者によって承認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="ef8c4-114">Canvas にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="ef8c4-115">グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="ef8c4-116">管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="ef8c4-117">トグルMicrosoft Teamsして同期を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="ef8c4-119">Microsoft テナント名とログイン属性を入力します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="ef8c4-120">login 属性は、Canvas ユーザーをユーザーに関連付Azure Active Directoryされます。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="ef8c4-121">[完了 **したら設定** 更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="ef8c4-122">Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="ef8c4-123">Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![permissions](media/permissions.png)

8. <span data-ttu-id="ef8c4-125">**[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="ef8c4-126">Canvas Admin</span><span class="sxs-lookup"><span data-stu-id="ef8c4-126">Canvas Admin</span></span>

<span data-ttu-id="ef8c4-127">LTI 1.3 Microsoft Teamsをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="ef8c4-128">Canvas 管理者として、環境内に LTI Microsoft Teamsクラスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="ef8c4-129">アプリの LTI クライアント ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="ef8c4-130">Microsoft Teamsクラス - 17000000000000570</span><span class="sxs-lookup"><span data-stu-id="ef8c4-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="ef8c4-131">Access **Admin settings**  >  **Apps**.</span><span class="sxs-lookup"><span data-stu-id="ef8c4-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="ef8c4-132">[+**アプリ] を** 選択して、LTI Teamsを追加します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![外部アプリ](media/external-apps.png)

3. <span data-ttu-id="ef8c4-134">構成 **の種類として [クライアント ID 別** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-134">Select **By Client ID** for configuration type.</span></span>

   ![アプリの追加](media/add-app.png)

4. <span data-ttu-id="ef8c4-136">指定されたクライアント ID を入力し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="ef8c4-137">確認のためにクライアント ID Microsoft Teamsクラス LTI アプリ名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="ef8c4-138">**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-138">Select **Install**.</span></span>

   <span data-ttu-id="ef8c4-139">LTI Microsoft Teamsクラスは、外部アプリの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="ef8c4-140">キャンバス コースの LTI アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="ef8c4-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="ef8c4-141">コース内で LTI アプリを使用するには、Canvas コースの講師が統合同期を有効にする必要があります。各コースは、対応するチームを作成するために講師が有効にする必要があります。チームを作成するためのグローバルメカニズムはありません。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="ef8c4-142">これは、望ましくないチームが作成されるのを防ぐための予防措置として設計されています。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="ef8c4-143">各コースで LTI アプリを [有効](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) にし、統合セットアップを完了するには、教員のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef8c4-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
