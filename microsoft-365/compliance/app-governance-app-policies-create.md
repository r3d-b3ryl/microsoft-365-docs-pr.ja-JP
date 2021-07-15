---
title: アプリ ポリシーを作成する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アプリ ポリシーを作成します。
ms.openlocfilehash: 17417d7fac80f2763edbbaa8dbb2c8be16e47371
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420423"
---
# <a name="create-app-policies"></a><span data-ttu-id="dff3a-103">アプリ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="dff3a-103">Create app policies</span></span>

><span data-ttu-id="dff3a-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="dff3a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dff3a-105">Microsoft アプリ ガバナンスのアプリ ポリシーには一連の機能が組み込まれており、以下の方法でアプリの異常な動作を検出してアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="dff3a-106">アプリ ガバナンスがアプリの動作を警告し、自動または手動で修復するための条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="dff3a-107">組織にアプリ コンプライアンス ポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="dff3a-108">アプリ ポリシーは、カスタマイズ可能な提供済みテンプレートから作成することができ、また独自のカスタム アプリ ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="dff3a-109">新しいアプリ ポリシーを作成するには **[Microsoft 365 コンプライアンス センター] > [アプリ保護とガバナンス] > [概要ページ] > [ポリシー]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App protection & governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="dff3a-110">アプリの使用向けに設計されたテンプレートを使用して新しいアプリ ポリシーを作成するには、**[アプリの使用ポリシーの作成]** の下の **[ポリシーの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="dff3a-111">アプリのアクセス許可向けに設計されたテンプレートを使用して新しいアプリ ポリシーを作成するには、**[アクセス許可ポリシーの作成]** の下の **[ポリシーの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="dff3a-112">アプリ認証またはカスタム ポリシー向けの新しいアプリ ポリシーを作成するには、**[新規作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="dff3a-113">アプリ ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="dff3a-113">App policy templates</span></span>

<span data-ttu-id="dff3a-114">アプリ ポリシー テンプレートに基づいて新しいアプリ ポリシーを作成するには、**[アプリ ポリシー テンプレートの選択] ページ** で、アプリ・テンプレートのカテゴリーを選択し、テンプレートの名前を選択して、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="dff3a-115">アプリ ガバナンスには、3 つのカテゴリーのアプリ ポリシー テンプレートがあります。</span><span class="sxs-lookup"><span data-stu-id="dff3a-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="dff3a-116">アプリ ユーザーとデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="dff3a-116">App users and data access</span></span>

<span data-ttu-id="dff3a-117">アプリ ガバナンスには、これらのテンプレートが含まれており、アプリの使用状況に関するアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="dff3a-118">テンプレート名</span><span class="sxs-lookup"><span data-stu-id="dff3a-118">Template name</span></span> | <span data-ttu-id="dff3a-119">説明</span><span class="sxs-lookup"><span data-stu-id="dff3a-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="dff3a-120">大量のデータ アクセスが可能な新しいアプリ</span><span class="sxs-lookup"><span data-stu-id="dff3a-120">New app with a high volume of data access</span></span> | <span data-ttu-id="dff3a-121">大量のデータ アクセスが可能な最近登録されたアプリを強調表示し、それらのデータ パターンが期待されたものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="dff3a-122">既定では、このポリシーは、過去 7 日間に登録され、その期間中に 1GB 以上のデータ アクセスがあったすべてのアプリにフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-122">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period.</span></span> <span data-ttu-id="dff3a-123">このポリシーは、詳細な条件やアクションをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-123">This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="dff3a-124">アプリの権限</span><span class="sxs-lookup"><span data-stu-id="dff3a-124">App Permissions</span></span>

<span data-ttu-id="dff3a-125">アプリ ガバナンスには、これらのテンプレートが含まれており、アプリのアクセス許可に関するアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="dff3a-126">テンプレート名</span><span class="sxs-lookup"><span data-stu-id="dff3a-126">Template name</span></span> | <span data-ttu-id="dff3a-127">説明</span><span class="sxs-lookup"><span data-stu-id="dff3a-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="dff3a-128">過度な特権を有するアプリ</span><span class="sxs-lookup"><span data-stu-id="dff3a-128">Overprivileged apps</span></span> | <span data-ttu-id="dff3a-129">付与されたアクセス許可が使用されているアクセス許可よりも多いアプリを強調表示し、アクセス許可を削減できる機会を特定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="dff3a-130">既定では、このポリシーは、90 日間使用されなかった場合、過度な特権を有するとしてマークされたすべてのアプリにフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="dff3a-131">この時間帯フィルターは、詳細な条件やアクションをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="dff3a-132">高い特権のアクセス許可を持つ新しいアプリ</span><span class="sxs-lookup"><span data-stu-id="dff3a-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="dff3a-133">このポリシーでは、高い特権のアクセス許可があるすべての新しいアプリを強調表示して、詳しい調査が必要な占有領域の大きいアプリを特定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="dff3a-134">既定では、このポリシーは、過去 7 日以内に登録された、対象範囲の広いアクセス許可があるすべてのアプリにフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="dff3a-135">アプリ証明書</span><span class="sxs-lookup"><span data-stu-id="dff3a-135">App certification</span></span>

