---
title: ラーニング管理システムで Microsoft Teams クラスを使用する
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
description: 学習管理システムに Microsoft Teams クラスを統合する
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327785"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a><span data-ttu-id="e8a69-103">ラーニング管理システムで Microsoft Teams クラスを使用する</span><span class="sxs-lookup"><span data-stu-id="e8a69-103">Use Microsoft Teams classes in your Learning Management System</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8a69-104">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="e8a69-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e8a69-105">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="e8a69-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e8a69-106">Microsoft Teams クラス のチームは、教育者と学生が学習管理システム (LMS) と Teams の間を簡単に移動するのに役立つラーニング ツール相互運用性 (LTI) アプリです。</span><span class="sxs-lookup"><span data-stu-id="e8a69-106">Microsoft Teams class teams is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="e8a69-107">ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e8a69-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="e8a69-108">Microsoft Azure テナントでアプリを承認する</span><span class="sxs-lookup"><span data-stu-id="e8a69-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="e8a69-109">次のタスクは、管理者 365 管理者Microsoft Office Blackboard Learn Ultra 管理者によって完了します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="e8a69-110">Blackboard Learn Ultra 内の統合を管理する前に、Microsoft Office 365 管理者は、教育機関の Microsoft Azure テナント用の Blackboard **MSFT Teams for** Learn Ultra Azure アプリを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a69-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="e8a69-111">Microsoft テナント ID を見つける。</span><span class="sxs-lookup"><span data-stu-id="e8a69-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="e8a69-112">テナント [を検索する方法を参照してください](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)。</span><span class="sxs-lookup"><span data-stu-id="e8a69-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="e8a69-113">次の例に従って、Microsoft Identity Platform Admin Consent Endpoint をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="e8a69-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="e8a69-114">{tenant} を組織の Microsoft テナント ID に置き換える。</span><span class="sxs-lookup"><span data-stu-id="e8a69-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="e8a69-115">統合アプリの登録</span><span class="sxs-lookup"><span data-stu-id="e8a69-115">Register the integration apps</span></span>

<span data-ttu-id="e8a69-116">Blackboard Learn Ultra 管理者として、テスト環境内に 2 つの LTI 1.3 統合アプリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a69-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="e8a69-117">名簿の同期をサポートする Blackboard Learn Class Teams の統合</span><span class="sxs-lookup"><span data-stu-id="e8a69-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="e8a69-118">Microsoft Teams クラス チーム LTI アプリ</span><span class="sxs-lookup"><span data-stu-id="e8a69-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="e8a69-119">両方のアプリに対して次の LTI クライアント ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="e8a69-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="e8a69-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="e8a69-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="e8a69-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="e8a69-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="e8a69-122">管理パネルにアクセスし、[統合] **で** LTI ツール プロバイダーを探します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![これは、[LTI ツール プロバイダー] ダイアログボックスにプロバイダーの一覧が表示されます。](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="e8a69-124">**[LTI1.3/Advantage Tool の登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="e8a69-125">指定されたクライアント ID (Blackboard または Microsoft) の最初の ID を入力し、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![クライアント ID を入力するフィールドを持つ LTI 登録ツール](../media/lti-media/register-tool.png)

5. <span data-ttu-id="e8a69-127">事前に設定された設定を確認し、ツールの状態が承認済みとしてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a69-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="e8a69-128">下までスクロールし、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="e8a69-129">前の手順を繰り返して、環境内で 2 番目の LTI アプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="e8a69-130">REST アプリケーションとクロスオリジン リソース共有のセットアップ</span><span class="sxs-lookup"><span data-stu-id="e8a69-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="e8a69-131">Blackboard Learn Ultra 管理者は、REST アプリケーションとクロス オリジン リソース共有構成を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a69-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="e8a69-132">REST アプリケーションをセットアップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="e8a69-133">[管理ツールの学習] にアクセスし、[統合] セクションから **[REST API の** 統合 **] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="e8a69-134">[ **統合の作成] を** 選択し、Blackboard Learn Class Teams Integration LTI ツールに入力したのと同じアプリケーション/クライアント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="e8a69-135">[ユーザーの学習] を入力します (これは、管理者のユーザー名を学習する場合があります)、または [参照] を選択 **して** 検索します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="e8a69-136">[エンド **ユーザー アクセス] で** **[はい] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="e8a69-137">[ユーザー **として機能\*\*\*\*する承認] で [はい] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="e8a69-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="e8a69-138">[完了 **したら送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="e8a69-139">クロスオリジン リソース共有のセットアップ</span><span class="sxs-lookup"><span data-stu-id="e8a69-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="e8a69-140">[管理ツールの学習] にアクセスし、[統合] セクションから [クロスオリジン **リソース共有\*\*\*\*] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="e8a69-141">[構成 **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="e8a69-142">原点 `https://bb-ms-teams-ultra-ext.api.blackboard.com` に入力します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="e8a69-143">[許可するヘッダー **] に [承認\*\*\*\*] という単語を追加します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="e8a69-144">[使用可能 **] を [はい** ] **に設定します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="e8a69-145">[完了 **したら送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="e8a69-146">Blackboard Learn でクラス チームを有効にする</span><span class="sxs-lookup"><span data-stu-id="e8a69-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="e8a69-147">LTI ツールを有効にしたら、次に、Microsoft Class Teams の統合を独自の 365 テナントからMicrosoft Officeします。</span><span class="sxs-lookup"><span data-stu-id="e8a69-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="e8a69-148">これを行うには、Blackboard Learn Ultra 管理者として次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="e8a69-149">[**管理ツールと**  >  **ユーティリティの詳細] で、[Microsoft** **Teams Integration Admin] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![使用可能なツールの一覧を含むツールとユーティリティ ダイアログ](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="e8a69-151">[Microsoft Teams を有効にする **] のチェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="e8a69-152">[Microsoft O365 Admin] のセクションで参照されているテナント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="e8a69-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="e8a69-153">アプリが O365 管理者によって承認されるまで、設定を保存できない。「Microsoft [Azure テナントでアプリを承認する」を参照してください](#approve-the-app-in-the-microsoft-azure-tenant)。</span><span class="sxs-lookup"><span data-stu-id="e8a69-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="e8a69-154">グローバル O365 管理者が Microsoft テナントで Blackboard Teams アプリケーションを承認した場合は、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8a69-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
