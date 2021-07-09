---
title: コネクタをセットアップして、Skype for BusinessデータをアーカイブMicrosoft 365
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
description: データをインポートおよびアーカイブする方法については、Microsoft 365 コンプライアンス センターでコネクタを設定して使用して、Skype for BusinessからMicrosoft 365。
ms.openlocfilehash: 4a66ee19530860bd482168297a8c935153442fee
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339456"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data"></a><span data-ttu-id="b2692-103">データをアーカイブするコネクタをSkype for Businessする</span><span class="sxs-lookup"><span data-stu-id="b2692-103">Set up a connector to archive Skype for Business data</span></span>

<span data-ttu-id="b2692-104">サーバーの Veritas コネクタを使用Microsoft 365 コンプライアンス センター、Skype for Business プラットフォームから組織のユーザー メールボックスにデータをインポートMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="b2692-104">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Skype for Business platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b2692-105">Veritas には[](https://www.veritas.com/en/au/insights/merge1/skype-for-business)、Skype for Business データ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムをデータ ソースにインポートするように構成された Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b2692-105">Veritas provides a [Skype for Business](https://www.veritas.com/en/au/insights/merge1/skype-for-business) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="b2692-106">コネクタは、ユーザー間のメッセージ、常設チャット、会議メッセージなどのコンテンツを Skype for Business から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="b2692-106">The connector converts the content such as messages between users, persistent chats, and conference messages from Skype for Business to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="b2692-107">ユーザー Skype for Businessにデータを保存した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルMicrosoft 365コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="b2692-107">After Skype for Business data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="b2692-108">アプリケーション コネクタSkype for Business使用して、データをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b2692-108">Using a Skype for Business connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-skype-for-business-data"></a><span data-ttu-id="b2692-109">データのアーカイブSkype for Business概要</span><span class="sxs-lookup"><span data-stu-id="b2692-109">Overview of archiving Skype for Business data</span></span>

<span data-ttu-id="b2692-110">次の概要では、コネクタを使用してデータをアーカイブするプロセスSkype for Business説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b2692-110">The following overview explains the process of using a connector to archive the Skype for Business data in Microsoft 365.</span></span>

![データをアーカイブするSkype for Businessワークフロー](../media/SkypeforBusinessConnectorWorkflow.png)

1. <span data-ttu-id="b2692-112">組織は、Skype for Businessサイトをセットアップおよび構成するためにSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="b2692-112">Your organization works with Skype for Business to set up and configure a Skype for Business site.</span></span>

2. <span data-ttu-id="b2692-113">24 時間に 1 回Skype for Businessは Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="b2692-113">Once every 24 hours, Skype for Business items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="b2692-114">また、コネクタは、Skype for Businessを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="b2692-114">The connector also converts Skype for Business items to an email message format.</span></span>

3. <span data-ttu-id="b2692-115">Microsoft 365 コンプライアンス センター で作成した Skype for Business コネクタは、毎日 Veritas Merge1 サイトに接続し、Skype for Business コンテンツを Microsoft クラウド内の安全な Azure Storage 場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="b2692-115">The Skype for Business connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the Skype for Business content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b2692-116">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="b2692-116">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="b2692-117">[受信トレイ] という名前の **Skype for Business** サブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b2692-117">A subfolder in the Inbox folder named **Skype for Business** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="b2692-118">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="b2692-118">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="b2692-119">すべてのSkype for Businessには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b2692-119">Every Skype for Business item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="b2692-120">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="b2692-120">Before you set up a connector</span></span>

- <span data-ttu-id="b2692-121">Microsoft コネクタ用の Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2692-121">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="b2692-122">これを行うには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/form/requestacall/ms-connectors-contact.html)。</span><span class="sxs-lookup"><span data-stu-id="b2692-122">To do this, contact [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact.html).</span></span> <span data-ttu-id="b2692-123">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2692-123">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b2692-124">手順 1 で Skype for Business コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2692-124">The user who creates the Skype for Business connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b2692-125">この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="b2692-125">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b2692-126">既定では、この役割は、グループ内の任意の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="b2692-126">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="b2692-127">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b2692-127">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b2692-128">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="b2692-128">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b2692-129">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b2692-129">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-skype-for-business-connector"></a><span data-ttu-id="b2692-130">手順 1: コネクタをSkype for Businessする</span><span class="sxs-lookup"><span data-stu-id="b2692-130">Step 1: Set up the Skype for Business connector</span></span>

<span data-ttu-id="b2692-131">最初の手順は、 [データコネクタ] ページの [データ コネクタ] ページにアクセスしMicrosoft 365 コンプライアンス センターデータのコネクタをSkype for Businessすることです。</span><span class="sxs-lookup"><span data-stu-id="b2692-131">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Skype for Business data.</span></span>

1. <span data-ttu-id="b2692-132">に移動し <https://compliance.microsoft.com> 、[**データ コネクタ] を**  >  **クリックSkype for Business。**</span><span class="sxs-lookup"><span data-stu-id="b2692-132">Go to <https://compliance.microsoft.com> and click **Data connectors** > **Skype for Business**.</span></span>

2. <span data-ttu-id="b2692-133">[製品の **Skype for Business]** ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b2692-133">On the **Skype for Business** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b2692-134">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b2692-134">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b2692-135">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b2692-135">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="b2692-136">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b2692-136">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a><span data-ttu-id="b2692-137">手順 2: Veritas Merge1 サイトSkype for Businessを構成する</span><span class="sxs-lookup"><span data-stu-id="b2692-137">Step 2: Configure the Skype for Business on the Veritas Merge1 site</span></span>

<span data-ttu-id="b2692-138">2 番目の手順は、Veritas Merge1 サイトSkype for Businessコネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="b2692-138">The second step is to configure the Skype for Business connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="b2692-139">コネクタを構成する方法についてはSkype for Business [Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)コネクタ ユーザー ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2692-139">For information about how to configure the Skype for Business connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf).</span></span>

<span data-ttu-id="b2692-140">[ファイルの **保存と&完了**] をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。</span><span class="sxs-lookup"><span data-stu-id="b2692-140">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="b2692-141">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="b2692-141">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="b2692-142">ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2692-142">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="b2692-143">[ユーザーを **ユーザーにSkype for BusinessするMicrosoft 365]** ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b2692-143">On the **Map Skype for Business users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="b2692-144">このSkype for Businessには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2692-144">The Skype for Business items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="b2692-145">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b2692-145">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="b2692-146">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="b2692-146">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-skype-for-business-connector"></a><span data-ttu-id="b2692-147">手順 4: コネクタをSkype for Businessする</span><span class="sxs-lookup"><span data-stu-id="b2692-147">Step 4: Monitor the Skype for Business connector</span></span>

<span data-ttu-id="b2692-148">コネクタコネクタを作成Skype for Business、コネクタの状態を [コネクタ] で表示Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="b2692-148">After you create the Skype for Business connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b2692-149">左側の <https://compliance.microsoft.com/> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2692-149">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b2692-150">[コネクタ **] タブを** クリックし、Skype for Businessコネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。 </span><span class="sxs-lookup"><span data-stu-id="b2692-150">Click the **Connectors** tab and then select the **Skype for Business** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b2692-151">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="b2692-151">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b2692-152">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2692-152">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b2692-153">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b2692-153">Known issues</span></span>

- <span data-ttu-id="b2692-154">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b2692-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b2692-155">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="b2692-155">Support for larger items will be available at a later date.</span></span>
