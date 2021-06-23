---
title: Blackboard でMicrosoft Teamsクラスを使用する
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
description: 管理Microsoft Teamsシステムにラーニングクラスを統合する
ms.openlocfilehash: 940c5c695d602ddce6ea49b1f914f2345fbeb7e5
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083245"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a><span data-ttu-id="9de1c-103">Blackboard でMicrosoft Teamsクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="9de1c-103">Use Microsoft Teams classes with Blackboard</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9de1c-104">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="9de1c-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9de1c-105">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="9de1c-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9de1c-106">Microsoft Teamsクラスは、ラーニング ツール相互運用性 (LTI) アプリで、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9de1c-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="9de1c-107">ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9de1c-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="9de1c-108">テナントでアプリをMicrosoft Azureする</span><span class="sxs-lookup"><span data-stu-id="9de1c-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="9de1c-109">次のタスクは、管理者と Blackboard Learn Ultra Microsoft Office 365によって完了します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="9de1c-110">Blackboard Learn Ultra 内の統合を管理する前に、Microsoft Office 365 管理者は、教育機関の Microsoft Azure テナントの Blackboard **MSFT Teams** for Learn Ultra Azure アプリを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9de1c-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="9de1c-111">Microsoft テナント ID を見つける。</span><span class="sxs-lookup"><span data-stu-id="9de1c-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="9de1c-112">テナント [を検索する方法を参照してください](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)。</span><span class="sxs-lookup"><span data-stu-id="9de1c-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="9de1c-113">次の例に従って、Microsoft Identity Platform Admin Consent Endpoint をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="9de1c-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="9de1c-114">{tenant} を組織の Microsoft テナント ID に置き換える。</span><span class="sxs-lookup"><span data-stu-id="9de1c-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="9de1c-115">統合アプリの登録</span><span class="sxs-lookup"><span data-stu-id="9de1c-115">Register the integration apps</span></span>

<span data-ttu-id="9de1c-116">Blackboard Learn Ultra 管理者として、テスト環境内に 2 つの LTI 1.3 統合アプリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9de1c-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="9de1c-117">名簿の同期をTeamsする Blackboard Learn クラスの統合</span><span class="sxs-lookup"><span data-stu-id="9de1c-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="9de1c-118">クラス Microsoft Teams LTI アプリ</span><span class="sxs-lookup"><span data-stu-id="9de1c-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="9de1c-119">両方のアプリに対して次の LTI クライアント ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="9de1c-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="9de1c-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="9de1c-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="9de1c-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="9de1c-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="9de1c-122">管理パネルにアクセスし、[統合] **で** LTI ツール プロバイダーを探します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![これは、[LTI ツール プロバイダー] ダイアログボックスにプロバイダーの一覧が表示されます。](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="9de1c-124">**[LTI1.3/Advantage Tool の登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="9de1c-125">指定されたクライアント ID (Blackboard または Microsoft) の最初の ID を入力し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

5. <span data-ttu-id="9de1c-126">事前に設定された設定を確認し、ツールの状態が承認済みとしてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9de1c-126">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="9de1c-127">下までスクロールし、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-127">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="9de1c-128">前の手順を繰り返して、環境内で 2 番目の LTI アプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-128">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="9de1c-129">REST アプリケーションとクロスオリジン リソース共有のセットアップ</span><span class="sxs-lookup"><span data-stu-id="9de1c-129">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="9de1c-130">Blackboard Learn Ultra 管理者は、REST アプリケーションとクロス オリジン リソース共有構成を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9de1c-130">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="9de1c-131">REST アプリケーションをセットアップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-131">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="9de1c-132">[管理ツールの学習] にアクセスし、[統合] セクションから **[REST API の** 統合 **] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-132">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="9de1c-133">[**統合の作成] を** 選択し、統合 LTI ツールに対して入力したのと同じアプリケーション/クライアント ID Teams入力します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-133">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="9de1c-134">[ユーザーの学習] を入力します (これは、管理者のユーザー名を学習する場合があります)、または [参照] を選択 **して** 検索します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-134">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="9de1c-135">[エンド **ユーザー アクセス] で** **[はい] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-135">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="9de1c-136">[ユーザー **として機能\*\*\*\*する承認] で [はい] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="9de1c-136">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="9de1c-137">[完了 **したら送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-137">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="9de1c-138">クロスオリジン リソース共有のセットアップ</span><span class="sxs-lookup"><span data-stu-id="9de1c-138">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="9de1c-139">[管理ツールの学習] にアクセスし、[統合] セクションから [クロスオリジン **リソース共有\*\*\*\*] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-139">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="9de1c-140">[構成 **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-140">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="9de1c-141">原点 `https://bb-ms-teams-ultra-ext.api.blackboard.com` に入力します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-141">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="9de1c-142">[許可するヘッダー **] に [承認\*\*\*\*] という単語を追加します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-142">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="9de1c-143">[使用可能 **] を [はい** ] **に設定します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-143">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="9de1c-144">[完了 **したら送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-144">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="9de1c-145">Blackboard Learn でTeamsを有効にする</span><span class="sxs-lookup"><span data-stu-id="9de1c-145">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="9de1c-146">LTI ツールを有効にしたら、次の手順では、独自のテナントから Microsoft Class Teams統合をMicrosoft Office 365します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-146">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="9de1c-147">これを行うには、Blackboard Learn Ultra 管理者として次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-147">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="9de1c-148">[**管理ツールと**  >  **ユーティリティの詳細] で**、[統合管理者] **Microsoft Teamsを選択します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-148">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![使用可能なツールの一覧を含むツールとユーティリティ ダイアログ](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="9de1c-150">[有効にする] チェック **ボックスをオンMicrosoft Teams。**</span><span class="sxs-lookup"><span data-stu-id="9de1c-150">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="9de1c-151">[Microsoft O365 Admin] のセクションで参照されているテナント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="9de1c-151">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="9de1c-152">アプリが O365 管理者によって承認されるまで、設定を保存できない。「[アプリを承認する」を参照Microsoft Azureします](#approve-the-app-in-the-microsoft-azure-tenant)。</span><span class="sxs-lookup"><span data-stu-id="9de1c-152">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="9de1c-153">グローバル O365 管理者が Microsoft テナントの Blackboard Teamsを承認した場合は、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9de1c-153">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
