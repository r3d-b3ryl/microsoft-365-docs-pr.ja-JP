---
title: ネットワーク内のテレグラム通信データをアーカイブするコネクタをMicrosoft 365
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
description: 管理者は、TeleMessage コネクタをセットアップして、テレグラム通信データをインポートおよびアーカイブMicrosoft 365。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 5db1869a1c386ed75f3d8d1381f598d907d2b5ba
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339444"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data"></a><span data-ttu-id="85c54-104">テレグラム通信データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="85c54-104">Set up a connector to archive Telegram communications data</span></span>

<span data-ttu-id="85c54-105">テレグラム チャット、添付ファイル、ファイル、および削除されたメッセージと呼び出しをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターの TeleMessage コネクタを使用します。</span><span class="sxs-lookup"><span data-stu-id="85c54-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive Telegram chats, attachments, files, and deleted messages and calls.</span></span> <span data-ttu-id="85c54-106">コネクタを設定して構成すると、そのコネクタは組織の TeleMessage アカウントに接続し、テレグラム アーカイブを使用する従業員のモバイル通信を Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="85c54-106">After you set up and configure a connector, it connects to your organization's TeleMessage account, and imports the mobile communication of employees using the Telegram Archiver to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="85c54-107">Telegram Archiver コネクタ データをユーザー メールボックスに格納した後、訴訟ホールド、コンテンツ検索、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をテレグラム通信データに適用できます。</span><span class="sxs-lookup"><span data-stu-id="85c54-107">After Telegram Archiver connector data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content search, and Microsoft 365 retention policies to Telegram communication data.</span></span> <span data-ttu-id="85c54-108">たとえば、コンテンツ検索を使用してテレグラム通信を検索したり、Telegram Archiver コネクタ データを含むメールボックスを保管担当者に関連付Advanced eDiscoveryできます。</span><span class="sxs-lookup"><span data-stu-id="85c54-108">For example, you can search Telegram communication using Content Search or associate the mailbox that contains the Telegram Archiver connector data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="85c54-109">Telegram Archiver コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織がコーポレート ガバナンス規制や規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85c54-109">Using a Telegram Archiver connector to import and archive data in Microsoft 365 can help your organization stay compliant with corporate governance regulations and regulatory policies.</span></span>

## <a name="overview-of-archiving-telegram-communications-data"></a><span data-ttu-id="85c54-110">テレグラム通信データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="85c54-110">Overview of archiving Telegram communications data</span></span>

<span data-ttu-id="85c54-111">次の概要では、コネクタを使用してテレグラム通信データをアーカイブするプロセスについて説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="85c54-111">The following overview explains the process of using a connector to archive  Telegram communications data in Microsoft 365.</span></span>

![テレグラム通信アーカイブ ワークフロー](../media/TelegramConnectorWorkflow.png)

1. <span data-ttu-id="85c54-113">組織は TeleMessage と一緒にテレグラム アーカイブ コネクタをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="85c54-113">Your organization works with TeleMessage to set up a Telegram Archiver connector.</span></span> <span data-ttu-id="85c54-114">詳細については[、「TeleMessage Telegram Archiver for the TeleMessage Archiver](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/)for Microsoft 365」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c54-114">For more information, see [Activating the TeleMessage Telegram Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/).</span></span>

2. <span data-ttu-id="85c54-115">リアルタイムで、組織の Telegram データが TeleMessage サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="85c54-115">In real time, your organization's Telegram data is copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="85c54-116">Microsoft 365 コンプライアンス センター で作成した Telegram Archiver コネクタは、毎日 TeleMessage サイトに接続し、過去 24 時間の電子メール メッセージを Microsoft Cloud の安全な Azure Storage 領域に転送します。</span><span class="sxs-lookup"><span data-stu-id="85c54-116">The Telegram Archiver connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the email messages from the previous 24 hours to a secure Azure Storage area in the Microsoft Cloud.</span></span>

4. <span data-ttu-id="85c54-117">コネクタは、モバイル通信アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="85c54-117">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="85c54-118">Telegram Archiver という名前の新しいフォルダーが特定のユーザーのメールボックスに作成され、アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="85c54-118">A new folder named Telegram Archiver will be created in the specific user's mailbox and the items will be imported to it.</span></span> <span data-ttu-id="85c54-119">コネクタは、User の [電子メール アドレス] プロパティの値を使用して *、このマッピングを実行* します。</span><span class="sxs-lookup"><span data-stu-id="85c54-119">The connector does this mapping by using the value of the *User's Email address* property.</span></span> <span data-ttu-id="85c54-120">すべての電子メール メッセージには、このプロパティが含まれるので、電子メール メッセージのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="85c54-120">Every email message contains this property, which is populated with the email address of every participant of the email message.</span></span>

