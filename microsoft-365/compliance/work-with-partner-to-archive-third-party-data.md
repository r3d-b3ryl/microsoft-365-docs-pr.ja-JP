---
title: パートナーと共同作業して、サード パーティのデータをアーカイブする
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
description: カスタム コネクタをセットアップして、Salesforce Chatter、Yahoo Messenger、またはデータ ソースなどのデータ ソースからサードパーティのデータをインポートするYammer。
ms.openlocfilehash: 2026e3c584cb0bc467a2db3903c51b7ed50e51e1
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228761"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="542cd-103">パートナーと共同作業して、サード パーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="542cd-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="542cd-104">Microsoft パートナーと一緒に作業して、サード パーティ製のデータ ソースからデータをインポートおよびアーカイブし、Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="542cd-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="542cd-105">パートナーは、サードパーティのデータ ソースからアイテムを抽出し (定期的に) それらのアイテムをインポートするように構成されたカスタム コネクタを提供できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="542cd-106">パートナー コネクタは、アイテムのコンテンツをデータ ソースから電子メール メッセージ形式に変換し、アイテムをメールボックスに格納します。</span><span class="sxs-lookup"><span data-stu-id="542cd-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="542cd-107">サード パーティのデータをインポートした後、訴訟ホールド、電子情報開示、In-Place アーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をこのデータに適用できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="542cd-108">この[記事で](communication-compliance.md)説明Microsoft 365コネクタによってインポートされたサード パーティのデータには、通信コンプライアンス ソリューションを適用できません。</span><span class="sxs-lookup"><span data-stu-id="542cd-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span>

<span data-ttu-id="542cd-109">Microsoft パートナーと一緒にサード パーティのデータをインポートするために必要なプロセスと手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="542cd-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="542cd-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="542cd-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="542cd-111">手順 2: サード パーティ製のデータ メールボックスを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="542cd-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="542cd-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="542cd-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="542cd-113">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="542cd-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="542cd-114">手順 5: サード パーティ製のデータ コネクタをデバイスに登録Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="542cd-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="542cd-115">サードパーティのデータのインポート プロセスが実行される方法</span><span class="sxs-lookup"><span data-stu-id="542cd-115">How the third-party data import process works</span></span>

<span data-ttu-id="542cd-116">次の図と説明では、パートナーを操作するときにサード パーティのデータ インポート プロセスがどのように機能しているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="542cd-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>

