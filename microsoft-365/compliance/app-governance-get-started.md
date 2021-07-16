---
title: アプリ ガバナンスの使用を開始する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アプリを管理するためのアプリ ガバナンス機能の使用を開始します。
ms.openlocfilehash: 80487298f2c3c3a93f0083337ddb223bd68e2611
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438038"
---
# <a name="get-started-with-app-governance-in-preview"></a><span data-ttu-id="ee7c4-103">アプリ ガバナンスの使用を開始する (プレビュー版)</span><span class="sxs-lookup"><span data-stu-id="ee7c4-103">Get started with app governance (in preview)</span></span>

<span data-ttu-id="ee7c4-104">Microsoft Cloud App Security のアプリ ガバナンス アドオンの使用を開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-104">To begin using the app governance add-on to Microsoft Cloud App Security:</span></span>

1. <span data-ttu-id="ee7c4-105">お客様のアカウントが適切なレベルのライセンスを所有していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-105">Verify your account has the appropriate level of licensing.</span></span> <span data-ttu-id="ee7c4-106">アプリ ガバナンスは、Microsoft Cloud App Security (MCAS) のアドオン機能であるため、アカウントに MCAS がスタンドアロン製品または以下の各種ライセンス パッケージの一部として存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-106">App governance is an add-on feature for Microsoft Cloud App Security (MCAS), and thus MCAS must be present in your account as either a standalone product or as part of the various license packages listed below.</span></span>
1. <span data-ttu-id="ee7c4-107">ポータルのアプリ ガバナンス ページにアクセスするには、以下のいずれかの管理者の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-107">You must have one of the administrator roles listed below to access the app governance pages in the portal.</span></span>

## <a name="licensing-for-app-governance"></a><span data-ttu-id="ee7c4-108">アプリ ガバナンスのライセンス</span><span class="sxs-lookup"><span data-stu-id="ee7c4-108">Licensing for app governance</span></span>

<span data-ttu-id="ee7c4-109">アプリ ガバナンスを開始する前に、「[Microsoft 365 管理センター（サブスクリプション](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)）」とアドオンを確認しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-109">Before you get started with app governance, you should confirm your [Microsoft 365 admin center - subscriptions](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="ee7c4-110">アプリ ガバナンスにアクセスして使用するには、組織は次のいずれかのサブスクリプションまたはアドオンを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-110">To access and use app governance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="ee7c4-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ee7c4-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="ee7c4-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ee7c4-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="ee7c4-113">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="ee7c4-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="ee7c4-114">Microsoft 365 E5 Developer (Windows および電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="ee7c4-114">Microsoft 365 E5 Developer (without Windows and Audio Conferencing)</span></span>
- <span data-ttu-id="ee7c4-115">Microsoft 365 E5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="ee7c4-115">Microsoft 365 E5 Information Protection and Governance</span></span>
- <span data-ttu-id="ee7c4-116">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="ee7c4-116">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="ee7c4-117">Microsoft 365 E5 (無料通話時間付き)</span><span class="sxs-lookup"><span data-stu-id="ee7c4-117">Microsoft 365 E5 with Calling Minutes</span></span>
- <span data-ttu-id="ee7c4-118">Microsoft 365 E5 (電話会議なし)</span><span class="sxs-lookup"><span data-stu-id="ee7c4-118">Microsoft 365 E5 without Audio Conferencing</span></span>
- <span data-ttu-id="ee7c4-119">Microsoft 365 A5 Compliance for faculty</span><span class="sxs-lookup"><span data-stu-id="ee7c4-119">Microsoft 365 A5 Compliance for faculty</span></span>
- <span data-ttu-id="ee7c4-120">Microsoft 365 A5 Compliance 学生用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-120">Microsoft 365 A5 Compliance for students</span></span>
- <span data-ttu-id="ee7c4-121">Microsoft 365 A5 教職員用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-121">Microsoft 365 A5 for faculty</span></span>
- <span data-ttu-id="ee7c4-122">Microsoft 365 A5 児童/学生用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-122">Microsoft 365 A5 for students</span></span>
- <span data-ttu-id="ee7c4-123">Microsoft 365 A5 Information Protection and Governance 教職員用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-123">Microsoft 365 A5 Information Protection and Governance for faculty</span></span>
- <span data-ttu-id="ee7c4-124">Microsoft 365 A5 Information Protection and Governance 児童/学生用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-124">Microsoft 365 A5 Information Protection and Governance for students</span></span>
- <span data-ttu-id="ee7c4-125">Microsoft 365 A5 Security for faculty</span><span class="sxs-lookup"><span data-stu-id="ee7c4-125">Microsoft 365 A5 Security for faculty</span></span>
- <span data-ttu-id="ee7c4-126">Microsoft 365 A5 Security 学生用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-126">Microsoft 365 A5 Security for students</span></span>
- <span data-ttu-id="ee7c4-127">Microsoft 365 A5 学生使用特典</span><span class="sxs-lookup"><span data-stu-id="ee7c4-127">Microsoft 365 A5 student use benefits</span></span>
- <span data-ttu-id="ee7c4-128">Microsoft 365 A5 (無料通話時間付き) 教職員用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-128">Microsoft 365 A5 with Calling Minutes for Faculty</span></span>
- <span data-ttu-id="ee7c4-129">Microsoft 365 A5 (無料通話時間付き) 学生用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-129">Microsoft 365 A5 with Calling Minutes for Students</span></span>
- <span data-ttu-id="ee7c4-130">Microsoft 365 A5 (電話会議なし) 教職員用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-130">Microsoft 365 A5 without Audio Conferencing for faculty</span></span>
- <span data-ttu-id="ee7c4-131">Microsoft 365 A5 (電話会議なし) 学生用</span><span class="sxs-lookup"><span data-stu-id="ee7c4-131">Microsoft 365 A5 without Audio Conferencing for students</span></span>
- <span data-ttu-id="ee7c4-132">Microsoft 365 A5 (電話会議なし) 学生使用特典</span><span class="sxs-lookup"><span data-stu-id="ee7c4-132">Microsoft 365 A5 without Audio Conferencing for students use benefit</span></span>

