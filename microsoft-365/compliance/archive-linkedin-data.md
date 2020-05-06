---
title: コネクタをセットアップして LinkedIn データをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: LinkedIn データを Microsoft 365 にインポートするためのコネクタを設定して、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンスツールを使用できるようにします。
ms.openlocfilehash: 7d88d366ea19be7d158a04edc7d7fb11dca7bab9
ms.sourcegitcommit: e55e4747d3b838baacab8985aefc24aac245c431
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44043348"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a><span data-ttu-id="986b9-103">コネクタをセットアップして LinkedIn データをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="986b9-103">Set up a connector to archive LinkedIn data</span></span>

<span data-ttu-id="986b9-104">Microsoft 365 コンプライアンスセンターのコネクタを使用して、LinkedIn の会社のページからデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="986b9-104">Use a connector in the Microsoft 365 compliance center to import and archive data from LinkedIn Company pages.</span></span> <span data-ttu-id="986b9-105">コネクタを設定して構成すると、24時間ごとに、特定の LinkedIn 会社のページのアカウントに接続されます。</span><span class="sxs-lookup"><span data-stu-id="986b9-105">After you set up and configure a connector, it connects to the account for the specific LinkedIn Company page once every 24 hours.</span></span> <span data-ttu-id="986b9-106">コネクタは、会社のページに投稿されたメッセージを電子メールメッセージに変換し、そのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="986b9-106">The connector converts the messages posted to the Company page to an email message, and then imports those items to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="986b9-107">LinkedIn 会社のページデータをメールボックスに格納した後、Microsoft 365 のコンプライアンス機能 (訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、Microsoft 365 アイテム保持ポリシーなど) を LinkedIn データに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="986b9-107">After the LinkedIn Company page data is stored in a mailbox, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to LinkedIn data.</span></span> <span data-ttu-id="986b9-108">たとえば、コンテンツ検索を使用してこれらのアイテムを検索したり、高度な電子情報開示ケースの保管担当者にストレージメールボックスを関連付けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="986b9-108">For example, you can search for these items using Content Search or associate the storage mailbox with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="986b9-109">Microsoft 365 で LinkedIn データをインポートおよびアーカイブするためのコネクタを作成することで、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="986b9-109">Creating a connector to import and archive LinkedIn data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="before-you--begin"></a><span data-ttu-id="986b9-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="986b9-110">Before you  begin</span></span>

- <span data-ttu-id="986b9-111">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="986b9-111">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="986b9-112">この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Microsoft 365 グローバル管理者の資格情報でサインインし、要求を承諾します。</span><span class="sxs-lookup"><span data-stu-id="986b9-112">To consent to this request, go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), sign in with the credentials of a Microsoft 365 global admin, and then accept the request.</span></span>

- <span data-ttu-id="986b9-113">LinkedIn Company Page コネクタを作成したユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="986b9-113">The user who creates a LinkedIn Company Page connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="986b9-114">これは、Microsoft 365 コンプライアンスセンターの [**データコネクタ**] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="986b9-114">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="986b9-115">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="986b9-115">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="986b9-116">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="986b9-116">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="986b9-117">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="986b9-117">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="986b9-118">詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="986b9-118">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

- <span data-ttu-id="986b9-119">アーカイブする LinkedIn の会社のページの管理者である LinkedIn ユーザーアカウントのサインイン資格情報 (電子メールアドレスまたは電話番号とパスワード) を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="986b9-119">You must have the sign-in credentials (email address or phone number and password) of a LinkedIn user account that is an admin for the LinkedIn Company Page that you want to archive.</span></span> <span data-ttu-id="986b9-120">これらの資格情報を使用して、コネクタを設定するときに LinkedIn にサインインします。</span><span class="sxs-lookup"><span data-stu-id="986b9-120">You use these credentials to sign into LinkedIn when setting up the connector.</span></span>

## <a name="create-a-linkedin-connector"></a><span data-ttu-id="986b9-121">LinkedIn コネクタを作成する</span><span class="sxs-lookup"><span data-stu-id="986b9-121">Create a LinkedIn connector</span></span>

1. <span data-ttu-id="986b9-122">に移動<https://compliance.microsoft.com>して、[**データコネクタ** > **LinkedIn の会社のページ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="986b9-122">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **LinkedIn Company pages**.</span></span>