![サードパーティのデータのインポート プロセスが実行される方法](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. <span data-ttu-id="542cd-118">お客様は、選択したパートナーと一緒に、サードパーティのデータ ソースからアイテムを抽出し、そのアイテムを外部にインポートするコネクタを構成Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="542cd-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>

2. <span data-ttu-id="542cd-119">パートナー コネクタは、サード パーティ製 API を介して (スケジュールまたは構成済み) サードパーティ のデータ ソースに接続し、データ ソースからアイテムを抽出します。</span><span class="sxs-lookup"><span data-stu-id="542cd-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="542cd-120">パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="542cd-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="542cd-121">メッセージ形式 [スキーマの説明](#more-information) については、「詳細」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="542cd-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span>

3. <span data-ttu-id="542cd-122">パートナー コネクタは、既知のエンド Microsoft 365経由で Exchange Web サービス (EWS) を使用して、Azure サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="542cd-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>

4. <span data-ttu-id="542cd-p103">アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。</span><span class="sxs-lookup"><span data-stu-id="542cd-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>

   1. <span data-ttu-id="542cd-125">**ユーザー アカウントに対応するユーザー ID を持つアイテム。** パートナー コネクタがサードパーティ データ ソース内のアイテムのユーザー ID を Microsoft 365 の特定のユーザー ID にマップできる場合、そのアイテムはユーザーの回復可能なアイテム フォルダーの **Purges** フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="542cd-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="542cd-126">ユーザーは Purges フォルダー内のアイテムにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="542cd-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="542cd-127">ただし、電子情報開示ツールを使用して、Purges フォルダー内のアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>

   1. <span data-ttu-id="542cd-128">**ユーザー アカウントに対応するユーザー ID を持** つアイテム:パートナー コネクタがアイテムのユーザー ID を特定のユーザー ID にマップできない場合、そのアイテムはサードパーティのデータ メールボックスの **受信** トレイ フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="542cd-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="542cd-129">アイテムを受信トレイにインポートすると、自分または組織内の誰かがサード パーティのメールボックスにサインインして、これらのアイテムを表示および管理し、パートナー コネクタ構成で調整が必要な場合に確認できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>

## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="542cd-130">手順 1: サード パーティのデータのパートナーを見つける</span><span class="sxs-lookup"><span data-stu-id="542cd-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="542cd-131">Microsoft 365 でサード パーティのデータをアーカイブするための重要なコンポーネントは、サード パーティのデータ ソースからのデータのキャプチャと Microsoft 365 へのインポートに特化した Microsoft パートナーの検索と操作です。</span><span class="sxs-lookup"><span data-stu-id="542cd-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="542cd-132">データをインポートした後、Exchange からのメールや SharePoint および OneDrive for Business からのドキュメントなど、組織の他の Microsoft データと共にアーカイブおよび保存できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="542cd-133">パートナーは、組織のサードパーティデータ ソース (BlackBerry、Facebook、Google+、トムソン ロイター、Twitter、YouTube など) からデータを抽出するコネクタを作成し、そのデータを Microsoft 365 API に渡して、アイテムを Exchange メールボックスに電子メール メッセージとしてインポートします。</span><span class="sxs-lookup"><span data-stu-id="542cd-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>

<span data-ttu-id="542cd-134">次のセクションでは、microsoft パートナー (およびサポートしているサード パーティのデータ ソース) を一覧表示します。このプログラムは、Microsoft 365 でサード パーティのデータをアーカイブするプログラムに参加しています。</span><span class="sxs-lookup"><span data-stu-id="542cd-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="542cd-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="542cd-135">17a-4 LLC</span></span>](#17a-4-llc)

[<span data-ttu-id="542cd-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="542cd-136">ArchiveSocial</span></span>](#archivesocial)

[<span data-ttu-id="542cd-137">Veritas</span><span class="sxs-lookup"><span data-stu-id="542cd-137">Veritas</span></span>](#veritas)

[<span data-ttu-id="542cd-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="542cd-138">OpenText</span></span>](#opentext)

[<span data-ttu-id="542cd-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="542cd-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="542cd-140">Verba</span><span class="sxs-lookup"><span data-stu-id="542cd-140">Verba</span></span>](#verba)

### <a name="17a-4-llc"></a><span data-ttu-id="542cd-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="542cd-141">17a-4 LLC</span></span>

<span data-ttu-id="542cd-142">[17a-4 LLC では](https://www.17a-4.com) 、次のサード パーティ製データ ソースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="542cd-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="542cd-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="542cd-143">BlackBerry</span></span>

- <span data-ttu-id="542cd-144">Bloomberg データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="542cd-144">Bloomberg Data Streams</span></span>

- <span data-ttu-id="542cd-145">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="542cd-145">Cisco Jabber</span></span>

- <span data-ttu-id="542cd-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="542cd-146">FactSet</span></span>

- <span data-ttu-id="542cd-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="542cd-147">HipChat</span></span>

- <span data-ttu-id="542cd-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="542cd-148">InvestEdge</span></span>

- <span data-ttu-id="542cd-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="542cd-149">LivePerson</span></span>

- <span data-ttu-id="542cd-150">MessageLabs データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="542cd-150">MessageLabs Data Streams</span></span>

- <span data-ttu-id="542cd-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="542cd-151">OpenText</span></span>

- <span data-ttu-id="542cd-152">Oracle/ATG 'click-to-call' Live ヘルプ</span><span class="sxs-lookup"><span data-stu-id="542cd-152">Oracle/ATG 'click-to-call' Live Help</span></span>

- <span data-ttu-id="542cd-153">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="542cd-153">Pivot IMTRADER</span></span>

- <span data-ttu-id="542cd-154">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="542cd-154">Microsoft SharePoint</span></span>

- <span data-ttu-id="542cd-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="542cd-155">MindAlign</span></span>

- <span data-ttu-id="542cd-156">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="542cd-156">Sitrion One (Newsgator)</span></span>

- <span data-ttu-id="542cd-157">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="542cd-157">Skype for Business (Lync/OCS)</span></span>

- <span data-ttu-id="542cd-158">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="542cd-158">Skype for Business Online (Lync Online)</span></span>

- <span data-ttu-id="542cd-159">SQL データベース</span><span class="sxs-lookup"><span data-stu-id="542cd-159">SQL Databases</span></span>

- <span data-ttu-id="542cd-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="542cd-160">Squawker</span></span>

- <span data-ttu-id="542cd-161">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="542cd-161">Thomson Reuters Eikon Messenger</span></span>

### <a name="archivesocial"></a><span data-ttu-id="542cd-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="542cd-162">ArchiveSocial</span></span>

<span data-ttu-id="542cd-163">[ArchiveSocial は](https://www.archivesocial.com) 、次のサード パーティ製データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="542cd-163">[ArchiveSocial](https://www.archivesocial.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="542cd-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="542cd-164">Facebook</span></span>

- <span data-ttu-id="542cd-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="542cd-165">Flickr</span></span>

- <span data-ttu-id="542cd-166">Instagram</span><span class="sxs-lookup"><span data-stu-id="542cd-166">Instagram</span></span>

- <span data-ttu-id="542cd-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="542cd-167">LinkedIn</span></span>

- <span data-ttu-id="542cd-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="542cd-168">Pinterest</span></span>

- <span data-ttu-id="542cd-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="542cd-169">Twitter</span></span>

- <span data-ttu-id="542cd-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="542cd-170">YouTube</span></span>

- <span data-ttu-id="542cd-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="542cd-171">Vimeo</span></span>

### <a name="veritas"></a><span data-ttu-id="542cd-172">Veritas</span><span class="sxs-lookup"><span data-stu-id="542cd-172">Veritas</span></span>

<span data-ttu-id="542cd-173">[Veritas は](https://www.globanet.com) 、次のサード パーティ製データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="542cd-173">[Veritas](https://www.globanet.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="542cd-174">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="542cd-174">AOL with Pivot Client</span></span>

- <span data-ttu-id="542cd-175">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="542cd-175">BlackBerry Call Logs (v5, v10, v12)</span></span>

- <span data-ttu-id="542cd-176">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="542cd-176">BlackBerry Messenger (v5, v10, v12)</span></span>

- <span data-ttu-id="542cd-177">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="542cd-177">BlackBerry PIN (v5, v10, v12)</span></span>

- <span data-ttu-id="542cd-178">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="542cd-178">BlackBerry SMS (v5, v10, v12)</span></span>

- <span data-ttu-id="542cd-179">Bloomberg チャット</span><span class="sxs-lookup"><span data-stu-id="542cd-179">Bloomberg Chat</span></span>

- <span data-ttu-id="542cd-180">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="542cd-180">Bloomberg Mail</span></span>

- <span data-ttu-id="542cd-181">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="542cd-181">Box</span></span>

- <span data-ttu-id="542cd-182">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="542cd-182">CipherCloud for Salesforce Chatter</span></span>

- <span data-ttu-id="542cd-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="542cd-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="542cd-184">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="542cd-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="542cd-185">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="542cd-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="542cd-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="542cd-186">CrowdCompass</span></span>

- <span data-ttu-id="542cd-187">カスタム区切りテキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="542cd-187">Custom-delimited text files</span></span>

- <span data-ttu-id="542cd-188">カスタムの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="542cd-188">Custom XML files</span></span>

- <span data-ttu-id="542cd-189">Facebook (ページ)</span><span class="sxs-lookup"><span data-stu-id="542cd-189">Facebook (Pages)</span></span>

- <span data-ttu-id="542cd-190">Factset</span><span class="sxs-lookup"><span data-stu-id="542cd-190">Factset</span></span>

- <span data-ttu-id="542cd-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="542cd-191">FXConnect</span></span>

- <span data-ttu-id="542cd-192">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="542cd-192">ICE Chat/YellowJacket</span></span>

- <span data-ttu-id="542cd-193">Jive</span><span class="sxs-lookup"><span data-stu-id="542cd-193">Jive</span></span>

- <span data-ttu-id="542cd-194">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="542cd-194">Macgregor XIP</span></span>

- <span data-ttu-id="542cd-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="542cd-195">Microsoft Exchange Server</span></span>

- <span data-ttu-id="542cd-196">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="542cd-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="542cd-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="542cd-197">Microsoft Teams</span></span>

- <span data-ttu-id="542cd-198">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="542cd-198">Microsoft Yammer</span></span>

- <span data-ttu-id="542cd-199">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="542cd-199">Mobile Guard</span></span>

- <span data-ttu-id="542cd-200">ピボット</span><span class="sxs-lookup"><span data-stu-id="542cd-200">Pivot</span></span>

- <span data-ttu-id="542cd-201">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="542cd-201">Salesforce Chatter</span></span>

- <span data-ttu-id="542cd-202">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="542cd-202">Skype for Business Online</span></span>

- <span data-ttu-id="542cd-203">Skype for Business、バージョン 2007 R2 ～ 2016 (オンプレミス)</span><span class="sxs-lookup"><span data-stu-id="542cd-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>

- <span data-ttu-id="542cd-204">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="542cd-204">Slack Enterprise Grid</span></span>

- <span data-ttu-id="542cd-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="542cd-205">Symphony</span></span>

- <span data-ttu-id="542cd-206">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="542cd-206">Thomson Reuters Eikon</span></span>

- <span data-ttu-id="542cd-207">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="542cd-207">Thomson Reuters Messenger</span></span>

- <span data-ttu-id="542cd-208">Thomson Reuters Dealings 3000 / FX トレーディング</span><span class="sxs-lookup"><span data-stu-id="542cd-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>

- <span data-ttu-id="542cd-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="542cd-209">Twitter</span></span>

- <span data-ttu-id="542cd-210">UBS チャット</span><span class="sxs-lookup"><span data-stu-id="542cd-210">UBS Chat</span></span>

- <span data-ttu-id="542cd-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="542cd-211">YouTube</span></span>

### <a name="opentext"></a><span data-ttu-id="542cd-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="542cd-212">OpenText</span></span>

<span data-ttu-id="542cd-213">[OpenText は](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) 、次のサード パーティ製データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="542cd-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span>

- <span data-ttu-id="542cd-214">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="542cd-214">Axs Encrypted</span></span>

- <span data-ttu-id="542cd-215">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="542cd-215">Axs Exchange</span></span>

- <span data-ttu-id="542cd-216">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="542cd-216">Axs Local Archive</span></span>

- <span data-ttu-id="542cd-217">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="542cd-217">Axs PlaceHolder</span></span>

- <span data-ttu-id="542cd-218">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="542cd-218">Axs Signed</span></span>

- <span data-ttu-id="542cd-219">ブルームバーグ</span><span class="sxs-lookup"><span data-stu-id="542cd-219">Bloomberg</span></span>

- <span data-ttu-id="542cd-220">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="542cd-220">Thomson Reuters</span></span>

### <a name="smarsh"></a><span data-ttu-id="542cd-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="542cd-221">Smarsh</span></span>

<span data-ttu-id="542cd-222">[Smarsh は](https://www.smarsh.com) 、次のサード パーティ製データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="542cd-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="542cd-223">AIM</span><span class="sxs-lookup"><span data-stu-id="542cd-223">AIM</span></span>

- <span data-ttu-id="542cd-224">American Idol</span><span class="sxs-lookup"><span data-stu-id="542cd-224">American Idol</span></span>

- <span data-ttu-id="542cd-225">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="542cd-225">Apple Juice</span></span>

- <span data-ttu-id="542cd-226">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="542cd-226">AOL with Pivot client</span></span>

- <span data-ttu-id="542cd-227">Ares</span><span class="sxs-lookup"><span data-stu-id="542cd-227">Ares</span></span>

- <span data-ttu-id="542cd-228">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="542cd-228">Bazaar Voice</span></span>

- <span data-ttu-id="542cd-229">Bearshare</span><span class="sxs-lookup"><span data-stu-id="542cd-229">Bear Share</span></span>

- <span data-ttu-id="542cd-230">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="542cd-230">Bit Torrent</span></span>

- <span data-ttu-id="542cd-231">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="542cd-231">BlackBerry Call Logs (v5, v10, v12)</span></span>

- <span data-ttu-id="542cd-232">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="542cd-232">BlackBerry Messenger (v5, v10, v12)</span></span>

- <span data-ttu-id="542cd-233">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="542cd-233">BlackBerry PIN (v5, v10, v12)</span></span>

- <span data-ttu-id="542cd-234">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="542cd-234">BlackBerry SMS (v5, v10, v12)</span></span>

- <span data-ttu-id="542cd-235">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="542cd-235">Bloomberg Mail</span></span>

- <span data-ttu-id="542cd-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="542cd-236">CellTrust</span></span>

- <span data-ttu-id="542cd-237">チャットのインポート</span><span class="sxs-lookup"><span data-stu-id="542cd-237">Chat Import</span></span>

- <span data-ttu-id="542cd-238">チャットのリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="542cd-238">Chat Real Time Logging and Policy</span></span>

- <span data-ttu-id="542cd-239">Chatter</span><span class="sxs-lookup"><span data-stu-id="542cd-239">Chatter</span></span>

- <span data-ttu-id="542cd-240">Cisco IM &amp; Presence Server (v9.0.1、v9.1、v9.1.1 SU1、v10、v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="542cd-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>

- <span data-ttu-id="542cd-241">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="542cd-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>

- <span data-ttu-id="542cd-242">共同作業のインポート</span><span class="sxs-lookup"><span data-stu-id="542cd-242">Collaboration Import</span></span>

- <span data-ttu-id="542cd-243">共同作業のリアルタイム ロギング</span><span class="sxs-lookup"><span data-stu-id="542cd-243">Collaboration Real Time Logging</span></span>

- <span data-ttu-id="542cd-244">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="542cd-244">Direct Connect</span></span>

- <span data-ttu-id="542cd-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="542cd-245">Facebook</span></span>

- <span data-ttu-id="542cd-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="542cd-246">FactSet</span></span>

- <span data-ttu-id="542cd-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="542cd-247">FastTrack</span></span>

- <span data-ttu-id="542cd-248">Gnutella</span><span class="sxs-lookup"><span data-stu-id="542cd-248">Gnutella</span></span>

- <span data-ttu-id="542cd-249">Google+</span><span class="sxs-lookup"><span data-stu-id="542cd-249">Google+</span></span>

- <span data-ttu-id="542cd-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="542cd-250">GoToMyPC</span></span>

- <span data-ttu-id="542cd-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="542cd-251">Hopster</span></span>

- <span data-ttu-id="542cd-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="542cd-252">HubConnex</span></span>

- <span data-ttu-id="542cd-253">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)</span><span class="sxs-lookup"><span data-stu-id="542cd-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>

- <span data-ttu-id="542cd-254">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="542cd-254">IBM Connections Chat Cloud</span></span>

- <span data-ttu-id="542cd-255">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="542cd-255">IBM Connections Social Cloud</span></span>

- <span data-ttu-id="542cd-256">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="542cd-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>

- <span data-ttu-id="542cd-257">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="542cd-257">IBM SameTime Communicate 9.0</span></span>

- <span data-ttu-id="542cd-258">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="542cd-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>

- <span data-ttu-id="542cd-259">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="542cd-259">IBM SameTime Complete 9.0</span></span>

- <span data-ttu-id="542cd-260">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="542cd-260">IBM SameTime Conference 9.0</span></span>

- <span data-ttu-id="542cd-261">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="542cd-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>

- <span data-ttu-id="542cd-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="542cd-262">ICE/YellowJacket</span></span>

- <span data-ttu-id="542cd-263">IM のインポート</span><span class="sxs-lookup"><span data-stu-id="542cd-263">IM Import</span></span>

- <span data-ttu-id="542cd-264">IM のリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="542cd-264">IM Real Time Logging and Policy</span></span>

- <span data-ttu-id="542cd-265">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="542cd-265">Indii Messenger</span></span>

- <span data-ttu-id="542cd-266">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="542cd-266">Instant Bloomberg</span></span>

- <span data-ttu-id="542cd-267">IRC</span><span class="sxs-lookup"><span data-stu-id="542cd-267">IRC</span></span>

- <span data-ttu-id="542cd-268">Jive</span><span class="sxs-lookup"><span data-stu-id="542cd-268">Jive</span></span>

- <span data-ttu-id="542cd-269">Jive 6 Real Time Logging (v6、v7)</span><span class="sxs-lookup"><span data-stu-id="542cd-269">Jive 6 Real Time Logging (v6, v7)</span></span>

- <span data-ttu-id="542cd-270">Jive のインポート</span><span class="sxs-lookup"><span data-stu-id="542cd-270">Jive Import</span></span>

- <span data-ttu-id="542cd-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="542cd-271">JXTA</span></span>

- <span data-ttu-id="542cd-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="542cd-272">LinkedIn</span></span>

- <span data-ttu-id="542cd-273">Microsoft Lync (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="542cd-273">Microsoft Lync (2010, 2013)</span></span>

- <span data-ttu-id="542cd-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="542cd-274">MFTP</span></span>

- <span data-ttu-id="542cd-275">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="542cd-275">Microsoft Lync 2013 Voice</span></span>

- <span data-ttu-id="542cd-276">Microsoft SharePoint (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="542cd-276">Microsoft SharePoint (2010, 2013)</span></span>

- <span data-ttu-id="542cd-277">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="542cd-277">Microsoft SharePoint Online</span></span>

- <span data-ttu-id="542cd-278">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="542cd-278">Microsoft UC (Unified Communications)</span></span>

- <span data-ttu-id="542cd-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="542cd-279">MindAlign</span></span>

- <span data-ttu-id="542cd-280">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="542cd-280">Mobile Guard</span></span>

- <span data-ttu-id="542cd-281">MSN</span><span class="sxs-lookup"><span data-stu-id="542cd-281">MSN</span></span>

- <span data-ttu-id="542cd-282">My Space</span><span class="sxs-lookup"><span data-stu-id="542cd-282">My Space</span></span>

- <span data-ttu-id="542cd-283">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="542cd-283">NEONetwork</span></span>

- <span data-ttu-id="542cd-284">Microsoft 365Lync 専用</span><span class="sxs-lookup"><span data-stu-id="542cd-284">Microsoft 365 Lync Dedicated</span></span>

- <span data-ttu-id="542cd-285">Microsoft 365共有 IM</span><span class="sxs-lookup"><span data-stu-id="542cd-285">Microsoft 365 Shared IM</span></span>

- <span data-ttu-id="542cd-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="542cd-286">Pinterest</span></span>

- <span data-ttu-id="542cd-287">ピボット</span><span class="sxs-lookup"><span data-stu-id="542cd-287">Pivot</span></span>

- <span data-ttu-id="542cd-288">QQ</span><span class="sxs-lookup"><span data-stu-id="542cd-288">QQ</span></span>

- <span data-ttu-id="542cd-289">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="542cd-289">Skype for Business 2015</span></span>

- <span data-ttu-id="542cd-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="542cd-290">SoftEther</span></span>

- <span data-ttu-id="542cd-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="542cd-291">Symphony</span></span>

- <span data-ttu-id="542cd-292">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="542cd-292">Thomson Reuters Eikon</span></span>

- <span data-ttu-id="542cd-293">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="542cd-293">Thomson Reuters Messenger</span></span>

- <span data-ttu-id="542cd-294">Tor</span><span class="sxs-lookup"><span data-stu-id="542cd-294">Tor</span></span>

- <span data-ttu-id="542cd-295">TTT</span><span class="sxs-lookup"><span data-stu-id="542cd-295">TTT</span></span>

- <span data-ttu-id="542cd-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="542cd-296">Twitter</span></span>

- <span data-ttu-id="542cd-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="542cd-297">WinMX</span></span>

- <span data-ttu-id="542cd-298">Winny</span><span class="sxs-lookup"><span data-stu-id="542cd-298">Winny</span></span>

- <span data-ttu-id="542cd-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="542cd-299">Yahoo</span></span>

- <span data-ttu-id="542cd-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="542cd-300">Yammer</span></span>

- <span data-ttu-id="542cd-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="542cd-301">YouTube</span></span>


### <a name="verba"></a><span data-ttu-id="542cd-302">Verba</span><span class="sxs-lookup"><span data-stu-id="542cd-302">Verba</span></span>

<span data-ttu-id="542cd-303">[Verba](https://www.verba.com) は、次のサード パーティ製データ ソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="542cd-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span>

- <span data-ttu-id="542cd-304">Avaya Aura ビデオ</span><span class="sxs-lookup"><span data-stu-id="542cd-304">Avaya Aura Video</span></span>

- <span data-ttu-id="542cd-305">Avaya Aura 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-305">Avaya Aura Voice</span></span>

- <span data-ttu-id="542cd-306">Avtec ラジオ</span><span class="sxs-lookup"><span data-stu-id="542cd-306">Avtec Radio</span></span>

- <span data-ttu-id="542cd-307">Bosch/Telex ラジオ</span><span class="sxs-lookup"><span data-stu-id="542cd-307">Bosch/Telex Radio</span></span>

- <span data-ttu-id="542cd-308">BroadSoft ビデオ</span><span class="sxs-lookup"><span data-stu-id="542cd-308">BroadSoft Video</span></span>

- <span data-ttu-id="542cd-309">BroadSoft 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-309">BroadSoft Voice</span></span>

- <span data-ttu-id="542cd-310">Centile 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-310">Centile Voice</span></span>

- <span data-ttu-id="542cd-311">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="542cd-311">Cisco Jabber IM</span></span>

- <span data-ttu-id="542cd-312">Cisco UC ビデオ</span><span class="sxs-lookup"><span data-stu-id="542cd-312">Cisco UC Video</span></span>

- <span data-ttu-id="542cd-313">Cisco UC 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-313">Cisco UC Voice</span></span>

- <span data-ttu-id="542cd-314">Cisco UCCX/UCCE ビデオ</span><span class="sxs-lookup"><span data-stu-id="542cd-314">Cisco UCCX/UCCE Video</span></span>

- <span data-ttu-id="542cd-315">Cisco UCCX/UCCE Voice</span><span class="sxs-lookup"><span data-stu-id="542cd-315">Cisco UCCX/UCCE Voice</span></span>

- <span data-ttu-id="542cd-316">ESChat ラジオ</span><span class="sxs-lookup"><span data-stu-id="542cd-316">ESChat Radio</span></span>

- <span data-ttu-id="542cd-317">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="542cd-317">Geoman Contact Expert</span></span>

- <span data-ttu-id="542cd-318">IP Trade 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-318">IP Trade Voice</span></span>

- <span data-ttu-id="542cd-319">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="542cd-319">Luware LUCS Contact Center</span></span>

- <span data-ttu-id="542cd-320">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="542cd-320">Microsoft UC (Unified Communications)</span></span>

- <span data-ttu-id="542cd-321">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="542cd-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>

- <span data-ttu-id="542cd-322">Oracle / Acme Packet Session Border Controller ビデオ</span><span class="sxs-lookup"><span data-stu-id="542cd-322">Oracle / Acme Packet Session Border Controller Video</span></span>

- <span data-ttu-id="542cd-323">Oracle / Acme Packet Session Border Controller 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-323">Oracle / Acme Packet Session Border Controller Voice</span></span>

- <span data-ttu-id="542cd-324">Singtel モバイル ボイス</span><span class="sxs-lookup"><span data-stu-id="542cd-324">Singtel Mobile Voice</span></span>

- <span data-ttu-id="542cd-325">SIPREC ビデオ</span><span class="sxs-lookup"><span data-stu-id="542cd-325">SIPREC Video</span></span>

-  <span data-ttu-id="542cd-326">SIPREC 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-326">SIPREC Voice</span></span>

- <span data-ttu-id="542cd-327">Skype for Business / Lync IM</span><span class="sxs-lookup"><span data-stu-id="542cd-327">Skype for Business / Lync IM</span></span>

- <span data-ttu-id="542cd-328">Skype for Business / Lync ビデオ</span><span class="sxs-lookup"><span data-stu-id="542cd-328">Skype for Business / Lync Video</span></span>

- <span data-ttu-id="542cd-329">Skype for Business / Lync 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-329">Skype for Business / Lync Voice</span></span>

- <span data-ttu-id="542cd-330">Speakerbus 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-330">Speakerbus Voice</span></span>

- <span data-ttu-id="542cd-331">標準的な SIP/H.323 ビデオ</span><span class="sxs-lookup"><span data-stu-id="542cd-331">Standard SIP/H.323 Video</span></span>

- <span data-ttu-id="542cd-332">標準的な SIP/H.323 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-332">Standard SIP/H.323 Voice</span></span>

- <span data-ttu-id="542cd-333">Truphone 音声</span><span class="sxs-lookup"><span data-stu-id="542cd-333">Truphone Voice</span></span>

- <span data-ttu-id="542cd-334">TwistedPair ラジオ</span><span class="sxs-lookup"><span data-stu-id="542cd-334">TwistedPair Radio</span></span>

- <span data-ttu-id="542cd-335">Windows デスクトップ コンピューターの画面</span><span class="sxs-lookup"><span data-stu-id="542cd-335">Windows Desktop Computer Screen</span></span>

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="542cd-336">手順 2: サード パーティ製のデータ メールボックスを作成して構成Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="542cd-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="542cd-337">データを外部にインポートするためのサード パーティ製のデータ メールボックスを作成および構成する手順をMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="542cd-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="542cd-338">前に説明したように、パートナー コネクタがアイテムのユーザー ID をユーザー アカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="542cd-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>

 <span data-ttu-id="542cd-339">**これらのタスクは、次の手順で実行Microsoft 365 管理センター**</span><span class="sxs-lookup"><span data-stu-id="542cd-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>

1. <span data-ttu-id="542cd-340">ユーザー アカウントを作成し、プラン 2 ライセンスExchange Online割り当てる。「ユーザー[をユーザーに追加する」をMicrosoft 365。](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="542cd-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](../admin/add-users/add-users.md).</span></span> <span data-ttu-id="542cd-341">訴訟ホールドにメールボックスを配置するか、無制限の記憶域クォータを持つアーカイブ メールボックスを有効にするには、プラン 2 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="542cd-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>

2. <span data-ttu-id="542cd-342">サード パーティのデータ メールボックスのユーザー アカウントを、管理者の管理者Exchange役割に追加Microsoft 365。「管理者[ロールの割り当て」を参照Microsoft 365。](../admin/add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="542cd-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](../admin/add-users/assign-admin-roles.md).</span></span>

    > [!TIP]
    > <span data-ttu-id="542cd-p109">このユーザー アカウントの資格情報を控えておきます。手順 4 で説明するように、この情報をパートナーに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="542cd-p109">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span>

 <span data-ttu-id="542cd-345">**管理センターでこれらのタスクExchange実行する**</span><span class="sxs-lookup"><span data-stu-id="542cd-345">**Complete these tasks in the Exchange admin center**</span></span>

1. <span data-ttu-id="542cd-346">組織内のアドレス帳や他のアドレス一覧からサード パーティのデータ メールボックスを非表示にします。「ユーザー [メールボックスの管理」を参照してください](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="542cd-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span> <span data-ttu-id="542cd-347">または、次の PowerShell コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="542cd-347">Alternatively, you can run the following PowerShell command:</span></span>

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="542cd-348">管理者またはコンプライアンス担当者がデスクトップ クライアントでサード パーティのデータ メールボックスを開くことができるので、サード パーティのデータ メールボックスに **FullAccess** アクセス許可を割り当Outlookします。「受信者 [のアクセス許可の管理」を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=692104)。</span><span class="sxs-lookup"><span data-stu-id="542cd-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>

3. <span data-ttu-id="542cd-349">サード パーティのデータ メールボックスに対して、次のコンプライアンス関連の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="542cd-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>

    - <span data-ttu-id="542cd-350">アーカイブ メールボックスを有効にします。「アーカイブ[メールボックスを有効にする」および「](enable-archive-mailboxes.md)[無制限のアーカイブを有効にする」を参照してください](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="542cd-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="542cd-351">これにより、サード パーティのデータ アイテムをアーカイブ メールボックスに移動するアーカイブ ポリシーを設定することで、プライマリ メールボックスの記憶域を解放できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="542cd-352">これにより、サードパーティのデータに対する無制限のストレージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-352">This provides you with unlimited storage for third-party data.</span></span>

    - <span data-ttu-id="542cd-353">サードパーティ データのメールボックスを訴訟ホールドの対象にします。</span><span class="sxs-lookup"><span data-stu-id="542cd-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="542cd-354">セキュリティとコンプライアンス センター Microsoft 365保持ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="542cd-355">このメールボックスを保留に設定すると、サード パーティのデータ アイテム (無期限または指定された期間) が保持され、メールボックスから削除されません。</span><span class="sxs-lookup"><span data-stu-id="542cd-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="542cd-356">次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="542cd-356">See one of the following topics:</span></span>

      - [<span data-ttu-id="542cd-357">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="542cd-357">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)

      - [<span data-ttu-id="542cd-358">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="542cd-358">Learn about retention policies and retention labels</span></span>](retention.md)

    - <span data-ttu-id="542cd-359">所有者、代理人、および第三者データ メールボックスへの管理者アクセスのメールボックス監査ログを有効にします。「 [メールボックス監査を有効にする」を参照してください](enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="542cd-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="542cd-360">これにより、サード パーティのデータ メールボックスにアクセスできるすべてのユーザーが実行するアクティビティを監査できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="542cd-361">手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="542cd-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="542cd-362">次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="542cd-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="542cd-363">これらのタスクは、管理センター Exchange、または対応するコマンドレットを使用してWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="542cd-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>

1. <span data-ttu-id="542cd-364">各ユーザーのアーカイブ メールボックスを有効にします。「アーカイブ[メールボックスを有効にする」および「](enable-archive-mailboxes.md)[無制限のアーカイブを有効にする」を参照してください](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="542cd-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

2. <span data-ttu-id="542cd-365">ユーザー メールボックスを訴訟ホールドに配置するか、ユーザー保持ポリシー Microsoft 365適用します。次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="542cd-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span>

    - [<span data-ttu-id="542cd-366">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="542cd-366">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)

    - [<span data-ttu-id="542cd-367">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="542cd-367">Learn about retention policies and retention labels</span></span>](retention.md)

    <span data-ttu-id="542cd-368">前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="542cd-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="542cd-369">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="542cd-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="542cd-370">最後の手順は、パートナーに次の情報を提供し、ユーザー のメールボックスとサード パーティのデータ メールボックスにデータをインポートするために、組織に接続するためのコネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="542cd-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span>

- <span data-ttu-id="542cd-371">Azure サービスへの接続に使用するエンドポイントは、次Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="542cd-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="542cd-372">手順 2 で作成Microsoft 365サード パーティ製のデータ メールボックスのサインイン資格情報 (ユーザー ID とパスワードを含む)。</span><span class="sxs-lookup"><span data-stu-id="542cd-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="542cd-373">パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="542cd-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="542cd-374">手順 5: サード パーティ製のデータ コネクタをデバイスに登録Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="542cd-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="542cd-375">2018 年 9 月 30 日から、Microsoft 365 の Azure サービスは Exchange Online で最新の認証を使用して、組織に接続してデータをインポートしようとするサードパーティのデータ コネクタの認証を開始します。</span><span class="sxs-lookup"><span data-stu-id="542cd-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="542cd-376">この変更の理由は、最新の認証は、前述のエンドポイントを使用して Azure サービスに接続するサード パーティ製コネクタの許可リストに基づいて、現在のメソッドよりもセキュリティが高いという点です。</span><span class="sxs-lookup"><span data-stu-id="542cd-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="542cd-377">新しい最新の認証方法を使用してサード パーティ製のデータ コネクタが Microsoft 365 に接続するには、組織内の管理者がコネクタを Azure Active Directory で信頼できるサービス アプリケーションとして登録する同意が必要です。</span><span class="sxs-lookup"><span data-stu-id="542cd-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="542cd-378">これは、アクセス許可要求を受け入れて、コネクタが組織内の組織のデータにアクセスAzure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="542cd-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="542cd-379">この要求を受け入れると、サード パーティ製のデータ コネクタがエンタープライズ アプリケーションとして Azure Active Directoryサービス プリンシパルとして表されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="542cd-380">同意プロセスの詳細については、「テナント管理者の同意  [」を参照してください](/skype-sdk/trusted-application-api/docs/tenantadminconsent)。</span><span class="sxs-lookup"><span data-stu-id="542cd-380">For more information the consent process, see  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="542cd-381">コネクタの登録要求にアクセスして承諾する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="542cd-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="542cd-382">このページ [に移動し](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 、グローバル管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="542cd-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="542cd-383">次のダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-383">The following dialog box is displayed.</span></span> <span data-ttu-id="542cd-384">キャレットを展開して、コネクタに割り当てられるアクセス許可を確認できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![アクセス許可要求ダイアログが表示されます](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="542cd-386">[**Accept**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="542cd-386">Click **Accept**.</span></span>

<span data-ttu-id="542cd-387">要求に同意すると [、Azure ポータルが](https://portal.azure.com) 表示されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="542cd-388">組織のアプリケーションの一覧を表示するには、[アプリケーション]をクリック  >  **Azure Active Directory Enterpriseクリックします**。</span><span class="sxs-lookup"><span data-stu-id="542cd-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="542cd-389">サード Microsoft 365 データ コネクタの一覧は、[アプリケーション] ブレードEnterprise **一覧表示** されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="542cd-390">2018 年 9 月 30 日以降、サード パーティ製データ コネクタを Azure Active Directory に登録しない場合、サードパーティのデータは組織内のメールボックスにインポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="542cd-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="542cd-391">既存のサード パーティ製データ コネクタ (2018 年 9 月 30 日より前に作成されたコネクタ) も、手順 5 の手順に従って Azure Active Directory に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="542cd-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="542cd-392">サード パーティ製データ コネクタに対する同意の取り下</span><span class="sxs-lookup"><span data-stu-id="542cd-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="542cd-393">組織が Azure Active Directory にサード パーティのデータ コネクタを登録するためのアクセス許可要求に同意した後、組織はいつでもその同意を取り消す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="542cd-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="542cd-394">ただし、コネクタの同意を取り戻すということは、サード パーティ製のデータ ソースからのデータがデータ ソースにインポートされなくなるMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="542cd-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="542cd-395">サード パーティのデータ コネクタの同意を取り消す場合は、Azure portal の **Enterprise** アプリケーション ブレードを使用するか、Microsoft 365 PowerShell の [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal)を使用して、Azure Active Directory から (対応するサービス プリンシパルを削除して) アプリケーションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="542cd-396">また、PowerShell で[Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal)コマンドレットAzure Active Directoryできます。</span><span class="sxs-lookup"><span data-stu-id="542cd-396">You can also use the [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>

## <a name="more-information"></a><span data-ttu-id="542cd-397">詳細</span><span class="sxs-lookup"><span data-stu-id="542cd-397">More information</span></span>

- <span data-ttu-id="542cd-398">前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="542cd-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="542cd-399">パートナー コネクタは、API で必要なスキーマを使用してアイテムMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="542cd-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="542cd-400">次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="542cd-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="542cd-401">この表では、メッセージのプロパティが必須かどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="542cd-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="542cd-402">必須プロパティは設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="542cd-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="542cd-403">アイテムに必須プロパティが存在しない場合、アイテムは必須プロパティにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="542cd-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="542cd-404">インポート プロセスは、アイテムがインポートされていない理由と、不足しているプロパティを説明するエラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="542cd-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>

    |<span data-ttu-id="542cd-405">**メッセージのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="542cd-405">**Message property**</span></span>|<span data-ttu-id="542cd-406">**必須かどうか?**</span><span class="sxs-lookup"><span data-stu-id="542cd-406">**Mandatory?**</span></span>|<span data-ttu-id="542cd-407">**説明**</span><span class="sxs-lookup"><span data-stu-id="542cd-407">**Description**</span></span>|<span data-ttu-id="542cd-408">**値の例**</span><span class="sxs-lookup"><span data-stu-id="542cd-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="542cd-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="542cd-409">**FROM**</span></span> <br/> |<span data-ttu-id="542cd-410">はい</span><span class="sxs-lookup"><span data-stu-id="542cd-410">Yes</span></span>  <br/> |<span data-ttu-id="542cd-411">最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="542cd-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="542cd-412">パートナー コネクタは、ソース アイテム (Twitter ハンドルなど) からすべての参加者 (FROM フィールドと TO フィールドのユーザー) のユーザー アカウントにユーザー ID をマップします。</span><span class="sxs-lookup"><span data-stu-id="542cd-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="542cd-413">メッセージのコピーが、すべての参加者のメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="542cd-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="542cd-414">アイテムの参加者のいずれもユーザー アカウントにマップしない場合、アイテムはユーザー アカウント内のサード パーティのアーカイブ メールボックスにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="542cd-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="542cd-415">アイテムの送信者として識別される参加者は、アイテムのインポート先である組織内のアクティブなメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="542cd-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="542cd-416">送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="542cd-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="542cd-417">**TO**</span></span> <br/> |<span data-ttu-id="542cd-418">はい</span><span class="sxs-lookup"><span data-stu-id="542cd-418">Yes</span></span>  <br/> |<span data-ttu-id="542cd-419">アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="542cd-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="542cd-420">**件名**</span><span class="sxs-lookup"><span data-stu-id="542cd-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="542cd-421">いいえ</span><span class="sxs-lookup"><span data-stu-id="542cd-421">No</span></span>  <br/> |<span data-ttu-id="542cd-422">ソース アイテムの件名。</span><span class="sxs-lookup"><span data-stu-id="542cd-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="542cd-423">**DATE**</span><span class="sxs-lookup"><span data-stu-id="542cd-423">**DATE**</span></span> <br/> |<span data-ttu-id="542cd-424">はい</span><span class="sxs-lookup"><span data-stu-id="542cd-424">Yes</span></span>  <br/> |<span data-ttu-id="542cd-425">アイテムが最初に作成または顧客データ ソースに投稿された日付。</span><span class="sxs-lookup"><span data-stu-id="542cd-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="542cd-426">たとえば、Twitter メッセージがツイートされた日付です。</span><span class="sxs-lookup"><span data-stu-id="542cd-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="542cd-427">**BODY**</span><span class="sxs-lookup"><span data-stu-id="542cd-427">**BODY**</span></span> <br/> |<span data-ttu-id="542cd-428">いいえ</span><span class="sxs-lookup"><span data-stu-id="542cd-428">No</span></span>  <br/> |<span data-ttu-id="542cd-429">メッセージまたは投稿のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="542cd-429">The contents of the message or post.</span></span> <span data-ttu-id="542cd-430">一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。</span><span class="sxs-lookup"><span data-stu-id="542cd-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="542cd-431">インポート プロセス中、パートナー コネクタはコンテンツ ソースからの完全な忠実度を可能な限り維持します。</span><span class="sxs-lookup"><span data-stu-id="542cd-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="542cd-432">可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="542cd-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="542cd-433">それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="542cd-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="542cd-434">このプロパティの内容は、パートナー コネクタとソース プラットフォームの機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="542cd-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="542cd-435">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="542cd-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="542cd-436">いいえ</span><span class="sxs-lookup"><span data-stu-id="542cd-436">No</span></span>  <br/> |<span data-ttu-id="542cd-437">データ ソース内のアイテム (Twitter でのツイートやインスタント メッセージング会話など) に添付ファイルまたは画像が含まれる場合、パートナー接続はまず **BODY** プロパティに添付ファイルを含める試みを行います。</span><span class="sxs-lookup"><span data-stu-id="542cd-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="542cd-438">それができない場合は、 \*\* ATTACHMENT \*\* プロパティに追加されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="542cd-439">添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。</span><span class="sxs-lookup"><span data-stu-id="542cd-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="542cd-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="542cd-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="542cd-441">はい</span><span class="sxs-lookup"><span data-stu-id="542cd-441">Yes</span></span>  <br/> | <span data-ttu-id="542cd-442">これは複数値のプロパティで、パートナー コネクタによって作成および設定されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="542cd-443">このプロパティの形式はです  `IPM.NOTE.Source.Event` 。</span><span class="sxs-lookup"><span data-stu-id="542cd-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="542cd-444">(このプロパティはで始まる必要があります  `IPM.NOTE` 。</span><span class="sxs-lookup"><span data-stu-id="542cd-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="542cd-445">この形式は、メッセージ クラスの形式と  `IPM.NOTE.X` 似ています)。このプロパティには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="542cd-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="542cd-446">`Source`: サードパーティのデータ ソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。</span><span class="sxs-lookup"><span data-stu-id="542cd-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="542cd-447">`Event`: アイテムを生成したサードパーティのデータ ソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイートや Facebook の投稿などです。</span><span class="sxs-lookup"><span data-stu-id="542cd-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="542cd-448">イベントはデータ ソースに固有です。</span><span class="sxs-lookup"><span data-stu-id="542cd-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="542cd-449">このプロパティの目的の 1 つは、アイテムが発生したデータ ソースに基づいて、またはイベントの種類に基づいて特定のアイテムをフィルター処理することです。</span><span class="sxs-lookup"><span data-stu-id="542cd-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="542cd-450">たとえば、電子情報開示検索で検索クエリを作成して、特定のユーザーが投稿したツイートを検索できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- <span data-ttu-id="542cd-451">アイテムが Microsoft 365 内のメールボックスに正常にインポートされると、HTTP 応答の一部として一意の識別子が呼び出し元に返されます。</span><span class="sxs-lookup"><span data-stu-id="542cd-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="542cd-452">この識別子 (呼び出し) は、アイテムのエンドツーエンドの追跡のためにパートナーが後続のトラブルシューティングの目的  `x-IngestionCorrelationID` で使用できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="542cd-453">パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="542cd-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="542cd-454">この識別子を示す HTTP 応答の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="542cd-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT
    ```

- <span data-ttu-id="542cd-455">セキュリティとコンプライアンス センターのコンテンツ検索ツールを使用して、サード パーティのデータ ソースからメールボックスにインポートされたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="542cd-456">これらのインポートされたアイテムを具体的に検索するには、コンテンツ検索のキーワード ボックスで次のメッセージ プロパティと値のペアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="542cd-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>

  - <span data-ttu-id="542cd-457">**`kind:externaldata`**: このプロパティと値のペアを使用して、すべてのサード パーティのデータ型を検索します。</span><span class="sxs-lookup"><span data-stu-id="542cd-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="542cd-458">たとえば、サードパーティのデータ ソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、キーワード クエリを使用します  `kind:externaldata AND subject:contoso` 。</span><span class="sxs-lookup"><span data-stu-id="542cd-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>

  - <span data-ttu-id="542cd-459">**`itemclass:ipm.externaldata.<third-party data type>`**: このプロパティと値のペアを使用して、指定した種類のサード パーティデータのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="542cd-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="542cd-460">たとえば、Subject プロパティの "contoso" という単語を含む Facebook データのみを検索するには、キーワード クエリを使用します  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 。</span><span class="sxs-lookup"><span data-stu-id="542cd-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span>

  <span data-ttu-id="542cd-461">プロパティのサード パーティのデータ型に使用する値の完全な一覧については、「コンテンツ検索を使用して、このプロパティにインポートされたサード パーティのデータを検索する」 `itemclass` [を参照Microsoft 365。](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="542cd-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>

   <span data-ttu-id="542cd-462">コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="542cd-462">For more information about using Content Search and creating keyword search queries, see:</span></span>

  - [<span data-ttu-id="542cd-463">コンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="542cd-463">Content Search</span></span>](content-search.md)

  - [<span data-ttu-id="542cd-464">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="542cd-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)