---
title: Cisco Jabber on PostgreSQL データをアーカイブするコネクタをセットアップMicrosoft 365
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
description: Microsoft 365 コンプライアンス センターでコネクタを設定して使用して、PostgreSQL の Cisco Jabber からデータをインポートおよびアーカイブする方法をMicrosoft 365。
ms.openlocfilehash: 06ec56b3b28b28b82554048ec788114a0e5cb389
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842748"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data-preview"></a><span data-ttu-id="3c8bb-103">PostgreSQL データの Cisco Jabber をアーカイブするコネクタをセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3c8bb-103">Set up a connector to archive Cisco Jabber on PostgreSQL data (preview)</span></span>

<span data-ttu-id="3c8bb-104">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、Cisco Jabber プラットフォームから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="3c8bb-105">Veritas は、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された、PostgreSQL コネクタ上の Cisco [Jabber](https://www.veritas.com/insights/merge1/jabber)を提供します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-105">Veritas provides a [Cisco Jabber on PostgreSQL](https://www.veritas.com/insights/merge1/jabber) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="3c8bb-106">コネクタは、メッセージ、チャット、共有コンテンツなどのコンテンツを、PostgreSQL の Cisco Jabber から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-106">The connector converts the content such as messages, chats, and shared content from Cisco Jabber on PostgreSQL to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="3c8bb-107">PostgreSQL データの Cisco Jabber がユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-107">After Cisco Jabber on PostgreSQL data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="3c8bb-108">PostgreSQL コネクタで Cisco Jabber を使用してデータをインポートおよびアーカイブすると、Microsoft 365規制ポリシーに準拠し、組織を支援できます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-108">Using a Cisco Jabber on PostgreSQL connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a><span data-ttu-id="3c8bb-109">PostgreSQL データでの Cisco Jabber のアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="3c8bb-109">Overview of archiving Cisco Jabber on PostgreSQL data</span></span>

<span data-ttu-id="3c8bb-110">次の概要では、コネクタを使用して、Cisco Jabber on PostgreSQL データをアーカイブするプロセスMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-110">The following overview explains the process of using a connector to archive the Cisco Jabber on PostgreSQL data in Microsoft 365.</span></span>

![PostgreSQL データの Cisco Jabber のアーカイブ ワークフロー](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. <span data-ttu-id="3c8bb-112">組織は、PostgreSQL の Cisco Jabber を使用して、PostgreSQL サイトで Cisco Jabber をセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-112">Your organization works with Cisco Jabber on PostgreSQL to set up and configure a Cisco Jabber on PostgreSQL site.</span></span>

2. <span data-ttu-id="3c8bb-113">24 時間に 1 回、PostgreSQL アイテムの Cisco Jabber が Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-113">Once every 24 hours, Cisco Jabber on PostgreSQL items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="3c8bb-114">また、このコネクタは、PostgreSQL アイテムの Cisco Jabber を電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-114">The connector also converts Cisco Jabber on PostgreSQL items to an email message format.</span></span>

3. <span data-ttu-id="3c8bb-115">Microsoft 365 コンプライアンス センターで作成した PostgreSQL コネクタ上の Cisco Jabber は、毎日 Veritas Merge1 サイトに接続し、Jabber コンテンツを Microsoft クラウド内の安全な Azure Storage 場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-115">The Cisco Jabber on PostgreSQL connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the Jabber content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="3c8bb-116">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="3c8bb-117">PostgreSQL の Cisco **Jabber** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-117">A subfolder in the Inbox folder named **Cisco Jabber on PostgreSQL** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="3c8bb-118">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="3c8bb-119">すべての Jabber アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-119">Every Jabber item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3c8bb-120">はじめに</span><span class="sxs-lookup"><span data-stu-id="3c8bb-120">Before you begin</span></span>

- <span data-ttu-id="3c8bb-121">Microsoft コネクタ用の Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="3c8bb-122">これを行うには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/en_US)。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/content/support/en_US).</span></span> <span data-ttu-id="3c8bb-123">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="3c8bb-124">手順 1 で PostgreSQL コネクタで Cisco Jabber を作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-124">The user who creates the Cisco Jabber on PostgreSQL connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="3c8bb-125">この役割は、コンプライアンス センターの [**データ** コネクタ] ページにコネクタを追加Microsoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3c8bb-126">既定では、この役割は、グループ内の任意の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="3c8bb-127">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3c8bb-128">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="3c8bb-129">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a><span data-ttu-id="3c8bb-130">手順 1: PostgreSQL コネクタで Cisco Jabber をセットアップする</span><span class="sxs-lookup"><span data-stu-id="3c8bb-130">Step 1: Set up the Cisco Jabber on PostgreSQL connector</span></span>

