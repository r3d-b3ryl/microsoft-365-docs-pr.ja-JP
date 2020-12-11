---
title: Microsoft 365 で Jive データをアーカイブするコネクタを設定する
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
description: 管理者は、Microsoft 365 の Globanet から Jive データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: e89404362505dbe276e351e95ebd30a0c0bdf88c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620394"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a><span data-ttu-id="b26f8-104">Jive データをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="b26f8-104">Set up a connector to archive Jive data</span></span>

<span data-ttu-id="b26f8-105">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、コラボレーション プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートしてアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="b26f8-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b26f8-106">Globanet は、サード パーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Jive](https://globanet.com/jive/) コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-106">Globanet provides a [Jive](https://globanet.com/jive/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="b26f8-107">コネクタは、電子メール メッセージ、チャット、添付ファイルなどのコンテンツをユーザーの Jive アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="b26f8-107">The connector converts content such as email messages, chats, and attachments from a user's Jive account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="b26f8-108">Jive データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-108">After Jive data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="b26f8-109">Jive コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-109">Using a Jive connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-jive-data"></a><span data-ttu-id="b26f8-110">アーカイブ Jive データの概要</span><span class="sxs-lookup"><span data-stu-id="b26f8-110">Overview of archiving Jive data</span></span>

<span data-ttu-id="b26f8-111">次の概要では、コネクタを使用して Microsoft 365 の Jive データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-111">The following overview explains the process of using a connector to archive the Jive data in Microsoft 365.</span></span>

![Jive データのアーカイブ ワークフロー](../media/JiveConnectorWorkflow.png)

1. <span data-ttu-id="b26f8-113">組織は Jive と共同で Jive サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-113">Your organization works with Jive to set up and configure a Jive site.</span></span>

2. <span data-ttu-id="b26f8-114">24 時間ごとに、Jive からのアイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-114">Once every 24 hours, items from Jive are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="b26f8-115">コネクタは、Jive アイテムのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-115">The connector also converts the content of Jive items to an email message format.</span></span>

3. <span data-ttu-id="b26f8-116">Microsoft 365 コンプライアンス センターで作成する Jive コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にコンテンツを転送します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-116">The Jive connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b26f8-117">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="b26f8-117">The connector imports the converted items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="b26f8-118">ユーザー メールボックスに **Jive** という名前の受信トレイ フォルダーに新しいサブフォルダーが作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-118">A new subfolder in the Inbox folder named **Jive** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="b26f8-119">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="b26f8-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="b26f8-120">すべての Jive アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-120">Every Jive item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b26f8-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="b26f8-121">Before you begin</span></span>

- <span data-ttu-id="b26f8-122">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="b26f8-123">このアカウントを作成するには [、globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact/)。</span><span class="sxs-lookup"><span data-stu-id="b26f8-123">To create this account, contact [globanet customer support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="b26f8-124">このアカウントは、手順 1 でコネクタを作成するときにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b26f8-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b26f8-125">手順 1 で Jive コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b26f8-125">The user who creates the Jive connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b26f8-126">この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="b26f8-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b26f8-127">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="b26f8-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="b26f8-128">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b26f8-129">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b26f8-130">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b26f8-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-jive-connector"></a><span data-ttu-id="b26f8-131">手順 1: Jive コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="b26f8-131">Step 1: Set up the Jive connector</span></span>

<span data-ttu-id="b26f8-132">最初の手順は、Microsoft 365 コンプライアンス センターの [Data **Connectors]** ページにアクセスし、Jive データ用のコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="b26f8-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jive data.</span></span>

1. <span data-ttu-id="b26f8-133">[データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ  >  **Jive]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="b26f8-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Jive**.</span></span>

2. <span data-ttu-id="b26f8-134">**[Jive 製品の説明]** ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b26f8-134">On the **Jive** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b26f8-135">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b26f8-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b26f8-136">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b26f8-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="b26f8-137">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b26f8-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-jive-connector"></a><span data-ttu-id="b26f8-138">手順 2: Jive コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="b26f8-138">Step 2: Configure the Jive connector</span></span>

<span data-ttu-id="b26f8-139">2 番目の手順は、Merge1 サイトで Jive コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="b26f8-139">The second step is to configure the Jive connector on the Merge1 site.</span></span> <span data-ttu-id="b26f8-140">Jive コネクタを構成する方法の詳細については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b26f8-140">For information about how to configure the Jive connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf).</span></span>

<span data-ttu-id="b26f8-141">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="b26f8-142">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="b26f8-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="b26f8-143">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="b26f8-144">**[Jive ユーザーを Microsoft 365** ユーザーにマップする] ページで、ユーザーの自動マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b26f8-144">On the **Map Jive users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="b26f8-145">Jive アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-145">The Jive items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="b26f8-146">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="b26f8-147">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-147">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-jive-connector"></a><span data-ttu-id="b26f8-148">手順 4: Jive コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="b26f8-148">Step 4: Monitor the Jive connector</span></span>

<span data-ttu-id="b26f8-149">Jive コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-149">After you create the Jive connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b26f8-150">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="b26f8-150">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b26f8-151">[ **コネクタ] タブを** クリックし **、[Jive** コネクタ] を選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="b26f8-151">Click the **Connectors** tab and then select the **Jive** connector to display the flyout page.</span></span> <span data-ttu-id="b26f8-152">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="b26f8-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b26f8-153">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="b26f8-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b26f8-154">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b26f8-154">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b26f8-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b26f8-155">Known issues</span></span>

- <span data-ttu-id="b26f8-156">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b26f8-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b26f8-157">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="b26f8-157">Support for larger items will be available at a later date.</span></span>