2. <span data-ttu-id="986b9-123">[ **LinkedIn company pages** product] ページで、[**コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="986b9-123">On the **LinkedIn company pages** product page, click **Add connector**.</span></span>

3. <span data-ttu-id="986b9-124">[**サービス利用規約**] ページで、[**同意**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="986b9-124">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="986b9-125">[ **Linkedin を使用**してサインインする] ページで、[ **linkedin でサインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="986b9-125">On the **Sign in with LinkedIn** page, click **Sign in with LinkedIn**.</span></span>

   <span data-ttu-id="986b9-126">LinkedIn サインインページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="986b9-126">The LinkedIn sign-in page is displayed.</span></span>

   ![LinkedIn サインインページ](../media/LinkedInSigninPage.png)

5. <span data-ttu-id="986b9-128">LinkedIn の [サインイン] ページで、アーカイブする会社のページに関連付けられている LinkedIn アカウントの電子メールアドレス (または電話番号) とパスワードを入力し、[**サインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="986b9-128">On the LinkedIn sign in page, enter the email address (or phone number) and password for the LinkedIn account associated with the company page that you want to archive, and then click **Sign in**.</span></span>

   <span data-ttu-id="986b9-129">ウィザードページが、サインインしたアカウントに関連付けられているすべての LinkedIn 会社のページの一覧と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="986b9-129">A wizard page is displayed with a list of all LinkedIn Company Pages associated with the account that you signed in to.</span></span> <span data-ttu-id="986b9-130">コネクタは、1つの会社のページに対してのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="986b9-130">A connector can only be configured for one company page.</span></span> <span data-ttu-id="986b9-131">組織に複数の LinkedIn Company ページがある場合は、それぞれに対してコネクタを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="986b9-131">If your organization has multiple LinkedIn Company Pages, you have to create a connector for each one.</span></span>

   ![LinkedIn 会社のページの一覧を含むページが表示されます。](../media/LinkedInSelectCompanyPage.png)

6. <span data-ttu-id="986b9-133">アイテムをアーカイブする会社のページを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="986b9-133">Select the company page that you want to archive items from, and then click **Next**.</span></span>

7. <span data-ttu-id="986b9-134">[**記憶域の場所の選択**] ページで、ボックス内のをクリックし、LinkedIn アイテムをインポートする Microsoft 365 メールボックスの電子メールアドレスを選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="986b9-134">On the **Choose storage location** page, click in the box, select the email address of a Microsoft 365 mailbox that the LinkedIn items will be imported to, and then click **Next**.</span></span> <span data-ttu-id="986b9-135">アイテムは、このメールボックスの受信トレイフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="986b9-135">Items are imported to the inbox folder in this mailbox.</span></span>

8. <span data-ttu-id="986b9-136">[**管理者に同意**する] で、[**同意を提供**する] をクリックし、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="986b9-136">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="986b9-137">組織内のデータにアクセスするために Office 365 Import service への同意を提供するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="986b9-137">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

9. <span data-ttu-id="986b9-138">[**次**へ] をクリックしてコネクタの設定を確認し、[**完了**] をクリックしてコネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="986b9-138">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

<span data-ttu-id="986b9-139">コネクタを作成したら、[**データコネクタ**] ページに戻り、新しいコネクタのインポート処理の進行状況を確認できます (コネクタの一覧を更新する必要がある場合は、[**更新**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="986b9-139">After you create the connector, you can go back to the **Data connectors** page to see the progress of the import process for the new connector (select **Refresh** if necessary to update the list of connectors).</span></span> <span data-ttu-id="986b9-140">[**状態**] 列の値は、**開始を待機**しています。</span><span class="sxs-lookup"><span data-stu-id="986b9-140">The value in the **Status** column is **Waiting to start**.</span></span> <span data-ttu-id="986b9-141">最初のインポート処理が開始されるまでに最大で24時間かかります。</span><span class="sxs-lookup"><span data-stu-id="986b9-141">It takes up to 24 hours for the initial import process to be started.</span></span> <span data-ttu-id="986b9-142">コネクタが初めて実行され、LinkedIn アイテムがインポートされると、コネクタは24時間ごとに1回実行され、過去24時間に LinkedIn Company ページに作成された新しいアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="986b9-142">After the first time the connector runs and imports the LinkedIn items, the connector will run once every 24 hours and import any new items that are created on the LinkedIn Company Page in the previous 24 hours.</span></span>

<span data-ttu-id="986b9-143">詳細を表示するには、[**データコネクタ**] ページの一覧でコネクタを選択して、フライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="986b9-143">To view more details, select the connector in the list on the **Data connectors** page to display the flyout page.</span></span> <span data-ttu-id="986b9-144">[**状態**] の下に表示される日付の範囲は、コネクタの作成時に選択された年齢フィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="986b9-144">Under **Status**, the date range that's displayed indicates the age filter that was selected when the connector was created.</span></span>

## <a name="more-information"></a><span data-ttu-id="986b9-145">詳細情報</span><span class="sxs-lookup"><span data-stu-id="986b9-145">More information</span></span>

<span data-ttu-id="986b9-146">LinkedIn アイテムは、Microsoft 365 のストレージメールボックスの受信トレイの LinkedIn サブフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="986b9-146">LinkedIn items are imported to the LinkedIn subfolder in the inbox of the storage mailbox in Microsoft 365.</span></span> <span data-ttu-id="986b9-147">電子メールメッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="986b9-147">They appear as email messages.</span></span>
