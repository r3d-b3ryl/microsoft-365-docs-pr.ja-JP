---
title: FX データをアーカイブするコネクタConnectを設定Microsoft 365
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
description: 管理者は、Veritas FX からデータをインポートおよびアーカイブするコネクタを設定して、ConnectをMicrosoft 365。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 1efbe8d6d8cecdd8394b565abad4d33c8610398f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164263"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a><span data-ttu-id="2c73f-104">FX データをアーカイブするコネクタConnectする</span><span class="sxs-lookup"><span data-stu-id="2c73f-104">Set up a connector to archive FX Connect data</span></span>

<span data-ttu-id="2c73f-105">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、FX Connect コラボレーション プラットフォームから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="2c73f-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the FX Connect collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="2c73f-106">Veritas には[、FX](https://globanet.com/fx-connect/) Connectアイテムをキャプチャし、それらのアイテムをインポートするように構成された FX ConnectコネクタがMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="2c73f-106">Veritas provides an [FX Connect](https://globanet.com/fx-connect/) connector that is configured to capture FX Connect items and import those items to Microsoft 365.</span></span> <span data-ttu-id="2c73f-107">コネクタは、組織の FX Connect アカウントの取引、メッセージ、その他の詳細などのコンテンツを FX Connect から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="2c73f-107">The connector converts the content from FX Connect, such as  trades, messages, and other details from your organization's FX Connect account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="2c73f-108">FX Connectデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-108">After FX Connect data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="2c73f-109">FX Connectコネクタを使用して、データをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-109">Using an FX Connect connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fx-connect-data"></a><span data-ttu-id="2c73f-110">データのアーカイブ FX Connect概要</span><span class="sxs-lookup"><span data-stu-id="2c73f-110">Overview of archiving FX Connect data</span></span>

<span data-ttu-id="2c73f-111">次の概要では、コネクタを使用して、FX ファイルの情報をアーカイブするプロセスConnect説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2c73f-111">The following overview explains the process of using a connector to archive the FX Connect information in Microsoft 365.</span></span>

![FX データのアーカイブ ワークフロー Connectする](../media/FXConnectConnectorWorkflow.png)

1. <span data-ttu-id="2c73f-113">組織は、FX Connectを使用して、FX サイトをConnectします。</span><span class="sxs-lookup"><span data-stu-id="2c73f-113">Your organization works with FX Connect to set up and configure an FX Connect site.</span></span>

2. <span data-ttu-id="2c73f-114">24 時間に 1 回、FX アカウントConnectは Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-114">Once every 24 hours, items from FX Connect accounts are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="2c73f-115">また、コネクタは、FX ファイルConnectメール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="2c73f-115">The connector also converts the FX Connect items to an email message format.</span></span>

3. <span data-ttu-id="2c73f-116">Microsoft 365 コンプライアンス センターで作成した FX Connect コネクタは、毎日 Veritas Merge1 サイトに接続し、FX Connect アイテムを Microsoft クラウド内の安全な Azure Storage 場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="2c73f-116">The FX Connect connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the FX Connect items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="2c73f-117">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="2c73f-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="2c73f-118">FX ファイルという名前の受信 **トレイ フォルダー Connect** ユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-118">A subfolder in the Inbox folder named **FX Connect** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="2c73f-119">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="2c73f-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="2c73f-120">すべての FX Connectには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-120">Every FX Connect item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2c73f-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="2c73f-121">Before you begin</span></span>

- <span data-ttu-id="2c73f-122">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c73f-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span>  <span data-ttu-id="2c73f-123">アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="2c73f-123">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="2c73f-124">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2c73f-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="2c73f-125">手順 1 で FX Connect コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c73f-125">The user who creates the FX Connect connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="2c73f-126">この役割は、コンプライアンス センターの [**データ** コネクタ] ページにコネクタを追加Microsoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="2c73f-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2c73f-127">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="2c73f-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="2c73f-128">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2c73f-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="2c73f-129">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="2c73f-130">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2c73f-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-fx-connect-connector"></a><span data-ttu-id="2c73f-131">手順 1: FX コネクタをConnectする</span><span class="sxs-lookup"><span data-stu-id="2c73f-131">Step 1: Set up the FX Connect connector</span></span>

<span data-ttu-id="2c73f-132">最初の手順は、コンプライアンス センターの [データ コネクタ] ページにアクセスし、Microsoft 365データ用のコネクタをConnectすることです。</span><span class="sxs-lookup"><span data-stu-id="2c73f-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for FX Connect data.</span></span>

1. <span data-ttu-id="2c73f-133">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データ** コネクタ  >  **FX] をクリックConnect。**</span><span class="sxs-lookup"><span data-stu-id="2c73f-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **FX Connect**.</span></span>

2. <span data-ttu-id="2c73f-134">[FX 製品 **の説明Connect]** ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2c73f-134">On the **FX Connect** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="2c73f-135">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2c73f-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="2c73f-136">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2c73f-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="2c73f-137">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2c73f-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-fx-connect-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="2c73f-138">手順 2: Veritas Merge1 サイトで FX Connectコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="2c73f-138">Step 2: Configure the FX Connect connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="2c73f-139">2 番目の手順は、Merge1 サイトで FX Connectコネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="2c73f-139">The second step is to configure the FX Connect connector on the Merge1 site.</span></span> <span data-ttu-id="2c73f-140">FX コネクタを構成する方法Connect Merge1 サードパーティ コネクタ ユーザー ガイド[を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="2c73f-140">For information about how to configure the FX Connect connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="2c73f-141">[ファイルの **保存と&完了**] をクリックすると、コンプライアンス センターのコネクタ ウィザードの [ユーザー Microsoft 365] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="2c73f-142">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="2c73f-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="2c73f-143">ユーザーをマップし、コンプライアンス センターでコネクタMicrosoft 365するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c73f-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="2c73f-144">[ユーザーに **ユーザーをConnectする**] Microsoft 365 FX マップ] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2c73f-144">On the **Map FX Connect users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="2c73f-145">FX のConnectには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-145">The FX Connect items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="2c73f-146">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="2c73f-147">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="2c73f-147">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-fx-connect-connector"></a><span data-ttu-id="2c73f-148">手順 4: FX コネクタをConnectする</span><span class="sxs-lookup"><span data-stu-id="2c73f-148">Step 4: Monitor the FX Connect connector</span></span>

<span data-ttu-id="2c73f-149">FX コネクタ コネクタをConnect、コンプライアンス センターでコネクタの状態Microsoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-149">After you create the FX Connect connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="2c73f-150">左側の <https://compliance.microsoft.com/> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c73f-150">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="2c73f-151">[コネクタ **] タブを** クリックし **、FX** Connectを選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="2c73f-151">Click the **Connectors** tab and then select the **FX Connect** connector to display the flyout page.</span></span> <span data-ttu-id="2c73f-152">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="2c73f-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="2c73f-153">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="2c73f-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="2c73f-154">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2c73f-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="2c73f-155">Known issues</span></span>

- <span data-ttu-id="2c73f-156">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2c73f-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="2c73f-157">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="2c73f-157">Support for larger items will be available at a later date.</span></span>