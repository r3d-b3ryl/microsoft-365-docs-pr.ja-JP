---
title: コネクタをセットアップして LinkedIn データをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がネイティブ コネクタを&して LinkedIn Company Page からデータをインポートする方法について説明Microsoft 365。
ms.openlocfilehash: 40e51424d086b0eee42d1f15ea577b7e8f1648c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906147"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="e2c83-103">コネクタをセットアップして LinkedIn データをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="e2c83-103">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="e2c83-104">LinkedIn Company ページからデータMicrosoft 365インポートおよびアーカイブするには、コンプライアンス センターのコネクタを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2c83-104">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="e2c83-105">コネクタを設定して構成した後、24 時間に 1 回、特定の LinkedIn Company ページのアカウントに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2c83-105">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="e2c83-106">コネクタは、[会社] ページに投稿されたメッセージを電子メール メッセージに変換し、それらのアイテムをメールボックスにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="e2c83-106">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="e2c83-107">LinkedIn Company ページ データをメールボックスに格納した後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を LinkedIn データに適用できます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-107">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="e2c83-108">たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、ストレージ メールボックスを保管担当者に関連付Advanced eDiscoveryできます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-108">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="e2c83-109">LinkedIn データをインポートおよびアーカイブするコネクタを作成すると、Microsoft 365規制ポリシーに準拠し、組織を支援できます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-109">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="e2c83-110">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="e2c83-110">Before you set up a connector</span></span>

- <span data-ttu-id="e2c83-111">LinkedIn Company Page コネクタを作成するユーザーには、ユーザーにメールボックスインポートエクスポートの役割が割りExchange Online。</span><span class="sxs-lookup"><span data-stu-id="e2c83-111">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e2c83-112">これは、コンプライアンス センターの [データコネクタ] ページにコネクタを追加Microsoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="e2c83-112">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e2c83-113">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="e2c83-113">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="e2c83-114">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e2c83-114">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e2c83-115">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-115">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e2c83-116">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e2c83-116">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="e2c83-117">アーカイブする LinkedIn Company Page の管理者である LinkedIn ユーザー アカウントのサインイン資格情報 (電子メール アドレスまたは電話番号とパスワード) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2c83-117">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="e2c83-118">コネクタをセットアップするときに、これらの資格情報を使用して LinkedIn にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2c83-118">You use these credentials to sign into LinkedIn when setting up the connector.</span></span>

- <span data-ttu-id="e2c83-119">LinkedIn コネクタは、1 日に合計 200,000 アイテムをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-119">The LinkedIn connector can import a total of 200,000 items in a single day.</span></span> <span data-ttu-id="e2c83-120">1 日に 200,000 件を超える LinkedIn アイテムがある場合、それらのアイテムはいずれもそのアイテムにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="e2c83-120">If there are more than 200,000 LinkedIn items in a day, none of those items will be imported to Microsoft 365.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="e2c83-121">LinkedIn コネクタの作成</span><span class="sxs-lookup"><span data-stu-id="e2c83-121">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="e2c83-122">[データ コネクタ <https://compliance.microsoft.com> ] **[LinkedIn Company]** ページ  >  **に移動し、[データ コネクタ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2c83-122">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="e2c83-123">**LinkedIn 会社ページの製品ページ** で、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2c83-123">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="e2c83-124">[サービス条件 **] ページで、[** 同意する] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e2c83-124">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="e2c83-125">**[LinkedIn でサインイン] ページで、[LinkedIn** で **サインイン] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2c83-125">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="e2c83-126">LinkedIn サインイン ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-126">The LinkedIn sign-in page is displayed.</span></span>

   ![LinkedIn サインイン ページ](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="e2c83-128">[LinkedIn サインイン] ページで、アーカイブする会社ページに関連付けられている LinkedIn アカウントの電子メール アドレス (または電話番号) とパスワードを入力し、[サインイン] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="e2c83-128">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="e2c83-129">サインインしたアカウントに関連付けられているすべての LinkedIn Company Pages の一覧がウィザード ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-129">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="e2c83-130">コネクタを構成できるのは、1 つの会社ページのみです。</span><span class="sxs-lookup"><span data-stu-id="e2c83-130">A connector can only be configured for one company page.</span></span> <span data-ttu-id="e2c83-131">組織に複数の LinkedIn Company Pages がある場合は、それぞれのコネクタを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2c83-131">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![LinkedIn Company Pages のリストを含むページが表示されます](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="e2c83-133">アイテムをアーカイブする会社ページを選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e2c83-133">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="e2c83-134">[保存 **場所の選択**] ページで、ボックス内をクリックし、LinkedIn アイテムをインポートする Microsoft 365 メールボックスの電子メール アドレスを選択し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="e2c83-134">On the **Choose storage location** page, click in the box, select the email address of a Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="e2c83-135">アイテムは、このメールボックスの受信トレイ フォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-135">Items are imported to the inbox folder in this mailbox.</span></span>

8. <span data-ttu-id="e2c83-136">[ **次へ]** をクリックしてコネクタの設定を確認し、[完了] を **クリックして** コネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="e2c83-136">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="e2c83-137">コネクタを作成した後、[データ コネクタ] ページに戻って、新しいコネクタのインポート プロセスの進行状況を確認できます (コネクタの一覧を更新するには、必要に応じて [更新] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="e2c83-137">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="e2c83-138">[状態] 列の **値は** 、[開始 **を待機中] です**。</span><span class="sxs-lookup"><span data-stu-id="e2c83-138">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="e2c83-139">最初のインポート プロセスを開始するには、最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="e2c83-139">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="e2c83-140">コネクタが初めて実行され、LinkedIn アイテムがインポートされると、コネクタは 24 時間に 1 回実行され、過去 24 時間に LinkedIn Company Page で作成された新しいアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-140">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="e2c83-141">詳細を表示するには、[データ コネクタ] ページの一覧でコネクタを **選択して、** フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="e2c83-141">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="e2c83-142">[ **状態]** で、表示される日付範囲は、コネクタの作成時に選択された年齢フィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="e2c83-142">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span>

## <a name="more-information"></a><span data-ttu-id="e2c83-143">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e2c83-143">More information</span></span>

<span data-ttu-id="e2c83-144">LinkedIn アイテムは、ストレージ メールボックスの受信トレイにある LinkedIn サブフォルダーにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="e2c83-144">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="e2c83-145">電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2c83-145">They appear as email messages.</span></span>