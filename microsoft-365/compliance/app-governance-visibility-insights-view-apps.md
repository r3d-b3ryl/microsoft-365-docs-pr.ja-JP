---
title: アプリを表示する
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
description: アプリを表示します。
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420261"
---
# <a name="view-your-apps"></a><span data-ttu-id="9cd8a-103">アプリを表示する</span><span class="sxs-lookup"><span data-stu-id="9cd8a-103">View your apps</span></span>

><span data-ttu-id="9cd8a-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="9cd8a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="9cd8a-105">Microsoft アプリ ガバナンスを使用すると、テナント内の Microsoft 365 アプリに関する詳細な分析情報をすばやく得ることができます。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="9cd8a-106">たとえば、次が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-106">For example, you can see:</span></span>

- <span data-ttu-id="9cd8a-107">Microsoft Graph API を使用するテナント内の OAuth 対応アプリのリストと、関連するアプリのメタデータおよび使用状況データ。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="9cd8a-108">リストからアプリを選択することにより詳細な分析情報を備えたアプリの詳細。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="9cd8a-109">テナント内のすべてのアプリのリストを取得する</span><span class="sxs-lookup"><span data-stu-id="9cd8a-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="9cd8a-110">テナント内のアプリの概要については、**[Microsoft 365 コンプライアンス センター] > [アプリの保護とガバナンス] > [アプリ]** にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![Microsoft 365 コンプライアンス センターの MAPG アプリの概要ページ](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="9cd8a-112">アプリ ガバナンス データを表示するには、サインイン アカウントに[これらのロール](app-governance-get-started.md#administrator-roles)のいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="9cd8a-113">アプリのリストと次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="9cd8a-114">アプリ名</span><span class="sxs-lookup"><span data-stu-id="9cd8a-114">App Name</span></span>
- <span data-ttu-id="9cd8a-115">発行元</span><span class="sxs-lookup"><span data-stu-id="9cd8a-115">Publisher</span></span>
- <span data-ttu-id="9cd8a-116">アプリ証明書</span><span class="sxs-lookup"><span data-stu-id="9cd8a-116">App certification</span></span>

  <span data-ttu-id="9cd8a-117">アプリが Microsoft のテクノロジと互換性があり、クラウド アプリのセキュリティのベスト プラクティスに準拠し、Microsoft によってサポートされているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="9cd8a-118">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="9cd8a-118">Last modified</span></span>

  <span data-ttu-id="9cd8a-119">アプリが最後に変更された日付よりも新しい日付の場合、アプリ ガバナンスがクライアントにインストールされた日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="9cd8a-120">インストール日</span><span class="sxs-lookup"><span data-stu-id="9cd8a-120">Date installed</span></span>
- <span data-ttu-id="9cd8a-121">特権レベル</span><span class="sxs-lookup"><span data-stu-id="9cd8a-121">Privilege level</span></span>
- <span data-ttu-id="9cd8a-122">ユーザーの数</span><span class="sxs-lookup"><span data-stu-id="9cd8a-122">Number of users</span></span>
- <span data-ttu-id="9cd8a-123">データ アクセス</span><span class="sxs-lookup"><span data-stu-id="9cd8a-123">Data access</span></span>

  <span data-ttu-id="9cd8a-124">最終日のテナントでのアプリのデータのアップロードとダウンロードの合計と、前日の変更。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="9cd8a-125">アプリ ガバナンスは、既定では **アプリ名** でアプリ リストを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="9cd8a-126">リストを別のアプリ属性で並べ替えるには、属性名を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="9cd8a-127">**[検索]** を選択して、名前でアプリを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="9cd8a-128">アプリの詳細情報を取得する</span><span class="sxs-lookup"><span data-stu-id="9cd8a-128">Getting detailed information on an app</span></span>

<span data-ttu-id="9cd8a-129">テナント内の特定のアプリの詳細については、\*\* [Microsoft 365 コンプライアンス センター] > [アプリ ガバナンス] > [アプリ ページ] > *アプリ名*\*\* にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![Microsoft 365 コンプライアンス センターの [アプリ ガバナンス アプリの詳細] ウィンドウ](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="9cd8a-131">アプリの詳細ウィンドウには、次のタブに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="9cd8a-132">タブ名</span><span class="sxs-lookup"><span data-stu-id="9cd8a-132">Tab name</span></span> | <span data-ttu-id="9cd8a-133">説明</span><span class="sxs-lookup"><span data-stu-id="9cd8a-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="9cd8a-134">詳細</span><span class="sxs-lookup"><span data-stu-id="9cd8a-134">Details</span></span> | <span data-ttu-id="9cd8a-135">最初に同意した日付やアプリ ID など、アプリに関する追加データを表示します。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="9cd8a-136">Azure AD に登録されているアプリのプロパティを表示するには、**[Azure AD のアプリを表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="9cd8a-137">使用法</span><span class="sxs-lookup"><span data-stu-id="9cd8a-137">Usage</span></span> | <span data-ttu-id="9cd8a-138">テナント内のアプリがアクセスするデータを確認し、データ使用量をプロットして、上位 \<x> ユーザーと[優先アカウント](/microsoft-365/admin/setup/priority-accounts)を持つユーザーによる使用状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="9cd8a-139">ユーザー</span><span class="sxs-lookup"><span data-stu-id="9cd8a-139">Users</span></span> | <span data-ttu-id="9cd8a-140">アプリを使用しているユーザーのリスト、ユーザーが優先アカウントであるかどうか、ダウンロードおよびアップロードされたデータの量を表示します。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="9cd8a-141">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9cd8a-141">Permissions</span></span> | <span data-ttu-id="9cd8a-142">アプリに付与されて使用されるアクセス許可の概要と、特定のアクセス許可のリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="9cd8a-143">詳細については、「[Microsoft Graph のアクセス許可リファレンス](/graph/permissions-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="9cd8a-144">有効なアプリの場合、選択したアプリの使用を無効にする **[アプリの無効化]** コントロールと、無効にしたアプリの使用を有効にする **[アプリの有効化]** コントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="9cd8a-145">これらのアクションには、次の[管理者の役割](app-governance-get-started.md#administrator-roles)が必要です。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="9cd8a-146">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="9cd8a-146">Compliance Administrator</span></span>
- <span data-ttu-id="9cd8a-147">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="9cd8a-147">Global Administrator</span></span>
- <span data-ttu-id="9cd8a-148">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="9cd8a-148">Security Administrator</span></span>
- <span data-ttu-id="9cd8a-149">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="9cd8a-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="9cd8a-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="9cd8a-150">Next step</span></span>

<span data-ttu-id="9cd8a-151">[アプリ全体のコンプライアンスへの取り組みを決定します](app-governance-visibility-insights-compliance-posture.md)。</span><span class="sxs-lookup"><span data-stu-id="9cd8a-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
