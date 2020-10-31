---
title: Microsoft 365 でピボットデータをアーカイブするためのコネクタの設定
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
ms.collection: M365-security-compliance
description: 管理者は、Microsoft 365 で Globanet からピボットデータをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: f9c0925856ffb9c43fa985c9da4bcd17485a5e39
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816580"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a><span data-ttu-id="cc745-104">ピボットデータをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="cc745-104">Set up a connector to archive Pivot data</span></span>

<span data-ttu-id="cc745-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、ピボットプラットフォームから Microsoft 365 組織のユーザーメールボックスにデータをインポートし、アーカイブします。</span><span class="sxs-lookup"><span data-stu-id="cc745-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Pivot platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="cc745-106">Globanet では、サードパーティのデータソースからアイテムを取得するように構成された [ピボット](https://globanet.com/pivot/) コネクタ (定期的に) が提供され、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="cc745-106">Globanet provides you with a [Pivot](https://globanet.com/pivot/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="cc745-107">Pivot は、財務市場の参加者とのコラボレーションを可能にするインスタントメッセージングプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="cc745-107">Pivot is an instant messaging platform that allows collaboration with financial market participants.</span></span> <span data-ttu-id="cc745-108">このコネクタは、チャットメッセージなどのアイテムを、ユーザーのピボットアカウントから電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="cc745-108">The connector converts items such as chat messages, from a users' Pivot accounts to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="cc745-109">ユーザーのメールボックスにピボットデータが格納されると、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="cc745-109">After Pivot data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="cc745-110">Microsoft 365 でピボットコネクタを使用してデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="cc745-110">Using a Pivot connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-pivot-data"></a><span data-ttu-id="cc745-111">ピボットデータのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="cc745-111">Overview of archiving Pivot data</span></span>

<span data-ttu-id="cc745-112">次の概要では、コネクタを使用して Microsoft 365 のピボットデータをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cc745-112">The following overview explains the process of using a connector to archive the Pivot data in Microsoft 365.</span></span>

![ピボットデータのアーカイブワークフロー](../media/PivotConnectorWorkflow.png)

1. <span data-ttu-id="cc745-114">組織はピボットを使用して、ピボットソースサイトを設定して構成します。</span><span class="sxs-lookup"><span data-stu-id="cc745-114">Your organization works with Pivot to set up and configure a Pivot source site.</span></span>

2. <span data-ttu-id="cc745-115">24時間ごとに、ピボットアイテムは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="cc745-115">Once every 24 hours, Pivot items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="cc745-116">また、コネクタは、ピボットアイテムを電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="cc745-116">The connector also converts the Pivot items to an email message format.</span></span>

3. <span data-ttu-id="cc745-117">Microsoft 365 コンプライアンスセンターで作成した Pivot connector は、Globanet Merge1 サイトに毎日接続し、そのピボットアイテムを Microsoft クラウド内のセキュリティで保護された Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="cc745-117">The Pivot connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the Pivot items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="cc745-118">コネクタは、 [手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、ピボットアイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="cc745-118">The connector imports the Pivot items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="cc745-119">ユーザーのメールボックスに、 **Pivot** という名前の受信トレイフォルダー内のサブフォルダーが作成され、そのフォルダーにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="cc745-119">A subfolder in the Inbox folder named **Pivot** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="cc745-120">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="cc745-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="cc745-121">すべてのピボットアイテムには、アイテムのすべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc745-121">Every Pivot item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cc745-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="cc745-122">Before you begin</span></span>

- <span data-ttu-id="cc745-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc745-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="cc745-124">このアカウントを作成するには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact/)に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="cc745-124">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="cc745-125">このアカウントは、手順1でコネクタを作成するときにサインインします。</span><span class="sxs-lookup"><span data-stu-id="cc745-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="cc745-126">手順1でピボットコネクタを作成する (および手順3で完了する) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc745-126">The user who creates the Pivot connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="cc745-127">この役割は、Microsoft 365 コンプライアンスセンターの [データコネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="cc745-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="cc745-128">既定では、この役割は Exchange Online の役割グループに割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="cc745-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="cc745-129">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cc745-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="cc745-130">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc745-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="cc745-131">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc745-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-pivot-connector"></a><span data-ttu-id="cc745-132">手順 1: ピボットコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="cc745-132">Step 1: Set up the Pivot connector</span></span>

<span data-ttu-id="cc745-133">最初の手順として、Microsoft コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、ピボットデータ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc745-133">The first step is to access to the **Data Connectors** page in the Microsoft compliance center and create a connector for Pivot data.</span></span>

1. <span data-ttu-id="cc745-134">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **データコネクタ** ] ピボットをクリックし  >  **Pivot** ます。</span><span class="sxs-lookup"><span data-stu-id="cc745-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Pivot** .</span></span>

2. <span data-ttu-id="cc745-135">[ **ピボット** 製品の説明] ページで、[ **コネクタの追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc745-135">On the **Pivot** product description page, click **Add connector** .</span></span>

3. <span data-ttu-id="cc745-136">[ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc745-136">On the **Terms of service** page, click **Accept** .</span></span>

4. <span data-ttu-id="cc745-137">コネクタを識別する一意の名前を入力し、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc745-137">Enter a unique name that identifies the connector and then click **Next** .</span></span>

5. <span data-ttu-id="cc745-138">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="cc745-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-pivot-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="cc745-139">手順 2: Globanet Merge1 サイトでピボットコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="cc745-139">Step 2: Configure the Pivot connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="cc745-140">2番目の手順では、Merge1 サイト上にピボットコネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="cc745-140">The second step is to configure the Pivot connector on the Merge1 site.</span></span> <span data-ttu-id="cc745-141">Globanet Merge1 サイトでピボットコネクタを構成する方法については、「 [Merge1 サードパーティ製コネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc745-141">For information about how to configure the Pivot connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="cc745-142">[ **保存 & 完了** ] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc745-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="cc745-143">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="cc745-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="cc745-144">ユーザーをマップし、Microsoft 356 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc745-144">To map users and complete the connector setup in the Microsoft 356 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="cc745-145">[ **ピボットユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cc745-145">On the **Map Pivot users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="cc745-146">Pivot アイテムには、 *電子メール* というプロパティが含まれています。このプロパティには、組織内のユーザーの電子メールアドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc745-146">The Pivot items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="cc745-147">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="cc745-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="cc745-148">[ **管理者の同意** ] ページで、[ **同意を提供** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc745-148">On the **Admin Consent** page, click **Provide Consent** .</span></span> <span data-ttu-id="cc745-149">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="cc745-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="cc745-150">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc745-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="cc745-151">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc745-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="cc745-152">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc745-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="cc745-153">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="cc745-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="cc745-154">[ **次へ** ] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="cc745-154">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-pivot-connector"></a><span data-ttu-id="cc745-155">手順 4: ピボットコネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="cc745-155">Step 4: Monitor the Pivot connector</span></span>

<span data-ttu-id="cc745-156">ピボットコネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cc745-156">After you create the Pivot connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="cc745-157">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[ **データコネクタ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cc745-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="cc745-158">[ **コネクタ** ] タブをクリックし、[ **ピボット** コネクタ] を選択して、フライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="cc745-158">Click the **Connectors** tab and then select the **Pivot** connector to display the flyout page.</span></span> <span data-ttu-id="cc745-159">このページには、コネクタに関するプロパティと情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc745-159">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="cc745-160">[ **コネクタの状態 (ソース付き** )] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="cc745-160">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="cc745-161">このログには、Microsoft クラウドにインポートされたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc745-161">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="cc745-162">既知の問題</span><span class="sxs-lookup"><span data-stu-id="cc745-162">Known issues</span></span>

- <span data-ttu-id="cc745-163">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cc745-163">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="cc745-164">より大きいアイテムのサポートは、後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="cc745-164">Support for larger items will be available at a later date.</span></span>