## <a name="administrator-roles"></a><span data-ttu-id="ee7c4-133">管理者の役割</span><span class="sxs-lookup"><span data-stu-id="ee7c4-133">Administrator roles</span></span>

<span data-ttu-id="ee7c4-134">アプリ ガバナンス ページを表示したり、ポリシーや設定を管理したりするには、以下のいずれかの管理者の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-134">One of the following administrator roles is required to see app governance pages or manage policies and settings:</span></span>

- <span data-ttu-id="ee7c4-135">アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-135">Application Administrator</span></span>
- <span data-ttu-id="ee7c4-136">クラウド アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-136">Cloud Application Administrator</span></span>
- <span data-ttu-id="ee7c4-137">社内管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-137">Company Administrator</span></span>
- <span data-ttu-id="ee7c4-138">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-138">Compliance Administrator</span></span>
- <span data-ttu-id="ee7c4-139">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-139">Compliance Data Administrator</span></span>
- <span data-ttu-id="ee7c4-140">コンプライアンス リーダー (読み取り専用)</span><span class="sxs-lookup"><span data-stu-id="ee7c4-140">Compliance Reader (read-only)</span></span>
- <span data-ttu-id="ee7c4-141">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-141">Global Reader</span></span>
- <span data-ttu-id="ee7c4-142">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-142">Security Administrator</span></span>
- <span data-ttu-id="ee7c4-143">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="ee7c4-143">Security Operator</span></span>
- <span data-ttu-id="ee7c4-144">セキュリティ リーダー (読み取り専用)</span><span class="sxs-lookup"><span data-stu-id="ee7c4-144">Security Reader (read-only)</span></span>

> [!NOTE]
> <span data-ttu-id="ee7c4-145">グローバル管理者のみが、アプリ ガバナンスの無料試用版を有効化できます。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-145">Only a Global Admin can activate the app governance free trial.</span></span>

<span data-ttu-id="ee7c4-146">こちらが各役割の機能です。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-146">Here are the capabilities for each role.</span></span>

