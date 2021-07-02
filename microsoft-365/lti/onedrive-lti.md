---
title: '[ツールMicrosoft OneDrive ラーニング相互運用性を使用する'
ms.author: heidip
author: MicrosoftHeidi
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
description: 新しいツール相互運用性アプリを使用して、課題の作成と採点、コース コンテンツの構築とキュレーション、ファイルMicrosoft OneDrive ラーニング共同作業を行います。
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53257021"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="002e3-103">LTI Microsoft OneDriveキャンバスとの統合</span><span class="sxs-lookup"><span data-stu-id="002e3-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="002e3-104">LTI Microsoft OneDrive Canvas との統合は、2 つのステッププロセスです。</span><span class="sxs-lookup"><span data-stu-id="002e3-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="002e3-105">最初の手順では Canvas Microsoft OneDriveを有効にし、2 番目の手順では、Microsoft OneDrive内で LTI を使用できます。</span><span class="sxs-lookup"><span data-stu-id="002e3-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="002e3-106">推奨されるブラウザー設定</span><span class="sxs-lookup"><span data-stu-id="002e3-106">Recommended browser settings</span></span>

- <span data-ttu-id="002e3-107">Cookie は、ユーザーに対してMicrosoft OneDrive。</span><span class="sxs-lookup"><span data-stu-id="002e3-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="002e3-108">ポップアップをブロックしない必要Microsoft OneDrive。</span><span class="sxs-lookup"><span data-stu-id="002e3-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="002e3-109">Cookie は Chrome ブラウザーのシークレット モードでは既定では有効になっていません。有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="002e3-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="002e3-110">Microsoft OneDriveLTI は、ブラウザーのプライベート モードMicrosoft Edgeします。</span><span class="sxs-lookup"><span data-stu-id="002e3-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="002e3-111">Cookie をブロックしていない (既定で有効になっている) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="002e3-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="002e3-112">Canvas Microsoft OneDrive LTI を有効にする</span><span class="sxs-lookup"><span data-stu-id="002e3-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="002e3-113">この統合を実行するユーザーは、Canvas の管理者であり、テナントの管理者Microsoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="002e3-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="002e3-114"><a href="https://onedrivelti.microsoft.com/admin" target="_blank">LTI 登録ポータルMicrosoft OneDriveサインインする</a></span><span class="sxs-lookup"><span data-stu-id="002e3-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="002e3-115">[管理者の **同意] ボタンを** 選択し、アクセス許可を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="002e3-115">Select the **Admin Consent** button and accept the permissions.</span></span>
1. <span data-ttu-id="002e3-116">[新しい **LTI テナントの作成] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="002e3-116">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="002e3-117">[LTI 登録] ページでドロップダウン **で [Canvas]** を選択し、Canvas インスタンスのベース URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="002e3-117">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="002e3-118">Canvas インスタンスが ( ) の場合 https://contoso.test.instructure.com https://contoso.test.instructure.com) は、完全な URL を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="002e3-118">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI テナント管理ページ(LTI コンシューマー プラットフォームを選択するためのドロップダウン フィールドと URL テキスト フィールドを含む)。":::

4. <span data-ttu-id="002e3-120">[コピー] ボタンを選択して **JSON** をコピーします (右側のアイコンで、2 つのページが上に表示されます)。</span><span class="sxs-lookup"><span data-stu-id="002e3-120">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="002e3-121">これは、Canvas でキーを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="002e3-121">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="表示された JSON テキストをコピーし、Canvas でのキー生成に使用できるコピー ボタンを示す画像。":::