<span data-ttu-id="3c8bb-131">最初の手順は、コンプライアンス センターの [データ コネクタ] ページMicrosoft 365、Jabber データ用のコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Jabber data.</span></span>

1. <span data-ttu-id="3c8bb-132">PostgreSQL <https://compliance.microsoft.com> の [ **データ** コネクタ Cisco &gt; **Jabber] に移動し、[データ コネクタ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-132">Go to <https://compliance.microsoft.com> and then click **Data connectors** &gt; **Cisco Jabber on PostgreSQL**.</span></span>

2. <span data-ttu-id="3c8bb-133">**[PostgreSQL 製品の説明] ページの [Cisco Jabber]** で、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-133">On the **Cisco Jabber on PostgreSQL** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="3c8bb-134">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="3c8bb-135">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="3c8bb-136">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a><span data-ttu-id="3c8bb-137">手順 2: Veritas Merge1 サイトの PostgreSQL で Cisco Jabber を構成する</span><span class="sxs-lookup"><span data-stu-id="3c8bb-137">Step 2: Configure the Cisco Jabber on PostgreSQL on the Veritas Merge1 site</span></span>

<span data-ttu-id="3c8bb-138">2 番目の手順は、Veritas Merge1 サイトの PostgreSQL コネクタで Cisco Jabber を構成することです。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-138">The second step is to configure the Cisco Jabber on PostgreSQL connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="3c8bb-139">PostgreSQL コネクタで Cisco Jabber を構成する方法については [、「Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf)コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-139">For information about how to configure the Cisco Jabber on PostgreSQL connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf).</span></span>

<span data-ttu-id="3c8bb-140">[ファイルの **保存と&完了**] をクリックすると、コンプライアンス センターのコネクタ ウィザードの [ユーザー Microsoft 365] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="3c8bb-141">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="3c8bb-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="3c8bb-142">ユーザーをマップし、コンプライアンス センターでコネクタMicrosoft 365するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="3c8bb-143">**[PostgreSQL ユーザーに Cisco Jabber をマップして** ユーザー Microsoft 365する] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-143">On the **Map Cisco Jabber on PostgreSQL users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="3c8bb-144">PostgreSQL アイテムの Cisco Jabber には、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-144">The Cisco Jabber on PostgreSQL items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="3c8bb-145">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="3c8bb-146">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a><span data-ttu-id="3c8bb-147">手順 4: PostgreSQL コネクタで Cisco Jabber を監視する</span><span class="sxs-lookup"><span data-stu-id="3c8bb-147">Step 4: Monitor the Cisco Jabber on PostgreSQL connector</span></span>

<span data-ttu-id="3c8bb-148">PostgreSQL コネクタで Cisco Jabber を作成した後、コンプライアンス センターでコネクタのMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-148">After you create the Cisco Jabber on PostgreSQL connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3c8bb-149">左側の <https://compliance.microsoft.com/> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3c8bb-150">[コネクタ **] タブをクリック** し、PostgreSQL コネクタの **Cisco Jabber** を選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-150">Click the **Connectors** tab and then select the **Cisco Jabber on PostgreSQL** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="3c8bb-151">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="3c8bb-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="3c8bb-152">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3c8bb-153">既知の問題</span><span class="sxs-lookup"><span data-stu-id="3c8bb-153">Known issues</span></span>

- <span data-ttu-id="3c8bb-154">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていませんが、大きいアイテムのサポートは後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="3c8bb-154">At this time, we don't support importing attachments or items larger than 10 MB but support for larger items will be available at a later date.</span></span>