| <span data-ttu-id="ee7c4-147">役割</span><span class="sxs-lookup"><span data-stu-id="ee7c4-147">Role</span></span> | <span data-ttu-id="ee7c4-148">ダッシュボードを読み取る</span><span class="sxs-lookup"><span data-stu-id="ee7c4-148">Read the dashboard</span></span> | <span data-ttu-id="ee7c4-149">すべてのアプリを読み取る</span><span class="sxs-lookup"><span data-stu-id="ee7c4-149">Read all apps</span></span> |<span data-ttu-id="ee7c4-150">ポリシーを読み取る</span><span class="sxs-lookup"><span data-stu-id="ee7c4-150">Read policies</span></span> | <span data-ttu-id="ee7c4-151">ポリシーを作成、更新、削除する</span><span class="sxs-lookup"><span data-stu-id="ee7c4-151">Create, update, or delete policies</span></span> | <span data-ttu-id="ee7c4-152">アラートを読み取る</span><span class="sxs-lookup"><span data-stu-id="ee7c4-152">Read alerts</span></span> | <span data-ttu-id="ee7c4-153">アラートを更新する</span><span class="sxs-lookup"><span data-stu-id="ee7c4-153">Update alerts</span></span> | <span data-ttu-id="ee7c4-154">設定を読み取る</span><span class="sxs-lookup"><span data-stu-id="ee7c4-154">Read settings</span></span> | <span data-ttu-id="ee7c4-155">設定を更新する</span><span class="sxs-lookup"><span data-stu-id="ee7c4-155">Update settings</span></span> | <span data-ttu-id="ee7c4-156">修復を読み取る</span><span class="sxs-lookup"><span data-stu-id="ee7c4-156">Read Remediation</span></span> | <span data-ttu-id="ee7c4-157">修復を更新する</span><span class="sxs-lookup"><span data-stu-id="ee7c4-157">Update Remediation</span></span> |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="ee7c4-158">アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-158">Application Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |
| <span data-ttu-id="ee7c4-169">クラウド アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-169">Cloud Application Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | | | | | | | | | |
| <span data-ttu-id="ee7c4-171">社内管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-171">Company Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |
| <span data-ttu-id="ee7c4-182">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-182">Compliance Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | |
| <span data-ttu-id="ee7c4-191">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-191">Compliance Data Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | |
| <span data-ttu-id="ee7c4-200">コンプライアンス リーダー</span><span class="sxs-lookup"><span data-stu-id="ee7c4-200">Compliance Reader</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | | |
| <span data-ttu-id="ee7c4-206">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-206">Global Reader</span></span>  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | | |
| <span data-ttu-id="ee7c4-212">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-212">Security Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | |
| <span data-ttu-id="ee7c4-221">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="ee7c4-221">Security Operator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | |
| <span data-ttu-id="ee7c4-231">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="ee7c4-231">Security Reader</span></span>  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) | |
|||||||||| | |