> <span data-ttu-id="85c54-121">*User* の [電子メール アドレス] プロパティの値を使用した自動ユーザー マッピングに加えて、CSV マッピング ファイルをアップロードしてカスタム マッピングを定義できます。</span><span class="sxs-lookup"><span data-stu-id="85c54-121">In addition to automatic user mapping using the value of the *User's Email address* property, you can also define a custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="85c54-122">このマッピング ファイルには、ユーザーのモバイル番号と、各ユーザー Microsoft 365対応するメールボックス アドレスが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="85c54-122">This mapping file should contain User's mobile Number and the corresponding Microsoft 365 mailbox address for each user.</span></span> <span data-ttu-id="85c54-123">自動ユーザー マッピングを有効にしてカスタム マッピングを提供する場合、すべての電子メール アイテムについて、コネクタは最初にカスタム マッピング ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="85c54-123">If you enable automatic user mapping and provide a custom mapping, for every email item the connector will first look at custom mapping file.</span></span> <span data-ttu-id="85c54-124">ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからなかった場合、コネクタは電子メール アイテムのユーザーの電子メール アドレス プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="85c54-124">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile number, the connector will use the User ‘s email address property of the email item.</span></span> <span data-ttu-id="85c54-125">コネクタがカスタム マッピング ファイルまたは電子メール アイテムのユーザーの電子メール アドレス プロパティに有効な Microsoft 365 ユーザーを見つからなかった場合、アイテムはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="85c54-125">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or the *user's email address* property of the email item, the item won't be imported.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="85c54-126">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="85c54-126">Before you set up a connector</span></span>

- <span data-ttu-id="85c54-127">[Telegram アーカイブ サービスを TeleMessage から注文し](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)、組織の有効な管理アカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c54-127">Order the [Telegram archiving service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization.</span></span> <span data-ttu-id="85c54-128">コンプライアンス センターでコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85c54-128">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="85c54-129">TeleMessage アカウントで Telegram アーカイブが必要なすべてのユーザーを登録します。</span><span class="sxs-lookup"><span data-stu-id="85c54-129">Register all users that require Telegram archiving in the TeleMessage account.</span></span> <span data-ttu-id="85c54-130">ユーザーを登録する場合は、ユーザーのアカウントに使用するメール アドレスと同じMicrosoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="85c54-130">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="85c54-131">従業員の携帯電話に Telegram Archiver アプリをインストールし、アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="85c54-131">Install the Telegram Archiver app on the mobile phones of your employees and activate it.</span></span> <span data-ttu-id="85c54-132">Telegram Archiver アプリを使用すると、他の Telegram ユーザーと通信してチャットできます。</span><span class="sxs-lookup"><span data-stu-id="85c54-132">The Telegram Archiver app allows them to communicate and chat with other Telegram users.</span></span>

- <span data-ttu-id="85c54-133">手順 3 で Telegram Archiver コネクタを作成するユーザーには、メールボックスのインポート エクスポートの役割が割り当てられている必要Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="85c54-133">The user who creates a Telegram Archiver connector in Step 3 must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="85c54-134">これは、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="85c54-134">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="85c54-135">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="85c54-135">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="85c54-136">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="85c54-136">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="85c54-137">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="85c54-137">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="85c54-138">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="85c54-138">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-telegram-archiver-connector"></a><span data-ttu-id="85c54-139">テレグラム アーカイブ コネクタの作成</span><span class="sxs-lookup"><span data-stu-id="85c54-139">Create a Telegram Archiver connector</span></span>

<span data-ttu-id="85c54-140">前のセクションで説明した前提条件を完了したら、次のセクションで Telegram Archiver コネクタを作成Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="85c54-140">After you've completed the prerequisites described in the previous section, you can create the Telegram Archiver connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="85c54-141">コネクタは、指定した情報を使用して、TeleMessage サイトに接続し、テレグラム通信データをネットワーク内の対応するユーザー メールボックス ボックスに転送Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="85c54-141">The connector uses the information you provide to connect to the TeleMessage site and transfers Telegram communications data to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="85c54-142">[T <https://compliance.microsoft.com> **elegram Archiver]** の [**データ**>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c54-142">Go to <https://compliance.microsoft.com> and then click **Data connectors** > T **elegram Archiver**.</span></span>

2. <span data-ttu-id="85c54-143">**[Telegram Archiver 製品の説明] ページ** で、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="85c54-143">On the **Telegram Archiver** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="85c54-144">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="85c54-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="85c54-145">**[TeleMessage へのログイン]** ページの [手順 3] で、次のボックスに必要な情報を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="85c54-145">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

    - <span data-ttu-id="85c54-146">**ユーザー名:** TeleMessage ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="85c54-146">**Username:** Your TeleMessage username.</span></span>

    - <span data-ttu-id="85c54-147">**パスワード:** TeleMessage パスワード。</span><span class="sxs-lookup"><span data-stu-id="85c54-147">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="85c54-148">コネクタを作成したら、ポップアップ ウィンドウを閉じて次のページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="85c54-148">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="85c54-149">[ユーザー マッピング **] ページで** 、自動ユーザー マッピングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="85c54-149">On the **User mapping** page, enable automatic user mapping.</span></span> <span data-ttu-id="85c54-150">カスタム マッピングを有効にするには、ユーザー マッピング情報を含む CSV ファイルをアップロードし、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="85c54-150">To enable custom mapping, upload a CSV file that contains the user mapping information, and then click **Next**.</span></span>

7. <span data-ttu-id="85c54-151">設定を確認し、[完了] を **クリックして** コネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="85c54-151">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="85c54-152">[データ コネクタ] ページの [コネクタ] **タブに移動** して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="85c54-152">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="85c54-153">既知の問題</span><span class="sxs-lookup"><span data-stu-id="85c54-153">Known issues</span></span>

- <span data-ttu-id="85c54-154">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="85c54-154">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="85c54-155">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="85c54-155">Support for larger items will be available at a later date.</span></span>
