---
title: Microsoft 365 で Jive データをアーカイブするためのコネクタをセットアップする
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
description: 管理者は、Microsoft 365 の Globanet から Jive データをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 9017e6a7e26c823243abe188328cf62a22ea91c6
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816560"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a><span data-ttu-id="62564-104">Jive データをアーカイブするためのコネクタの設定</span><span class="sxs-lookup"><span data-stu-id="62564-104">Set up a connector to archive Jive data</span></span>

<span data-ttu-id="62564-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、コラボレーションプラットフォームから Microsoft 365 組織のユーザーメールボックスへのデータのインポートとアーカイブを行います。</span><span class="sxs-lookup"><span data-stu-id="62564-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="62564-106">Globanet には、サードパーティのデータソースからアイテムを取得するように構成された [Jive](https://globanet.com/jive/) コネクタがあり (定期的に)、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="62564-106">Globanet provides a [Jive](https://globanet.com/jive/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="62564-107">コネクタは、電子メールメッセージ、チャット、添付ファイルなどのコンテンツをユーザーの Jive アカウントから電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="62564-107">The connector converts content such as email messages, chats, and attachments from a user's Jive account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="62564-108">Jive データがユーザーのメールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="62564-108">After Jive data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="62564-109">Jive コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることで、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="62564-109">Using a Jive connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-jive-data"></a><span data-ttu-id="62564-110">Jive データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="62564-110">Overview of archiving Jive data</span></span>

<span data-ttu-id="62564-111">次の概要では、コネクタを使用して Microsoft 365 の Jive データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62564-111">The following overview explains the process of using a connector to archive the Jive data in Microsoft 365.</span></span>

![Jive データのアーカイブワークフロー](../media/JiveConnectorWorkflow.png)

1. <span data-ttu-id="62564-113">組織は Jive を使用して、Jive サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="62564-113">Your organization works with Jive to set up and configure a Jive site.</span></span>

2. <span data-ttu-id="62564-114">24時間ごとに Jive のアイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="62564-114">Once every 24 hours, items from Jive are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="62564-115">また、コネクタは Jive アイテムのコンテンツを電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="62564-115">The connector also converts the content of Jive items to an email message format.</span></span>

3. <span data-ttu-id="62564-116">Microsoft 365 コンプライアンスセンターで作成した Jive コネクタは、毎日 Globanet Merge1 サイトに接続し、そのコンテンツを Microsoft クラウド内のセキュリティ保護された Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="62564-116">The Jive connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="62564-117">このコネクタは、 [手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="62564-117">The connector imports the converted items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="62564-118">ユーザーメールボックスに **Jive** という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、そのフォルダーにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="62564-118">A new subfolder in the Inbox folder named **Jive** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="62564-119">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="62564-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="62564-120">すべての Jive item には、アイテムのすべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62564-120">Every Jive item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="62564-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="62564-121">Before you begin</span></span>

- <span data-ttu-id="62564-122">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="62564-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="62564-123">このアカウントを作成するには、 [globanet カスタマーサポート](https://globanet.com/ms-connectors-contact/)に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="62564-123">To create this account, contact [globanet customer support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="62564-124">このアカウントは、手順1でコネクタを作成するときにサインインします。</span><span class="sxs-lookup"><span data-stu-id="62564-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="62564-125">手順1で Jive コネクタを作成したユーザー (手順3で完了します) は、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="62564-125">The user who creates the Jive connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="62564-126">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="62564-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="62564-127">既定では、この役割は Exchange Online の役割グループに割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="62564-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="62564-128">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="62564-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="62564-129">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="62564-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="62564-130">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62564-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-jive-connector"></a><span data-ttu-id="62564-131">手順 1: Jive コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="62564-131">Step 1: Set up the Jive connector</span></span>

<span data-ttu-id="62564-132">最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、Jive データ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="62564-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jive data.</span></span>

1. <span data-ttu-id="62564-133">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **データコネクタ** の Jive] をクリックし  >  **Jive** ます。</span><span class="sxs-lookup"><span data-stu-id="62564-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Jive** .</span></span>

2. <span data-ttu-id="62564-134">**Jive** 製品の説明ページで、[ **コネクタの追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62564-134">On the **Jive** product description page, click **Add connector** .</span></span>

3. <span data-ttu-id="62564-135">[ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62564-135">On the **Terms of service** page, click **Accept** .</span></span>

4. <span data-ttu-id="62564-136">コネクタを識別する一意の名前を入力し、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62564-136">Enter a unique name that identifies the connector, and then click **Next** .</span></span>

5. <span data-ttu-id="62564-137">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="62564-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-jive-connector"></a><span data-ttu-id="62564-138">手順 2: Jive コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="62564-138">Step 2: Configure the Jive connector</span></span>

<span data-ttu-id="62564-139">2番目の手順は、Merge1 サイト上の Jive コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="62564-139">The second step is to configure the Jive connector on the Merge1 site.</span></span> <span data-ttu-id="62564-140">Jive コネクタを構成する方法については、「 [Merge1 サードパーティ製コネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62564-140">For information about how to configure the Jive connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf).</span></span>

<span data-ttu-id="62564-141">[ **保存 & 完了** ] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62564-141">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="62564-142">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="62564-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="62564-143">ユーザーをマップして、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="62564-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="62564-144">[ **Map Jive users To Microsoft 365 users** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="62564-144">On the **Map Jive users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="62564-145">Jive のアイテムには、組織内のユーザーの電子メールアドレスを含む *email* というプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62564-145">The Jive items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="62564-146">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="62564-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="62564-147">[ **管理者の同意** ] ページで、[ **同意を提供** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62564-147">On the **Admin Consent** page, click **Provide Consent** .</span></span> <span data-ttu-id="62564-148">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="62564-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="62564-149">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62564-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="62564-150">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="62564-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="62564-151">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62564-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="62564-152">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="62564-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="62564-153">[ **次へ** ] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="62564-153">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-jive-connector"></a><span data-ttu-id="62564-154">手順 4: Jive コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="62564-154">Step 4: Monitor the Jive connector</span></span>

<span data-ttu-id="62564-155">Jive コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="62564-155">After you create the Jive connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="62564-156">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[ **データコネクタ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62564-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="62564-157">[ **コネクタ** ] タブをクリックし、[ **Jive** コネクタ] を選択して、フライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="62564-157">Click the **Connectors** tab and then select the **Jive** connector to display the flyout page.</span></span> <span data-ttu-id="62564-158">このページには、コネクタに関するプロパティと情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="62564-158">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="62564-159">[ **コネクタの状態 (ソース付き** )] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="62564-159">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="62564-160">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="62564-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="62564-161">既知の問題</span><span class="sxs-lookup"><span data-stu-id="62564-161">Known issues</span></span>

- <span data-ttu-id="62564-162">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="62564-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="62564-163">より大きいアイテムのサポートは、後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="62564-163">Support for larger items will be available at a later date.</span></span>