<span data-ttu-id="ee7c4-238">各役割に関する詳細については、「[管理者の役割のアクセス許可](/azure/active-directory/roles/permissions-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-238">For additional information about each role, see [Administrator role permissions](/azure/active-directory/roles/permissions-reference).</span></span>

## <a name="add-app-governance-to-your-microsoft-365-account"></a><span data-ttu-id="ee7c4-239">Microsoft 365 アカウントにアプリ ガバナンスを追加する</span><span class="sxs-lookup"><span data-stu-id="ee7c4-239">Add app governance to your Microsoft 365 account</span></span>

<span data-ttu-id="ee7c4-240">既存の Microsoft 365 のお客様の場合:</span><span class="sxs-lookup"><span data-stu-id="ee7c4-240">For existing Microsoft 365 customers:</span></span>

1. <span data-ttu-id="ee7c4-241">[Microsoft 365 管理センター](https://admin.microsoft.com)で、**[請求 - サービスの購入]** に移動し、**[アドオン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-241">In your [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Billing - Purchase services** and click **Add-ons**.</span></span>
1. <span data-ttu-id="ee7c4-242">アプリ ガバナンス カードで、**[詳細]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-242">In the app governance card, click **Details**.</span></span>
1. <span data-ttu-id="ee7c4-243">**[無料試用版を開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-243">Click **Start free trial**.</span></span>
1. <span data-ttu-id="ee7c4-244">必要な情報を入力し、選択済みのテナントにアプリ ガバナンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-244">Complete the requested information to add app governance to your selected tenant.</span></span> <span data-ttu-id="ee7c4-245">新規のお客様の場合、まずアカウントを作成するための情報を提供し、試用期間中のテナントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-245">I you are a new customer, you must first provide information to establish an account and create a tenant for your trial period.</span></span> <span data-ttu-id="ee7c4-246">これが完了すると、試用版にアプリ ガバナンスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-246">Once this is done you can add app governance to the trial.</span></span>

<span data-ttu-id="ee7c4-247">Microsoft 365 の新しいお客様の場合:</span><span class="sxs-lookup"><span data-stu-id="ee7c4-247">For new Microsoft 365 customers:</span></span>

1. <span data-ttu-id="ee7c4-248">このページの上部にある **[無料アカウント]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-248">At the top of this page, click the **Free Account** button.</span></span>
1. <span data-ttu-id="ee7c4-249">**[Microsoft 365 for business を試す]** で、**1 ヶ月の無料試用版を試す]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-249">Under **Try Microsoft 365 for business** click **Try 1 month free**.</span></span>

<span data-ttu-id="ee7c4-250">両者向け:</span><span class="sxs-lookup"><span data-stu-id="ee7c4-250">For both:</span></span>

1. <span data-ttu-id="ee7c4-251">サインアップ ポータルでは、試用版に使用するメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-251">In the sign-up portal, provide your email address to use for the trial.</span></span> <span data-ttu-id="ee7c4-252">既存のお客様の場合は、アカウントに関連付けられたメールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-252">If you are an existing customer, use the email associated with your account.</span></span> <span data-ttu-id="ee7c4-253">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-253">Click **Next**</span></span>
1. <span data-ttu-id="ee7c4-254">サインインしたら、**[今すぐ試す]** をクリックして、無料体験版を入手します。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-254">Once you have signed in, click **Try now** to get the free trial.</span></span>
1. <span data-ttu-id="ee7c4-255">**[続行]** をクリックしてページを閉じ、使用番の設定を開始します。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-255">Click **Continue** to close page and begin trial setup.</span></span> <span data-ttu-id="ee7c4-256">新しいアプリ ガバナンスのお客様の場合、アプリ ガバナンスのインスタンスが利用可能になるまで、最大で 2 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-256">For new app governance customers, it will take up to two hours for your app governance instance to become available.</span></span> <span data-ttu-id="ee7c4-257">既存のお客様については、既存のサービスに支障はありません。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-257">For existing customers, there will be no interruption of existing services.</span></span>
  > [!NOTE]
<span data-ttu-id="ee7c4-258">アカウントをお持ちでない場合は、試用版の使用を開始する前に、新しいアカウントを設定するためのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-258">If you do not already have an account you will be prompted to set up a new account before you can proceed with the trial.</span></span>

1. <span data-ttu-id="ee7c4-259">AAD テナントの利用可能なドメイン名を入力し、**[利用可能か確認]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-259">Enter in an available domain name for your AAD tenant and click **Check availability**.</span></span> <span data-ttu-id="ee7c4-260">管理者の役割が自動的に割り当てられます (アプリ ガバナンスのための既存の役割がない場合)。ドメイン名の変更やテナントの追加購入は、Microsoft 365 管理センター経由で後からでも可能です。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-260">You will automatically be assigned an Admin role (if you don’t have an existing role for app governance) and can always change the domain name and/or purchase more tenants later through the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="ee7c4-261">アカウントへのログインに使用するユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-261">Enter the username and password you would like to use to login to your account.</span></span> <span data-ttu-id="ee7c4-262">[**サインアップ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-262">Click **Sign up**.</span></span>
1. <span data-ttu-id="ee7c4-263">**[今すぐ開始]** をクリックしてアプリ ガバナンスポータルに移動するか、**[サブスクリプションの管理]** をクリックして Microsoft 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="ee7c4-263">Click **Get started** to go to the app governance portal or **Manage your subscription** to go to the Microsoft 365 admin center.</span></span>
