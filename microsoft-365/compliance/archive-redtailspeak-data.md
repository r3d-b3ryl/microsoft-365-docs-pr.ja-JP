---
title: Microsoft 365 で Redtail Speak データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet から Microsoft 365 に Redtail Speak データをインポートしてアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 546298288e69746856a1250cc4b87643dd479c91
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2020
ms.locfileid: "49723008"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data-preview"></a><span data-ttu-id="65739-105">Redtail Speak データをアーカイブするコネクタをセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="65739-105">Set up a connector to archive Redtail Speak data (preview)</span></span>

<span data-ttu-id="65739-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Microsoft 365 組織内の Redtail Speak to user メールボックスからデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="65739-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Redtail Speak to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="65739-107">Globanet は [、Redtail](https://globanet.com/redtail/) からアイテムを受信する組織の SFTP サーバーからアイテムをキャプチャするように構成された Redtail Speak コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="65739-107">Globanet provides you with a [Redtail Speak](https://globanet.com/redtail/) connector that's configured to capture items from your organization’s SFTP server where the items are received from Redtail.</span></span> <span data-ttu-id="65739-108">コネクタは、Redtail Speak から電子メール メッセージ形式にコンテンツを変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="65739-108">The connector converts the content from Redtail Speak to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="65739-109">Redtail Speak データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="65739-109">After Redtail Speak data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="65739-110">Redtail Speak コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="65739-110">Using a Redtail Speak connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-redtail-speak-data"></a><span data-ttu-id="65739-111">Redtail Speak データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="65739-111">Overview of archiving the Redtail Speak data</span></span>

<span data-ttu-id="65739-112">次の概要では、コネクタを使用して Microsoft 365 の Redtail Speak データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="65739-112">The following overview explains the process of using a connector to archive the Redtail Speak data in Microsoft 365.</span></span>

![Redtail Speak データのアーカイブ ワークフロー](../media/RedtailSpeakConnectorWorkflow.png)

1. <span data-ttu-id="65739-114">組織は Redtail Speak と連携して、毎日のメッセージが Redtail Speak から組織の SFTP サーバーに転送される SMTP ゲートウェイを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="65739-114">Your organization works with Redtail Speak to set up and configure an SMTP gateway where daily messages are forwarded from Redtail Speak to your organizations SFTP server.</span></span>

2. <span data-ttu-id="65739-115">24 時間ごとに Redtail Speak アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="65739-115">Once every 24 hours, the Redtail Speak items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="65739-116">コネクタは、Redtail Speak アイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="65739-116">The connector also converts the Redtail Speak items to an email message format.</span></span>

3. <span data-ttu-id="65739-117">Microsoft 365 コンプライアンス センターで作成する Redtail Speak コネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="65739-117">The Redtail Speak connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="65739-118">コネクタは、ステップ 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Redtail Speak アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="65739-118">The connector imports the converted Redtail Speak items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="65739-119">**Redtail Speak** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="65739-119">A subfolder in the Inbox folder named **Redtail Speak** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="65739-120">コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="65739-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="65739-121">すべての Redtail Speak アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="65739-121">Every Redtail Speak item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="65739-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="65739-122">Before you begin</span></span>

- <span data-ttu-id="65739-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="65739-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="65739-124">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="65739-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="65739-125">手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65739-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="65739-126">手順で、組織の SFTP サーバーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65739-126">In Step you, you need to specify your organization's SFTP server.</span></span> <span data-ttu-id="65739-127">これは、Globanet Merge1 が SFTP を介して Redtail Speak データを収集するために通信するために必要です。</span><span class="sxs-lookup"><span data-stu-id="65739-127">This is necessary so that Globanet Merge1 can contact it to collect Redtail Speak data via SFTP.</span></span>

- <span data-ttu-id="65739-128">手順 1 で Redtail Speak Importer コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65739-128">The user who creates the Redtail Speak Importer connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="65739-129">この役割は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="65739-129">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="65739-130">既定では、この役割は Exchange Online の役割グループには割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="65739-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="65739-131">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="65739-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="65739-132">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="65739-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="65739-133">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65739-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-redtail-speak-connector"></a><span data-ttu-id="65739-134">手順 1: Redtail Speak コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="65739-134">Step 1: Set up the Redtail Speak connector</span></span>

<span data-ttu-id="65739-135">最初の手順は、Microsoft 365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、Redtail Speak データ用のコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="65739-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for the Redtail Speak data.</span></span>

1. <span data-ttu-id="65739-136">[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/)  &gt; **Redtail Speak] に移動してクリックします**。</span><span class="sxs-lookup"><span data-stu-id="65739-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** &gt; **Redtail Speak**.</span></span>

2. <span data-ttu-id="65739-137">Redtail **Speak 製品の説明ページ** で、[新しいコネクタの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="65739-137">On the **Redtail Speak** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="65739-138">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="65739-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="65739-139">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="65739-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="65739-140">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="65739-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="65739-141">手順 2: Globanet Merge1 サイトで Redtail Speak コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="65739-141">Step 2: Configure the Redtail Speak connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="65739-142">2 番目の手順は、Merge1 サイトで Redtail Speak コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="65739-142">The second step is to configure the Redtail Speak connector on the Merge1 site.</span></span> <span data-ttu-id="65739-143">Redtail Speak コネクタを構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="65739-143">For information about how to configure the Redtail Speak connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="65739-144">[Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65739-144">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="65739-145">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="65739-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="65739-146">ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="65739-146">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="65739-147">**[Redtail Speak ユーザーを Microsoft 365** ユーザーにマップする] ページで、ユーザーの自動マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65739-147">On the **Map Redtail Speak users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="65739-148">Redtail Speak アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="65739-148">The Redtail Speak items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="65739-149">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="65739-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="65739-150">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="65739-150">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-redtail-speak-connector"></a><span data-ttu-id="65739-151">手順 4: Redtail Speak コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="65739-151">Step 4: Monitor the Redtail Speak connector</span></span>

<span data-ttu-id="65739-152">Redtail Speak コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="65739-152">After you create the Redtail Speak connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="65739-153">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="65739-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="65739-154">[ **コネクタ] タブをクリック** し **、Redtail Speak** コネクタを選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="65739-154">Click the **Connectors** tab and then select the **Redtail Speak** connector to display the flyout page.</span></span> <span data-ttu-id="65739-155">このページには、コネクタに関するプロパティと情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="65739-155">This page displays properties and information about the connector.</span></span>

3. <span data-ttu-id="65739-156">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="65739-156">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="65739-157">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="65739-157">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="65739-158">既知の問題</span><span class="sxs-lookup"><span data-stu-id="65739-158">Known issues</span></span>

- <span data-ttu-id="65739-159">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65739-159">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="65739-160">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="65739-160">Support for larger items will be available at a later date.</span></span>