<span data-ttu-id="dff3a-136">アプリ ガバナンスには、これらのテンプレートが含まれており、アプリ証明書に関するアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="dff3a-137">テンプレート名</span><span class="sxs-lookup"><span data-stu-id="dff3a-137">Template name</span></span> | <span data-ttu-id="dff3a-138">説明</span><span class="sxs-lookup"><span data-stu-id="dff3a-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="dff3a-139">認証されていない新しいアプリ</span><span class="sxs-lookup"><span data-stu-id="dff3a-139">New uncertified app</span></span> | <span data-ttu-id="dff3a-140">アプリ認証プロセスを経ていない新しいアプリを強調表示して、テナントで期待されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="dff3a-141">既定では、このポリシーは、過去 7 日間に登録され、認定されていないすべてのアプリにフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="dff3a-142">カスタム アプリ ポリシー</span><span class="sxs-lookup"><span data-stu-id="dff3a-142">Custom app policies</span></span>

<span data-ttu-id="dff3a-143">カスタム アプリ ポリシーは、組み込みのテンプレートの 1 つではまだ実行されていないことを行う必要がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="dff3a-144">新しいカスタム アプリ ポリシーを作成するには、まず **[ポリシー]** ページで **[新規作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="dff3a-145">**[アプリ ポリシー テンプレートの選択] ページ** で、**[カスタム]** カテゴリ、**[カスタム ポリシー]** テンプレートの順に選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="dff3a-146">**[名前と説明]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="dff3a-147">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="dff3a-147">Policy Name</span></span>

- <span data-ttu-id="dff3a-148">ポリシーの説明</span><span class="sxs-lookup"><span data-stu-id="dff3a-148">Policy Description</span></span>

- <span data-ttu-id="dff3a-149">ポリシーの重大度を選択して、このポリシーで生成されるアラートの重大度を設定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="dff3a-150">高</span><span class="sxs-lookup"><span data-stu-id="dff3a-150">High</span></span>
  - <span data-ttu-id="dff3a-151">中</span><span class="sxs-lookup"><span data-stu-id="dff3a-151">Medium</span></span>
  - <span data-ttu-id="dff3a-152">低</span><span class="sxs-lookup"><span data-stu-id="dff3a-152">Low</span></span>

<span data-ttu-id="dff3a-153">**[ポリシーの設定と条件を選択]** ページで、**このポリシーの対象となるアプリを選択します** に以下の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="dff3a-154">すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="dff3a-154">All Apps</span></span>
- <span data-ttu-id="dff3a-155">特定のアプリを選択する</span><span class="sxs-lookup"><span data-stu-id="dff3a-155">Choose specific apps</span></span>

  <span data-ttu-id="dff3a-156">ウィンドウでは、1 つ以上のアプリを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="dff3a-157">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-157">Select **Add**.</span></span>

<span data-ttu-id="dff3a-158">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-158">Select **Next**.</span></span>

<span data-ttu-id="dff3a-159">**[ポリシーの設定と条件を選択]** ページで、**[ポリシーに新しい条件を設定]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="dff3a-160">**[ルールの作成]** ウィンドウでは、新しいルールの条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="dff3a-161">**[条件の追加]** を選択し、条件の一覧から選択して、条件の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="dff3a-162">複数の条件を追加できます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-162">You can add multiple conditions.</span></span>

<span data-ttu-id="dff3a-163">カスタム アプリ ポリシーで利用可能な条件は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dff3a-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="dff3a-164">条件</span><span class="sxs-lookup"><span data-stu-id="dff3a-164">Condition</span></span> | <span data-ttu-id="dff3a-165">承諾済みの条件値</span><span class="sxs-lookup"><span data-stu-id="dff3a-165">Condition values accepted</span></span> | <span data-ttu-id="dff3a-166">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dff3a-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="dff3a-167">アプリの登録年齢</span><span class="sxs-lookup"><span data-stu-id="dff3a-167">App registration age</span></span> | <span data-ttu-id="dff3a-168">過去 X 日以内</span><span class="sxs-lookup"><span data-stu-id="dff3a-168">Within last X days</span></span> |  |
| <span data-ttu-id="dff3a-169">アプリ証明書</span><span class="sxs-lookup"><span data-stu-id="dff3a-169">App certification</span></span> | <span data-ttu-id="dff3a-170">基本的なコンプライアンス、MCAS コンプライアンス、または該当なし</span><span class="sxs-lookup"><span data-stu-id="dff3a-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="dff3a-171">Microsoft 365 認定</span><span class="sxs-lookup"><span data-stu-id="dff3a-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="dff3a-172">Publisher の検証</span><span class="sxs-lookup"><span data-stu-id="dff3a-172">Publisher verification</span></span> | <span data-ttu-id="dff3a-173">[はい] または [いいえ]</span><span class="sxs-lookup"><span data-stu-id="dff3a-173">Yes or No</span></span> | [<span data-ttu-id="dff3a-174">Publisher の検証</span><span class="sxs-lookup"><span data-stu-id="dff3a-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="dff3a-175">アプリケーションのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="dff3a-175">Application Permission</span></span> | <span data-ttu-id="dff3a-176">1 つ以上のエントリをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="dff3a-177">Microsoft Graph のアクセス許可のリファレンス</span><span class="sxs-lookup"><span data-stu-id="dff3a-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="dff3a-178">委任されたアクセス許可</span><span class="sxs-lookup"><span data-stu-id="dff3a-178">Delegated Permission</span></span> | <span data-ttu-id="dff3a-179">1 つ以上の API アクセス許可をリストから選択します</span><span class="sxs-lookup"><span data-stu-id="dff3a-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="dff3a-180">Microsoft Graph のアクセス許可のリファレンス</span><span class="sxs-lookup"><span data-stu-id="dff3a-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="dff3a-181">高特権</span><span class="sxs-lookup"><span data-stu-id="dff3a-181">High privilege</span></span> | <span data-ttu-id="dff3a-182">[はい] または [いいえ]</span><span class="sxs-lookup"><span data-stu-id="dff3a-182">Yes or No</span></span> | <span data-ttu-id="dff3a-183">これは、MCAS で使用されるものと同じ論理に基づいた内部名称です。</span><span class="sxs-lookup"><span data-stu-id="dff3a-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="dff3a-184">過度な特権を有するアプリ</span><span class="sxs-lookup"><span data-stu-id="dff3a-184">Overprivileged app</span></span> | <span data-ttu-id="dff3a-185">[はい] または [いいえ]</span><span class="sxs-lookup"><span data-stu-id="dff3a-185">Yes or No</span></span> | <span data-ttu-id="dff3a-186">使用されているアクセス許可よりも多くのアクセス許可が付与されているアプリ。</span><span class="sxs-lookup"><span data-stu-id="dff3a-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="dff3a-187">アプリのデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="dff3a-187">App data access</span></span> | <span data-ttu-id="dff3a-188">毎時 X GB 以上のデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="dff3a-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="dff3a-189">アプリのデータ アクセスの傾向</span><span class="sxs-lookup"><span data-stu-id="dff3a-189">App data access trend</span></span> | <span data-ttu-id="dff3a-190">過去 7 日間でデータ使用率が X% 増加</span><span class="sxs-lookup"><span data-stu-id="dff3a-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="dff3a-191">アプリ API アクセス</span><span class="sxs-lookup"><span data-stu-id="dff3a-191">App API Access</span></span> | <span data-ttu-id="dff3a-192">毎時 X 以上の API 呼び出し</span><span class="sxs-lookup"><span data-stu-id="dff3a-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="dff3a-193">アプリ API のアクセス傾向</span><span class="sxs-lookup"><span data-stu-id="dff3a-193">App API Access trend</span></span> | <span data-ttu-id="dff3a-194">過去 7 日間の API 呼び出しが X% 増加</span><span class="sxs-lookup"><span data-stu-id="dff3a-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="dff3a-195">同意済みユーザー</span><span class="sxs-lookup"><span data-stu-id="dff3a-195">Users consented</span></span> | <span data-ttu-id="dff3a-196">(大なり小なり) X 人の同意済みユーザー</span><span class="sxs-lookup"><span data-stu-id="dff3a-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="dff3a-197">同意済み優先ユーザー</span><span class="sxs-lookup"><span data-stu-id="dff3a-197">Priority user consented</span></span> | <span data-ttu-id="dff3a-198">[はい] または [いいえ]</span><span class="sxs-lookup"><span data-stu-id="dff3a-198">Yes or No</span></span> | <span data-ttu-id="dff3a-199">[優先アカウント](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)を持つユーザー。</span><span class="sxs-lookup"><span data-stu-id="dff3a-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="dff3a-200">同意済みアプリ</span><span class="sxs-lookup"><span data-stu-id="dff3a-200">App consented by</span></span> | <span data-ttu-id="dff3a-201">リストからユーザーを選択する</span><span class="sxs-lookup"><span data-stu-id="dff3a-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="dff3a-202">ユーザーの役割に同意する</span><span class="sxs-lookup"><span data-stu-id="dff3a-202">Consenting user’s role</span></span> | <span data-ttu-id="dff3a-203">1 つ以上選択: Teams 管理者、ディレクトリ リーダー、セキュリティ リーダー、コンプライアンス管理者、セキュリティ管理者、ヘルプデスク管理者、SharePoint 管理者、Exchange 管理者、グローバル リーダー、グローバル管理者、コンプライアンスデータ管理者、ユーザー管理者、サービス サポート管理者</span><span class="sxs-lookup"><span data-stu-id="dff3a-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="dff3a-204">複数の選択が可能です。</span><span class="sxs-lookup"><span data-stu-id="dff3a-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="dff3a-205">メンバーが割り当てられている Azure AD ロールを、このリストで利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff3a-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="dff3a-206">ワークロードにアクセス済み</span><span class="sxs-lookup"><span data-stu-id="dff3a-206">Workload accessed</span></span> | <span data-ttu-id="dff3a-207">OneDrive、SharePoint、Exchange</span><span class="sxs-lookup"><span data-stu-id="dff3a-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="dff3a-208">複数の選択が可能です。</span><span class="sxs-lookup"><span data-stu-id="dff3a-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="dff3a-209">エラー率</span><span class="sxs-lookup"><span data-stu-id="dff3a-209">Error rate</span></span> | <span data-ttu-id="dff3a-210">過去 7 日間のエラー率が X% を超えています (X は管理者が定義した値)。</span><span class="sxs-lookup"><span data-stu-id="dff3a-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="dff3a-211">このアプリ ポリシーを適用するには、指定された条件をすべて満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff3a-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="dff3a-212">条件の指定が完了したら、**[保存]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="dff3a-213">**[ポリシー アクションを定義する]** ページで、このポリシーに基づくアラートが生成された場合にアプリ ガバナンスでアプリを無効にしたい場合は、**[アプリを無効にする]** を選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="dff3a-214">**[ポリシー状態を定義する]** ページで、以下のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="dff3a-215">**監査モード**: ポリシーは評価されますが、構成済みアクションは発生しません。</span><span class="sxs-lookup"><span data-stu-id="dff3a-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="dff3a-216">監査モード ポリシーは、ポリシーのリストに **[監査]** の状態で表示されます。</span><span class="sxs-lookup"><span data-stu-id="dff3a-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="dff3a-217">**アクティブ**: ポリシーは評価され、構成済みアクションが発生します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="dff3a-218">**非アクティブ**: ポリシーは評価されず、構成済みアクションは発生しません。</span><span class="sxs-lookup"><span data-stu-id="dff3a-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="dff3a-219">新しいアプリ ポリシーのテストと監視</span><span class="sxs-lookup"><span data-stu-id="dff3a-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="dff3a-220">アプリ ポリシーが作成されたら、**[ポリシー]** ページで監視し、テスト中に想定される数のアクティブなアラートと合計アラートが登録されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff3a-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![強調表示されたポリシーを含む Microsoft 365 コンプライアンス センターの MAPG ポリシーの概要ページ](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="dff3a-222">アラートの数が想定外に少ない場合は、アプリ ポリシーの設定を編集して、状態を設定する前に正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dff3a-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="dff3a-223">ここでは、新しいポリシーを作成し、それをテストしてからアクティブにするまでのプロセスの例を示します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="dff3a-224">重大度、アプリ、条件、アクションを初期値に設定し、状態を **[監査モード]** に設定した新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="dff3a-225">生成されたアラートなど、期待される動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="dff3a-226">想定外の動作の場合は、必要に応じてポリシー アプリ、条件、アクションの設定を編集し、手順 2 に戻ります。</span><span class="sxs-lookup"><span data-stu-id="dff3a-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="dff3a-227">想定どおりの動作であれば、ポリシーを編集して、状態を **[アクティブ]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![アプリ ポリシー作成のワークフロー](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="dff3a-229">次の手順</span><span class="sxs-lookup"><span data-stu-id="dff3a-229">Next step</span></span>

[<span data-ttu-id="dff3a-230">アプリ ポリシーを管理します。</span><span class="sxs-lookup"><span data-stu-id="dff3a-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