5. <span data-ttu-id="002e3-123">Canvas インスタンスに管理者としてサインインし、ページの左側にあるメニューから [開発者キー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="002e3-123">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="002e3-124">ドロップダウンから、ページ右上のドロップダウンから **[LTI キー** ] を選択して開発者キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="002e3-124">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="[開発者キー] が選択されている左側のナビゲーション バーと、ページの右側のドロップダウンから選択された LTI キー エントリを示すスクリーンショット。":::

6. <span data-ttu-id="002e3-126">[構成] ページの[メソッド] ドロップダウンで、[メソッドとして **JSON** を貼り付ける] を選択し、表示されるテキスト フィールドの手順 5 でコピーした JSON テキストを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="002e3-126">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="002e3-127">キーを保存すると、Off 状態の Canvas **で使用** できます。</span><span class="sxs-lookup"><span data-stu-id="002e3-127">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="002e3-128">キーを **オンに** し、[詳細] 列で指定したキーをコピーして、次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="002e3-128">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="キーがオフの状態で設定されたキャンバス ページ。このキーをオンにし、このページの詳細列からキーをコピーする必要があります。":::

8. <span data-ttu-id="002e3-130">LTI 登録ポータルMicrosoft OneDriveに戻り、[Canvas Client ID] フィールドにキー **を貼り付** けます。</span><span class="sxs-lookup"><span data-stu-id="002e3-130">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="002e3-131">準備 **ができたら、[** 次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="002e3-131">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="キーをコピーする必要がある JSON テキストとテキスト ボックスを示す LTI テナント登録ページ。":::

9. <span data-ttu-id="002e3-133">変更を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="002e3-133">Review and save your changes.</span></span> <span data-ttu-id="002e3-134">正常に登録されると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="002e3-134">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="002e3-135">登録の詳細は、ホーム ページの **[LTI** テナントの表示] ボタンを選択して確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="002e3-135">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="002e3-136">キャンバス コースMicrosoft OneDrive LTI を有効にする</span><span class="sxs-lookup"><span data-stu-id="002e3-136">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="002e3-137">キャンバス管理者は、すべてのコースMicrosoft OneDrive LTI を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="002e3-137">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="002e3-138">LTI Microsoft OneDrive (すべてのコースではなく) で必要な場合、コースの教師は、コース設定内で同じ手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="002e3-138">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="002e3-139">管理者としてサインインし、[管理者] セクション **に設定** します。</span><span class="sxs-lookup"><span data-stu-id="002e3-139">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="002e3-140">[アプリ] **セクションに移動** し、[アプリ構成の表示 **] ボタンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="002e3-140">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="002e3-141">[アプリの **追加] ボタンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="002e3-141">Select the **Add App** button.</span></span>
4. <span data-ttu-id="002e3-142">[構成の **種類] ドロップダウン** で、[クライアント ID 別 **] オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="002e3-142">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="002e3-143">以前に生成された開発者キーの値を [クライアント **ID]** フィールドに貼り付け、[送信] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="002e3-143">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="[構成の種類] ドロップダウン メニューの [クライアント ID 別] オプションを表示する [アプリの追加] ページ。":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="002e3-145">キャンバス 設定 LTI Microsoft OneDriveの共同作業</span><span class="sxs-lookup"><span data-stu-id="002e3-145">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="002e3-146">教育者と学生が共同作業を行う場合は、共同作業の設定を有効にしない必要があります。</span><span class="sxs-lookup"><span data-stu-id="002e3-146">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="002e3-147">設定が有効になっていないか確認するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="002e3-147">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="002e3-148">管理者としてサインインし、[管理者] セクション **に設定** します。</span><span class="sxs-lookup"><span data-stu-id="002e3-148">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="002e3-149">[機能 **オプション] セクションに** 移動し、[コース] セクション **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="002e3-149">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="002e3-150">[外部 **コラボレーション ツール] 機能を** 有効に設定します。</span><span class="sxs-lookup"><span data-stu-id="002e3-150">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="002e3-151">コラボレーションは、個々の学生と学生のグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="002e3-151">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="002e3-152">個々の学生への割り当ては、既定で動作します。</span><span class="sxs-lookup"><span data-stu-id="002e3-152">Assigning to individual students works by default.</span></span> <span data-ttu-id="002e3-153">学生のグループに共同作業を割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="002e3-153">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="002e3-154">管理者としてログインし、[開発者キー] **セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="002e3-154">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="002e3-155">値 170000000000000710 のキーを検索し、[オン] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="002e3-155">Find the key with value 170000000000710 and set it to **On**.</span></span>
