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
description: 管理者がネイティブ コネクタを使用&して LinkedIn Company Page から Microsoft 365 にデータをインポートする方法について説明します。
ms.openlocfilehash: 42183be3663fbf4b55eadde2173b492feeae5373
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619983"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="e6c14-103">コネクタをセットアップして LinkedIn データをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="e6c14-103">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="e6c14-104">Microsoft 365 コンプライアンス センターのコネクタを使用して、LinkedIn Company ページからデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="e6c14-104">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="e6c14-105">コネクタを設定して構成すると、24 時間ごとに 1 回、特定の LinkedIn Company ページのアカウントに接続されます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-105">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="e6c14-106">コネクタは、会社のページに投稿されたメッセージを電子メール メッセージに変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="e6c14-106">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="e6c14-107">LinkedIn Company ページのデータがメールボックスに保存された後、Microsoft 365 コンプライアンス機能 (訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 アイテム保持ポリシーなど) を LinkedIn データに適用できます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-107">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="e6c14-108">たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、Advanced eDiscovery ケースの保管担当者にストレージ メールボックスを関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-108">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="e6c14-109">Microsoft 365 で LinkedIn データをインポートおよびアーカイブするためのコネクタを作成すると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-109">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="assign-roles-and-verify-credentials"></a><span data-ttu-id="e6c14-110">役割を割り当て、資格情報を確認する</span><span class="sxs-lookup"><span data-stu-id="e6c14-110">Assign roles, and verify credentials</span></span>

- <span data-ttu-id="e6c14-111">LinkedIn Company Page コネクタを作成するユーザーには、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6c14-111">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e6c14-112">これは、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="e6c14-112">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e6c14-113">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="e6c14-113">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="e6c14-114">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-114">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e6c14-115">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-115">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e6c14-116">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6c14-116">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="e6c14-117">アーカイブする LinkedIn 会社ページの管理者である LinkedIn ユーザー アカウントのサインイン資格情報 (電子メール アドレスまたは電話番号とパスワード) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e6c14-117">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="e6c14-118">コネクタを設定するときに、これらの資格情報を使用して LinkedIn にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e6c14-118">You use these credentials to sign into LinkedIn when setting up the connector.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="e6c14-119">LinkedIn コネクタを作成する</span><span class="sxs-lookup"><span data-stu-id="e6c14-119">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="e6c14-120"><https://compliance.microsoft.com>[LinkedIn Company] ページに移動し、[**データ コネクタ**  >  **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e6c14-120">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="e6c14-121">**LinkedIn 会社ページの製品ページで、[** コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e6c14-121">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="e6c14-122">On the **Terms of service page,** select **Accept**.</span><span class="sxs-lookup"><span data-stu-id="e6c14-122">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="e6c14-123">**[LinkedIn でサインイン] ページで、[LinkedIn** でサインイン]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e6c14-123">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="e6c14-124">LinkedIn サインイン ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-124">The LinkedIn sign-in page is displayed.</span></span>

   ![LinkedIn サインイン ページ](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="e6c14-126">LinkedIn サインイン ページで、アーカイブする会社のページに関連付けられている LinkedIn アカウントの電子メール アドレス (または電話番号) とパスワードを入力し、[サインイン] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="e6c14-126">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="e6c14-127">ウィザード ページが表示され、サインインしたアカウントに関連付けられているすべての LinkedIn Company Pages の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-127">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="e6c14-128">コネクタは、1 つの会社ページにのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-128">A connector can only be configured for one company page.</span></span> <span data-ttu-id="e6c14-129">組織に複数の LinkedIn 会社ページがある場合は、それぞれにコネクタを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6c14-129">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![LinkedIn Company Pages のリストを含むページが表示される](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="e6c14-131">アイテムをアーカイブする会社のページを選択し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="e6c14-131">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="e6c14-132">[ストレージ **の場所** の選択] ページで、ボックスをクリックし、LinkedIn アイテムのインポート先の Microsoft 365 メールボックスの電子メール アドレスを選択し、[次へ] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="e6c14-132">On the **Choose storage location** page, click in the box, select the email address of a Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="e6c14-133">アイテムは、このメールボックスの受信トレイ フォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-133">Items are imported to the inbox folder in this mailbox.</span></span>

8. <span data-ttu-id="e6c14-134">[ **次へ]** をクリックしてコネクタの設定を確認し、[完了] **をクリックして** コネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="e6c14-134">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="e6c14-135">コネクタを作成した後、[データ コネクタ] ページに戻り、新しいコネクタのインポート プロセスの進行状況を確認できます (必要に応じて [最新の情報に更新] を選択してコネクタの一覧を更新します)。</span><span class="sxs-lookup"><span data-stu-id="e6c14-135">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="e6c14-136">The value in the **Status** column is **Waiting to start**.</span><span class="sxs-lookup"><span data-stu-id="e6c14-136">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="e6c14-137">最初のインポート プロセスが開始するには、最大 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="e6c14-137">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="e6c14-138">コネクタが初めて実行され、LinkedIn アイテムをインポートした後、コネクタは 24 時間ごとに 1 回実行され、過去 24 時間以内に LinkedIn Company Page で作成された新しいアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-138">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="e6c14-139">詳細を表示するには、[データ コネクタ] ページの一覧でコネクタを **選択して、** フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6c14-139">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="e6c14-140">[ **状態]** の下に表示される日付範囲は、コネクタの作成時に選択された年齢フィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="e6c14-140">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span>

## <a name="more-information"></a><span data-ttu-id="e6c14-141">詳細</span><span class="sxs-lookup"><span data-stu-id="e6c14-141">More information</span></span>

<span data-ttu-id="e6c14-142">LinkedIn アイテムは、Microsoft 365 のストレージ メールボックスの受信トレイにある LinkedIn サブフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-142">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="e6c14-143">電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6c14-143">They appear as email messages.</span></span>
