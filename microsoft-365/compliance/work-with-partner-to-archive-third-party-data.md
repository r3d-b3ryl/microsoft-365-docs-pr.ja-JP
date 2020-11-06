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
description: カスタムコネクタをセットアップして、Salesforce チャター、Yahoo Messenger、Yammer などのデータソースからサードパーティのデータをインポートする方法について説明します。
ms.openlocfilehash: 97e36566c3dcc9b069a39eb50e203cda971ba3c2
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931949"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="49a99-103">パートナーと共同作業して、サード パーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="49a99-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="49a99-104">Microsoft パートナーと協力して、サードパーティのデータソースから Microsoft 365 にデータをインポートしてアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="49a99-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="49a99-105">パートナーは、サードパーティのデータソースからアイテムを抽出するように構成されたカスタムコネクタ (定期的に) を提供して、それらのアイテムをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="49a99-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="49a99-106">パートナーコネクタは、アイテムのコンテンツをデータソースから電子メールメッセージ形式に変換し、そのアイテムをメールボックスに格納します。</span><span class="sxs-lookup"><span data-stu-id="49a99-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="49a99-107">サードパーティのデータがインポートされたら、訴訟ホールド、電子情報開示、In-Place アーカイブ、監査、Microsoft 365 のアイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能をこのデータに適用できます。</span><span class="sxs-lookup"><span data-stu-id="49a99-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>
 
>[!IMPORTANT]
><span data-ttu-id="49a99-108">Microsoft 365 の [通信コンプライアンス](communication-compliance.md) ソリューションは、この記事で説明されているパートナーコネクタによってインポートされたサードパーティのデータには適用できません。</span><span class="sxs-lookup"><span data-stu-id="49a99-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span> 
 
<span data-ttu-id="49a99-109">ここでは、サードパーティのデータをインポートするために Microsoft パートナーと連携するために必要なプロセスと手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="49a99-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="49a99-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="49a99-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="49a99-111">手順 2: サードパーティのデータメールボックスを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="49a99-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="49a99-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="49a99-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="49a99-113">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="49a99-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="49a99-114">手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する</span><span class="sxs-lookup"><span data-stu-id="49a99-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="49a99-115">サードパーティのデータのインポート プロセスが実行される方法</span><span class="sxs-lookup"><span data-stu-id="49a99-115">How the third-party data import process works</span></span>

<span data-ttu-id="49a99-116">次の図と説明は、パートナーと連携している場合にサードパーティのデータインポートプロセスがどのように動作するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="49a99-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![サードパーティのデータのインポート プロセスが実行される方法](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="49a99-118">お客様は、選択したパートナーと連携して、サードパーティのデータソースからアイテムを抽出し、それらのアイテムを Microsoft 365 にインポートするコネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="49a99-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="49a99-119">パートナーコネクタは、サードパーティの API を使用してサードパーティのデータソースに接続し (スケジュールに従って、または構成されている場合)、データソースからアイテムを抽出します。</span><span class="sxs-lookup"><span data-stu-id="49a99-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="49a99-120">パートナー コネクタは、アイテムのコンテンツを電子メール メッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="49a99-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="49a99-121">メッセージ形式スキーマの詳細については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="49a99-122">パートナーコネクタは、既知のエンドポイントを介して Exchange Web サービス (EWS) を使用して、Microsoft 365 の Azure サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="49a99-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="49a99-p103">アイテムは特定のユーザーのメールボックスまたは "catch-all" というサードパーティ データのメールボックスにインポートされます。アイテムが特定のユーザーのメールボックスにインポートされるか、またはサードパーティ データのメールボックスにインポートされるかは、以下の条件に基づきます。</span><span class="sxs-lookup"><span data-stu-id="49a99-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="49a99-125">ユーザー **アカウントに対応するユーザー ID を持つアイテム:** パートナーコネクタがサードパーティのデータソース内のアイテムのユーザー ID を Office 365 の特定のユーザー ID にマップできる場合、そのアイテムはユーザーの [回復可能なアイテム] フォルダー **内の [削除] フォルダーに** コピーされます。</span><span class="sxs-lookup"><span data-stu-id="49a99-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="49a99-126">ユーザーがパージフォルダー内のアイテムにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="49a99-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="49a99-127">ただし、電子情報開示ツールを使用して、[削除] フォルダー内のアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="49a99-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="49a99-128">ユーザー **アカウントに対応するユーザー ID を持たないアイテム:** パートナーコネクタがアイテムのユーザー ID を特定のユーザー ID にマップできない場合、そのアイテムはサードパーティのデータメールボックスの **受信トレイ** フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="49a99-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="49a99-129">受信トレイにアイテムをインポートすると、組織内のユーザーがサードパーティのメールボックスにサインインしてこれらのアイテムを表示および管理できるようになります。また、パートナーコネクタ構成で調整が必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="49a99-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="49a99-130">手順 1: サード パーティのデータのパートナーを見つける</span><span class="sxs-lookup"><span data-stu-id="49a99-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="49a99-131">Microsoft 365 でサードパーティのデータをアーカイブするための主要なコンポーネントは、サードパーティのデータソースからデータを取得して Office 365 にインポートすることに特化した Microsoft パートナーを検索して作業することです。</span><span class="sxs-lookup"><span data-stu-id="49a99-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="49a99-132">インポートされたデータは、組織の他の Microsoft データ (Exchange からの電子メールや SharePoint および OneDrive for business からのメールなど) と共にアーカイブおよび保存することができます。</span><span class="sxs-lookup"><span data-stu-id="49a99-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="49a99-133">パートナーは、組織のサードパーティのデータソース (BlackBerry、Facebook、Google +、Thomson Reuters、Twitter、YouTube など) からデータを抽出し、そのデータを電子メールメッセージとして Exchange メールボックスにインポートする Office 365 API に渡すコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="49a99-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="49a99-134">次のセクションでは、Office 365 でサードパーティのデータをアーカイブするためにプログラムに参加している Microsoft パートナー (およびサポートされているサードパーティのデータソース) を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="49a99-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="49a99-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="49a99-135">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="49a99-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="49a99-136">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="49a99-137">Globanet</span><span class="sxs-lookup"><span data-stu-id="49a99-137">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="49a99-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="49a99-138">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="49a99-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="49a99-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="49a99-140">Verba</span><span class="sxs-lookup"><span data-stu-id="49a99-140">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="49a99-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="49a99-141">17a-4 LLC</span></span>

<span data-ttu-id="49a99-142">[17a-4 で](https://www.17a-4.com) は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="49a99-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="49a99-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="49a99-143">BlackBerry</span></span>
    
- <span data-ttu-id="49a99-144">Bloomberg データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="49a99-144">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="49a99-145">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="49a99-145">Cisco Jabber</span></span>
    
- <span data-ttu-id="49a99-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="49a99-146">FactSet</span></span>
    
- <span data-ttu-id="49a99-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="49a99-147">HipChat</span></span>
    
- <span data-ttu-id="49a99-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="49a99-148">InvestEdge</span></span>
    
- <span data-ttu-id="49a99-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="49a99-149">LivePerson</span></span>
    
- <span data-ttu-id="49a99-150">MessageLabs データ ストリーム</span><span class="sxs-lookup"><span data-stu-id="49a99-150">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="49a99-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="49a99-151">OpenText</span></span>
    
- <span data-ttu-id="49a99-152">Oracle/ATG 'click-to-call' Live ヘルプ</span><span class="sxs-lookup"><span data-stu-id="49a99-152">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="49a99-153">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="49a99-153">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="49a99-154">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="49a99-154">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="49a99-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="49a99-155">MindAlign</span></span>
    
- <span data-ttu-id="49a99-156">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="49a99-156">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="49a99-157">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="49a99-157">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="49a99-158">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="49a99-158">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="49a99-159">SQL データベース</span><span class="sxs-lookup"><span data-stu-id="49a99-159">SQL Databases</span></span>
    
- <span data-ttu-id="49a99-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="49a99-160">Squawker</span></span>
    
- <span data-ttu-id="49a99-161">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="49a99-161">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="49a99-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="49a99-162">ArchiveSocial</span></span>

<span data-ttu-id="49a99-163">[ArchiveSocial ](https://www.archivesocial.com) は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="49a99-163">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="49a99-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="49a99-164">Facebook</span></span>
    
- <span data-ttu-id="49a99-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="49a99-165">Flickr</span></span>
    
- <span data-ttu-id="49a99-166">Instagram</span><span class="sxs-lookup"><span data-stu-id="49a99-166">Instagram</span></span>
    
- <span data-ttu-id="49a99-167">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="49a99-167">LinkedIn</span></span>
    
- <span data-ttu-id="49a99-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="49a99-168">Pinterest</span></span>
    
- <span data-ttu-id="49a99-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="49a99-169">Twitter</span></span>
    
- <span data-ttu-id="49a99-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="49a99-170">YouTube</span></span>
    
- <span data-ttu-id="49a99-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="49a99-171">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="49a99-172">Globanet</span><span class="sxs-lookup"><span data-stu-id="49a99-172">Globanet</span></span>

<span data-ttu-id="49a99-173">[Globanet](https://www.globanet.com) は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="49a99-173">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="49a99-174">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="49a99-174">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="49a99-175">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="49a99-175">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="49a99-176">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="49a99-176">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="49a99-177">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="49a99-177">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="49a99-178">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="49a99-178">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="49a99-179">Bloomberg チャット</span><span class="sxs-lookup"><span data-stu-id="49a99-179">Bloomberg Chat</span></span>
    
- <span data-ttu-id="49a99-180">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="49a99-180">Bloomberg Mail</span></span>
    
- <span data-ttu-id="49a99-181">検索ボックス</span><span class="sxs-lookup"><span data-stu-id="49a99-181">Box</span></span>
    
- <span data-ttu-id="49a99-182">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="49a99-182">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="49a99-183">Cisco IM &amp; プレゼンスサーバー (v10、v V10.5.1 SU1、v 11.0、v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="49a99-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="49a99-184">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="49a99-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="49a99-185">Citrix ワークスペースの編集 &amp; ファイル</span><span class="sxs-lookup"><span data-stu-id="49a99-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="49a99-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="49a99-186">CrowdCompass</span></span>

- <span data-ttu-id="49a99-187">カスタム区切りのテキストファイル</span><span class="sxs-lookup"><span data-stu-id="49a99-187">Custom-delimited text files</span></span>
    
- <span data-ttu-id="49a99-188">カスタムの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="49a99-188">Custom XML files</span></span>
    
- <span data-ttu-id="49a99-189">Facebook (ページ)</span><span class="sxs-lookup"><span data-stu-id="49a99-189">Facebook (Pages)</span></span>
    
- <span data-ttu-id="49a99-190">Factset</span><span class="sxs-lookup"><span data-stu-id="49a99-190">Factset</span></span>
    
- <span data-ttu-id="49a99-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="49a99-191">FXConnect</span></span>
    
- <span data-ttu-id="49a99-192">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="49a99-192">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="49a99-193">Jive</span><span class="sxs-lookup"><span data-stu-id="49a99-193">Jive</span></span>
    
- <span data-ttu-id="49a99-194">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="49a99-194">Macgregor XIP</span></span>

- <span data-ttu-id="49a99-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="49a99-195">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="49a99-196">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="49a99-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="49a99-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49a99-197">Microsoft Teams</span></span>
       
- <span data-ttu-id="49a99-198">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="49a99-198">Microsoft Yammer</span></span>
    
- <span data-ttu-id="49a99-199">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="49a99-199">Mobile Guard</span></span>
    
- <span data-ttu-id="49a99-200">ピボット</span><span class="sxs-lookup"><span data-stu-id="49a99-200">Pivot</span></span>
    
- <span data-ttu-id="49a99-201">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="49a99-201">Salesforce Chatter</span></span>

- <span data-ttu-id="49a99-202">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="49a99-202">Skype for Business Online</span></span>
    
- <span data-ttu-id="49a99-203">Skype for Business、バージョン 2007 R2 ～ 2016 (オンプレミス)</span><span class="sxs-lookup"><span data-stu-id="49a99-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="49a99-204">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="49a99-204">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="49a99-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="49a99-205">Symphony</span></span>
    
- <span data-ttu-id="49a99-206">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="49a99-206">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="49a99-207">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="49a99-207">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="49a99-208">Thomson Reuters Dealings 3000 / FX トレーディング</span><span class="sxs-lookup"><span data-stu-id="49a99-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="49a99-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="49a99-209">Twitter</span></span>
    
- <span data-ttu-id="49a99-210">UBS チャット</span><span class="sxs-lookup"><span data-stu-id="49a99-210">UBS Chat</span></span>
    
- <span data-ttu-id="49a99-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="49a99-211">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="49a99-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="49a99-212">OpenText</span></span>

<span data-ttu-id="49a99-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="49a99-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="49a99-214">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="49a99-214">Axs Encrypted</span></span>
    
- <span data-ttu-id="49a99-215">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="49a99-215">Axs Exchange</span></span>
    
- <span data-ttu-id="49a99-216">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="49a99-216">Axs Local Archive</span></span>
    
- <span data-ttu-id="49a99-217">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="49a99-217">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="49a99-218">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="49a99-218">Axs Signed</span></span>
    
- <span data-ttu-id="49a99-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="49a99-219">Bloomberg</span></span>
    
- <span data-ttu-id="49a99-220">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="49a99-220">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="49a99-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="49a99-221">Smarsh</span></span>

<span data-ttu-id="49a99-222">[Smarsh](https://www.smarsh.com) は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="49a99-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="49a99-223">目的</span><span class="sxs-lookup"><span data-stu-id="49a99-223">AIM</span></span>
    
- <span data-ttu-id="49a99-224">American Idol</span><span class="sxs-lookup"><span data-stu-id="49a99-224">American Idol</span></span>
    
- <span data-ttu-id="49a99-225">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="49a99-225">Apple Juice</span></span>
    
- <span data-ttu-id="49a99-226">AOL with Pivot クライアント</span><span class="sxs-lookup"><span data-stu-id="49a99-226">AOL with Pivot client</span></span>
    
- <span data-ttu-id="49a99-227">アレス</span><span class="sxs-lookup"><span data-stu-id="49a99-227">Ares</span></span>
    
- <span data-ttu-id="49a99-228">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="49a99-228">Bazaar Voice</span></span>
    
- <span data-ttu-id="49a99-229">Bearshare</span><span class="sxs-lookup"><span data-stu-id="49a99-229">Bear Share</span></span>
    
- <span data-ttu-id="49a99-230">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="49a99-230">Bit Torrent</span></span>
    
- <span data-ttu-id="49a99-231">BlackBerry 呼び出しログ (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="49a99-231">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="49a99-232">BlackBerry メッセンジャー (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="49a99-232">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="49a99-233">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="49a99-233">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="49a99-234">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="49a99-234">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="49a99-235">Bloomberg メール</span><span class="sxs-lookup"><span data-stu-id="49a99-235">Bloomberg Mail</span></span>
    
- <span data-ttu-id="49a99-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="49a99-236">CellTrust</span></span>
    
- <span data-ttu-id="49a99-237">チャットのインポート</span><span class="sxs-lookup"><span data-stu-id="49a99-237">Chat Import</span></span>
    
- <span data-ttu-id="49a99-238">チャットのリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="49a99-238">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="49a99-239">チャター</span><span class="sxs-lookup"><span data-stu-id="49a99-239">Chatter</span></span>
    
- <span data-ttu-id="49a99-240">Cisco IM &amp; プレゼンスサーバー (v 9.0.1、v 9.1、v 9.1.1 SU1、v10、v V10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="49a99-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="49a99-241">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="49a99-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="49a99-242">共同作業のインポート</span><span class="sxs-lookup"><span data-stu-id="49a99-242">Collaboration Import</span></span>
    
- <span data-ttu-id="49a99-243">共同作業のリアルタイム ロギング</span><span class="sxs-lookup"><span data-stu-id="49a99-243">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="49a99-244">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="49a99-244">Direct Connect</span></span>
    
- <span data-ttu-id="49a99-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="49a99-245">Facebook</span></span>
    
- <span data-ttu-id="49a99-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="49a99-246">FactSet</span></span>
    
- <span data-ttu-id="49a99-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="49a99-247">FastTrack</span></span>
    
- <span data-ttu-id="49a99-248">Gnutella</span><span class="sxs-lookup"><span data-stu-id="49a99-248">Gnutella</span></span>
    
- <span data-ttu-id="49a99-249">Google +</span><span class="sxs-lookup"><span data-stu-id="49a99-249">Google+</span></span>
    
- <span data-ttu-id="49a99-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="49a99-250">GoToMyPC</span></span>
    
- <span data-ttu-id="49a99-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="49a99-251">Hopster</span></span>
    
- <span data-ttu-id="49a99-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="49a99-252">HubConnex</span></span>
    
- <span data-ttu-id="49a99-253">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)</span><span class="sxs-lookup"><span data-stu-id="49a99-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="49a99-254">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="49a99-254">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="49a99-255">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="49a99-255">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="49a99-256">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="49a99-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="49a99-257">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="49a99-257">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="49a99-258">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="49a99-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="49a99-259">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="49a99-259">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="49a99-260">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="49a99-260">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="49a99-261">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="49a99-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="49a99-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="49a99-262">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="49a99-263">IM のインポート</span><span class="sxs-lookup"><span data-stu-id="49a99-263">IM Import</span></span>
    
- <span data-ttu-id="49a99-264">IM のリアルタイム ロギングとポリシー</span><span class="sxs-lookup"><span data-stu-id="49a99-264">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="49a99-265">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="49a99-265">Indii Messenger</span></span>
    
- <span data-ttu-id="49a99-266">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="49a99-266">Instant Bloomberg</span></span>
    
- <span data-ttu-id="49a99-267">IRC</span><span class="sxs-lookup"><span data-stu-id="49a99-267">IRC</span></span>
    
- <span data-ttu-id="49a99-268">Jive</span><span class="sxs-lookup"><span data-stu-id="49a99-268">Jive</span></span>
    
- <span data-ttu-id="49a99-269">Jive 6 Real Time Logging (v6、v7)</span><span class="sxs-lookup"><span data-stu-id="49a99-269">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="49a99-270">Jive のインポート</span><span class="sxs-lookup"><span data-stu-id="49a99-270">Jive Import</span></span>
    
- <span data-ttu-id="49a99-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="49a99-271">JXTA</span></span>
    
- <span data-ttu-id="49a99-272">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="49a99-272">LinkedIn</span></span>
    
- <span data-ttu-id="49a99-273">Microsoft Lync (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="49a99-273">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="49a99-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="49a99-274">MFTP</span></span>
    
- <span data-ttu-id="49a99-275">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="49a99-275">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="49a99-276">Microsoft SharePoint (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="49a99-276">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="49a99-277">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="49a99-277">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="49a99-278">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="49a99-278">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="49a99-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="49a99-279">MindAlign</span></span>
    
- <span data-ttu-id="49a99-280">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="49a99-280">Mobile Guard</span></span>
    
- <span data-ttu-id="49a99-281">ウェブ</span><span class="sxs-lookup"><span data-stu-id="49a99-281">MSN</span></span>
    
- <span data-ttu-id="49a99-282">My Space</span><span class="sxs-lookup"><span data-stu-id="49a99-282">My Space</span></span>
    
- <span data-ttu-id="49a99-283">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="49a99-283">NEONetwork</span></span>
    
- <span data-ttu-id="49a99-284">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="49a99-284">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="49a99-285">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="49a99-285">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="49a99-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="49a99-286">Pinterest</span></span>
    
- <span data-ttu-id="49a99-287">ピボット</span><span class="sxs-lookup"><span data-stu-id="49a99-287">Pivot</span></span>
    
- <span data-ttu-id="49a99-288">QQ</span><span class="sxs-lookup"><span data-stu-id="49a99-288">QQ</span></span>
    
- <span data-ttu-id="49a99-289">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="49a99-289">Skype for Business 2015</span></span>
    
- <span data-ttu-id="49a99-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="49a99-290">SoftEther</span></span>
    
- <span data-ttu-id="49a99-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="49a99-291">Symphony</span></span>
    
- <span data-ttu-id="49a99-292">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="49a99-292">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="49a99-293">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="49a99-293">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="49a99-294">終わり</span><span class="sxs-lookup"><span data-stu-id="49a99-294">Tor</span></span>
    
- <span data-ttu-id="49a99-295">TTT</span><span class="sxs-lookup"><span data-stu-id="49a99-295">TTT</span></span>
    
- <span data-ttu-id="49a99-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="49a99-296">Twitter</span></span>
    
- <span data-ttu-id="49a99-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="49a99-297">WinMX</span></span>
    
- <span data-ttu-id="49a99-298">Winny</span><span class="sxs-lookup"><span data-stu-id="49a99-298">Winny</span></span>
    
- <span data-ttu-id="49a99-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="49a99-299">Yahoo</span></span>
    
- <span data-ttu-id="49a99-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="49a99-300">Yammer</span></span>
    
- <span data-ttu-id="49a99-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="49a99-301">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="49a99-302">Verba</span><span class="sxs-lookup"><span data-stu-id="49a99-302">Verba</span></span>

<span data-ttu-id="49a99-303">[Verba](https://www.verba.com) は、次のサードパーティデータソースをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="49a99-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="49a99-304">Avaya Aura ビデオ</span><span class="sxs-lookup"><span data-stu-id="49a99-304">Avaya Aura Video</span></span>
    
- <span data-ttu-id="49a99-305">Avaya Aura 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-305">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="49a99-306">Avtec ラジオ</span><span class="sxs-lookup"><span data-stu-id="49a99-306">Avtec Radio</span></span>
    
- <span data-ttu-id="49a99-307">Bosch/Telex ラジオ</span><span class="sxs-lookup"><span data-stu-id="49a99-307">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="49a99-308">BroadSoft ビデオ</span><span class="sxs-lookup"><span data-stu-id="49a99-308">BroadSoft Video</span></span>
    
- <span data-ttu-id="49a99-309">BroadSoft 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-309">BroadSoft Voice</span></span>
    
- <span data-ttu-id="49a99-310">Centile 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-310">Centile Voice</span></span>
    
- <span data-ttu-id="49a99-311">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="49a99-311">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="49a99-312">Cisco UC ビデオ</span><span class="sxs-lookup"><span data-stu-id="49a99-312">Cisco UC Video</span></span>
    
- <span data-ttu-id="49a99-313">Cisco UC 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-313">Cisco UC Voice</span></span>
    
- <span data-ttu-id="49a99-314">Cisco UCCX/UCCX ビデオ</span><span class="sxs-lookup"><span data-stu-id="49a99-314">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="49a99-315">Cisco UCCX/UCCX 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-315">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="49a99-316">ESChat ラジオ</span><span class="sxs-lookup"><span data-stu-id="49a99-316">ESChat Radio</span></span>
    
- <span data-ttu-id="49a99-317">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="49a99-317">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="49a99-318">IP Trade 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-318">IP Trade Voice</span></span>
    
- <span data-ttu-id="49a99-319">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="49a99-319">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="49a99-320">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="49a99-320">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="49a99-321">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="49a99-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="49a99-322">Oracle / Acme Packet Session Border Controller ビデオ</span><span class="sxs-lookup"><span data-stu-id="49a99-322">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="49a99-323">Oracle / Acme Packet Session Border Controller 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-323">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="49a99-324">Singtel モバイル ボイス</span><span class="sxs-lookup"><span data-stu-id="49a99-324">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="49a99-325">SIPREC ビデオ</span><span class="sxs-lookup"><span data-stu-id="49a99-325">SIPREC Video</span></span>
    
-  <span data-ttu-id="49a99-326">SIPREC 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-326">SIPREC Voice</span></span> 
    
- <span data-ttu-id="49a99-327">Skype for Business / Lync IM</span><span class="sxs-lookup"><span data-stu-id="49a99-327">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="49a99-328">Skype for Business / Lync ビデオ</span><span class="sxs-lookup"><span data-stu-id="49a99-328">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="49a99-329">Skype for Business / Lync 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-329">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="49a99-330">Speakerbus 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-330">Speakerbus Voice</span></span>
    
- <span data-ttu-id="49a99-331">標準的な SIP/H.323 ビデオ</span><span class="sxs-lookup"><span data-stu-id="49a99-331">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="49a99-332">標準的な SIP/H.323 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-332">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="49a99-333">Truphone 音声</span><span class="sxs-lookup"><span data-stu-id="49a99-333">Truphone Voice</span></span>
    
- <span data-ttu-id="49a99-334">TwistedPair ラジオ</span><span class="sxs-lookup"><span data-stu-id="49a99-334">TwistedPair Radio</span></span>
    
- <span data-ttu-id="49a99-335">Windows デスクトップ コンピューターの画面</span><span class="sxs-lookup"><span data-stu-id="49a99-335">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="49a99-336">手順 2: Office 365 でサード パーティ データのメールボックスを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="49a99-336">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="49a99-337">Office 365 にデータをインポートするためにサードパーティ製のデータメールボックスを作成して構成する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="49a99-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="49a99-338">前に説明したように、パートナーコネクタがアイテムのユーザー ID をユーザーアカウントにマップできない場合、アイテムはこのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="49a99-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>
  
 <span data-ttu-id="49a99-339">**Microsoft 365 管理センターでこれらのタスクを完了する**</span><span class="sxs-lookup"><span data-stu-id="49a99-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="49a99-340">ユーザーアカウントを作成し、Exchange Online プラン2ライセンスを割り当てます。「 [Office 365 にユーザーを追加する」を](https://go.microsoft.com/fwlink/p/?LinkId=692098)参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="49a99-341">プラン2ライセンスは、メールボックスを訴訟ホールドの対象にするため、または記憶域クォータが無制限のアーカイブメールボックスを有効にするために必要です。</span><span class="sxs-lookup"><span data-stu-id="49a99-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="49a99-342">Office 365 で、サードパーティのデータメールボックスのユーザーアカウントを **Exchange 管理** 者の役割に追加します。「 [Office 365 で管理者ロールを割り当てる」を](https://go.microsoft.com/fwlink/p/?LinkId=532393)参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="49a99-343">このユーザー アカウントの資格情報を控えておきます。</span><span class="sxs-lookup"><span data-stu-id="49a99-343">Write down the credentials for this user account.</span></span> <span data-ttu-id="49a99-344">手順 4 で説明するように、この情報をパートナーに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a99-344">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="49a99-345">**Exchange 管理センターでこれらのタスクを完了する**</span><span class="sxs-lookup"><span data-stu-id="49a99-345">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="49a99-346">組織内のアドレス帳およびその他のアドレス一覧から、サードパーティのデータメールボックスを非表示にします。「 [ユーザーメールボックスの管理](https://go.microsoft.com/fwlink/p/?LinkId=616058)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="49a99-347">または、次の PowerShell コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="49a99-347">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="49a99-348">サードパーティのデータメールボックスに **Fullaccess** のアクセス許可を割り当てて、管理者またはコンプライアンス責任者が Outlook デスクトップクライアントでサードパーティのデータメールボックスを開くことができるようにします。「 [管理者のアクセス許可を管理する」を](https://go.microsoft.com/fwlink/p/?LinkId=692104)参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="49a99-349">サードパーティのデータメールボックスに対して、次のコンプライアンス関連の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="49a99-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="49a99-350">アーカイブメールボックスを有効にします。「 [アーカイブメールボックスを有効に](enable-archive-mailboxes.md) する」および「 [無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49a99-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="49a99-351">これにより、サードパーティのデータアイテムをアーカイブメールボックスに移動するアーカイブポリシーを設定することによって、プライマリメールボックスの記憶域スペースを解放できます。</span><span class="sxs-lookup"><span data-stu-id="49a99-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="49a99-352">これにより、サードパーティのデータに対して無制限のストレージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="49a99-352">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="49a99-353">サードパーティ データのメールボックスを訴訟ホールドの対象にします。</span><span class="sxs-lookup"><span data-stu-id="49a99-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="49a99-354">セキュリティ/コンプライアンスセンターでは、Microsoft 365 のアイテム保持ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="49a99-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="49a99-355">このメールボックスを保留にすると、サードパーティのデータアイテム (無期限または指定した期間中) が保持され、それらがメールボックスから削除されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="49a99-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="49a99-356">次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-356">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="49a99-357">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="49a99-357">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="49a99-358">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="49a99-358">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="49a99-359">サードパーティデータメールボックスへの所有者、代理人、および管理者のアクセスに対してメールボックス監査ログを有効にします。「 [メールボックス監査を有効にする」を](enable-mailbox-auditing.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="49a99-360">これにより、サードパーティのデータメールボックスにアクセスできるすべてのユーザーによって実行されたすべてのアクティビティを監査できます。</span><span class="sxs-lookup"><span data-stu-id="49a99-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="49a99-361">手順 3: サード パーティのデータに対してユーザーのメールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="49a99-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="49a99-362">次の手順は、サード パーティのデータをサポートするためにユーザーのメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="49a99-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="49a99-363">Exchange 管理センターまたは対応する Windows PowerShell コマンドレットを使用して、これらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="49a99-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="49a99-364">各ユーザーのアーカイブメールボックスを有効にします。「 [アーカイブメールボックスを有効に](enable-archive-mailboxes.md) する」および「 [無制限アーカイブを有効にする](enable-unlimited-archiving.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49a99-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="49a99-365">ユーザーメールボックスを訴訟ホールドの対象にするか、Microsoft 365 アイテム保持ポリシーを適用します。次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="49a99-366">メールボックスを訴訟ホールドの対象にする</span><span class="sxs-lookup"><span data-stu-id="49a99-366">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="49a99-367">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="49a99-367">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="49a99-368">前述のように、メールボックスをホールドの対象にすると、サードパーティ データ ソースからのアイテムを保持する期間を設定したり、アイテムを無期限に保持したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="49a99-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="49a99-369">手順 4: パートナーに情報を提供する</span><span class="sxs-lookup"><span data-stu-id="49a99-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="49a99-370">最後の手順として、パートナーに次の情報を提供し、ユーザーのメールボックスとサードパーティデータメールボックスにデータをインポートするために組織に接続するためのコネクタを構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a99-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="49a99-371">Office 365 の Azure サービスに接続するために使用されるエンドポイント:</span><span class="sxs-lookup"><span data-stu-id="49a99-371">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="49a99-372">手順2で作成したサードパーティデータメールボックスのサインイン資格情報 (Microsoft 365 ユーザー ID とパスワード)。</span><span class="sxs-lookup"><span data-stu-id="49a99-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="49a99-373">パートナーのコネクタがアイテムにアクセスして、アイテムをユーザーのメールボックスとサード パーティ データのメールボックスにインポートするには、これらの資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="49a99-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="49a99-374">手順 5: Azure Active Directory にサードパーティのデータコネクタを登録する</span><span class="sxs-lookup"><span data-stu-id="49a99-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="49a99-375">2018年9月30日から、Office 365 の Azure サービスは、Exchange Online での先進認証の使用を開始して、組織に接続してデータをインポートするサードパーティデータコネクタを認証します。</span><span class="sxs-lookup"><span data-stu-id="49a99-375">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="49a99-376">この変更の理由は、モダン認証によって、現在のメソッドよりも高いセキュリティが提供されるためです。これは、以前に説明したエンドポイントを使用して Azure サービスに接続するサードパーティ製コネクタの許可リストに基づいていました。</span><span class="sxs-lookup"><span data-stu-id="49a99-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="49a99-377">新しいモダン認証方法を使用してサードパーティ製データコネクタを Office 365 に接続できるようにするには、組織の管理者が、Azure Active Directory の信頼できるサービスアプリケーションとしてそのコネクタを登録するために同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a99-377">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="49a99-378">これを行うには、アクセス許可要求を受け入れ、コネクタが Azure Active Directory 内の組織のデータにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="49a99-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="49a99-379">この要求を承諾すると、サードパーティのデータコネクタがエンタープライズアプリケーションとして Azure Active Directory に追加され、サービスプリンシパルとして表されます。</span><span class="sxs-lookup"><span data-stu-id="49a99-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="49a99-380">同意プロセスの詳細については、「  [テナント管理者の同意](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-380">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="49a99-381">コネクタを登録するための要求をアクセスして受け入れる手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="49a99-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="49a99-382">[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動し、全体管理者の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="49a99-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="49a99-383">次のダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49a99-383">The following dialog box is displayed.</span></span> <span data-ttu-id="49a99-384">Carets を展開して、コネクタに割り当てられているアクセス許可を確認できます。</span><span class="sxs-lookup"><span data-stu-id="49a99-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![[アクセス許可の要求] ダイアログが表示されます。](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="49a99-386">[ **Accept** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49a99-386">Click **Accept**.</span></span>

<span data-ttu-id="49a99-387">要求を受け入れると、 [Azure portal](https://portal.azure.com) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49a99-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="49a99-388">組織のアプリケーションの一覧を表示するには、[ **Azure Active Directory**  >  **エンタープライズアプリケーション** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49a99-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="49a99-389">Office 365 サードパーティデータコネクタは、 **エンタープライズアプリケーション** ブレードに一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="49a99-389">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49a99-390">2018年9月30日以降、サードパーティのデータコネクタを Azure Active Directory に登録しない場合、組織内のメールボックスにサードパーティのデータがインポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="49a99-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="49a99-391">注: 既存のサードパーティのデータコネクタ (2018 年9月30日より前に作成されたもの) は、手順5の手順に従って Azure Active Directory に登録する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="49a99-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="49a99-392">サードパーティのデータコネクタの同意を取り消す</span><span class="sxs-lookup"><span data-stu-id="49a99-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="49a99-393">組織がアクセス許可要求に同意して、Azure Active Directory にサードパーティデータコネクタを登録すると、組織はいつでもその同意を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="49a99-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="49a99-394">ただし、コネクタの同意を取り消すということは、サードパーティのデータソースからのデータが Office 365 にインポートされなくなることを意味します。</span><span class="sxs-lookup"><span data-stu-id="49a99-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="49a99-395">サードパーティのデータコネクタの同意を取り消すには、Azure ポータルの [ **エンタープライズアプリケーション** ] ブレードまたは Office 365 PowerShell で [new-msolserviceprincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) を使用して、azure Active Directory からアプリケーションを削除します (対応するサービスプリンシパルを削除する)。</span><span class="sxs-lookup"><span data-stu-id="49a99-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="49a99-396">Azure Active Directory PowerShell で [AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="49a99-396">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="49a99-397">詳細情報</span><span class="sxs-lookup"><span data-stu-id="49a99-397">More information</span></span>

- <span data-ttu-id="49a99-398">前述のように、サード パーティのデータ ソースのアイテムは、メール メッセージとして Exchange メールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="49a99-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="49a99-399">パートナーコネクタは、Office 365 API によって必要とされるスキーマを使用してアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="49a99-399">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="49a99-400">次の表では、メール メッセージとして Exchange メールボックスにインポートされた後の、サード パーティのデータ ソースのアイテムのメッセージのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="49a99-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="49a99-401">この表では、メッセージのプロパティが必須かどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="49a99-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="49a99-402">必須プロパティは設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a99-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="49a99-403">必須のプロパティが設定されていないアイテムは、Office 365 にインポートされません。</span><span class="sxs-lookup"><span data-stu-id="49a99-403">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="49a99-404">インポートプロセスでは、アイテムがインポートされなかった理由と、不足しているプロパティがあることを示すエラーメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="49a99-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="49a99-405">**メッセージのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="49a99-405">**Message property**</span></span>|<span data-ttu-id="49a99-406">**必須かどうか?**</span><span class="sxs-lookup"><span data-stu-id="49a99-406">**Mandatory?**</span></span>|<span data-ttu-id="49a99-407">**説明**</span><span class="sxs-lookup"><span data-stu-id="49a99-407">**Description**</span></span>|<span data-ttu-id="49a99-408">**値の例**</span><span class="sxs-lookup"><span data-stu-id="49a99-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="49a99-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="49a99-409">**FROM**</span></span> <br/> |<span data-ttu-id="49a99-410">必要</span><span class="sxs-lookup"><span data-stu-id="49a99-410">Yes</span></span>  <br/> |<span data-ttu-id="49a99-411">最初にサード パーティのデータ ソース内のアイテムを作成または送信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="49a99-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="49a99-412">パートナーコネクタは、ソースアイテム (Twitter ハンドルなど) から、すべての参加者 ([差出人] および [宛先] フィールド内のユーザー) のユーザーアカウントにユーザー ID をマップしようとします。</span><span class="sxs-lookup"><span data-stu-id="49a99-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="49a99-413">メッセージのコピーが、すべての参加者のメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="49a99-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="49a99-414">アイテムの参加者が1人のユーザーアカウントにマップできない場合、そのアイテムは Office 365 のサードパーティ製のアーカイブメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="49a99-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="49a99-415">アイテムの送信者として識別される参加者は、アイテムのインポート先の組織内にアクティブなメールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49a99-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="49a99-416">送信者がアクティブなメールボックスを持っていない場合は、次のエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="49a99-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="49a99-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="49a99-417">**TO**</span></span> <br/> |<span data-ttu-id="49a99-418">必要</span><span class="sxs-lookup"><span data-stu-id="49a99-418">Yes</span></span>  <br/> |<span data-ttu-id="49a99-419">アイテムを受信したユーザー (データ ソース内のアイテムに該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="49a99-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="49a99-420">**件名**</span><span class="sxs-lookup"><span data-stu-id="49a99-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="49a99-421">いいえ</span><span class="sxs-lookup"><span data-stu-id="49a99-421">No</span></span>  <br/> |<span data-ttu-id="49a99-422">ソース アイテムの件名。</span><span class="sxs-lookup"><span data-stu-id="49a99-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="49a99-423">**DATE**</span><span class="sxs-lookup"><span data-stu-id="49a99-423">**DATE**</span></span> <br/> |<span data-ttu-id="49a99-424">必要</span><span class="sxs-lookup"><span data-stu-id="49a99-424">Yes</span></span>  <br/> |<span data-ttu-id="49a99-425">アイテムが最初に作成または顧客データソースに投稿された日付。</span><span class="sxs-lookup"><span data-stu-id="49a99-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="49a99-426">たとえば、Twitter メッセージがツイートされた日時です。</span><span class="sxs-lookup"><span data-stu-id="49a99-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="49a99-427">**物体**</span><span class="sxs-lookup"><span data-stu-id="49a99-427">**BODY**</span></span> <br/> |<span data-ttu-id="49a99-428">いいえ</span><span class="sxs-lookup"><span data-stu-id="49a99-428">No</span></span>  <br/> |<span data-ttu-id="49a99-429">メッセージまたは投稿のコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="49a99-429">The contents of the message or post.</span></span> <span data-ttu-id="49a99-430">一部のデータ ソースでは、このプロパティのコンテンツは **SUBJECT** プロパティのコンテンツと同じになります。</span><span class="sxs-lookup"><span data-stu-id="49a99-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="49a99-431">インポート処理中に、パートナーコネクタは、可能な限りコンテンツソースの完全な忠実性を維持しようとします。</span><span class="sxs-lookup"><span data-stu-id="49a99-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="49a99-432">可能な場合には、ソース アイテムの本文からのファイル、グラフィック、またはその他のコンテンツが、このプロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="49a99-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="49a99-433">それ以外の場合、ソース アイテムからのコンテンツは **ATTACHMENT** プロパティに含まれます。</span><span class="sxs-lookup"><span data-stu-id="49a99-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="49a99-434">このプロパティの内容は、パートナーコネクタとソースプラットフォームの機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="49a99-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="49a99-435">**資料**</span><span class="sxs-lookup"><span data-stu-id="49a99-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="49a99-436">いいえ</span><span class="sxs-lookup"><span data-stu-id="49a99-436">No</span></span>  <br/> |<span data-ttu-id="49a99-437">データソース内のアイテム (Twitter のツイート、インスタントメッセージングの会話など) に添付ファイルがあり、画像が含まれている場合、パートナー接続は最初に **BODY** プロパティに添付ファイルを含めようとします。</span><span class="sxs-lookup"><span data-stu-id="49a99-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="49a99-438">これができない場合は、\* \* ATTACHMENT \* \* プロパティに追加されます。</span><span class="sxs-lookup"><span data-stu-id="49a99-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="49a99-439">添付ファイルの例として、他にも Facebook の「いいね」、コンテンツ ソースからのメタデータ、およびメッセージまたは投稿への返信などがあります。</span><span class="sxs-lookup"><span data-stu-id="49a99-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="49a99-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="49a99-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="49a99-441">必要</span><span class="sxs-lookup"><span data-stu-id="49a99-441">Yes</span></span>  <br/> | <span data-ttu-id="49a99-442">これは、パートナーコネクタによって作成および設定される複数値プロパティです。</span><span class="sxs-lookup"><span data-stu-id="49a99-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="49a99-443">このプロパティの形式は  `IPM.NOTE.Source.Event` です。</span><span class="sxs-lookup"><span data-stu-id="49a99-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="49a99-444">(このプロパティはで始まる必要があり  `IPM.NOTE` ます。</span><span class="sxs-lookup"><span data-stu-id="49a99-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="49a99-445">この形式は、メッセージクラスの形式と似て  `IPM.NOTE.X` います)。このプロパティには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="49a99-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="49a99-446">`Source`: サードパーティのデータソースを示します。たとえば、Twitter、Facebook、BlackBerry などです。</span><span class="sxs-lookup"><span data-stu-id="49a99-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="49a99-447">`Event`: アイテムを生成したサードパーティのデータソースで実行されたアクティビティの種類を示します。たとえば、Twitter のツイート、または Facebook の投稿。</span><span class="sxs-lookup"><span data-stu-id="49a99-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="49a99-448">イベントは、データソースに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="49a99-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="49a99-449">このプロパティの目的の1つは、アイテムが発生元であるデータソースに基づいて、またはイベントの種類に基づいて、特定のアイテムをフィルター処理することです。</span><span class="sxs-lookup"><span data-stu-id="49a99-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="49a99-450">たとえば、電子情報開示検索では、検索クエリを作成して、特定のユーザーによって投稿されたすべてのツイートなど) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="49a99-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="49a99-451">アイテムが Office 365 のメールボックスに正常にインポートされると、一意識別子が HTTP 応答の一部として発信者に戻されます。</span><span class="sxs-lookup"><span data-stu-id="49a99-451">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="49a99-452">と呼ばれるこの識別子は  `x-IngestionCorrelationID` 、アイテムのエンドツーエンドの追跡のためにパートナーによって、以降のトラブルシューティングのために使用できます。</span><span class="sxs-lookup"><span data-stu-id="49a99-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="49a99-453">パートナーがこの情報をキャプチャし、パートナーの側で記録することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49a99-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="49a99-454">この識別子を示す HTTP 応答の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="49a99-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="49a99-455">セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、サードパーティのデータソースからメールボックスにインポートされたアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="49a99-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="49a99-456">これらのインポートされたアイテムを検索するには、次のようなメッセージのプロパティと値のペアをキーワードボックスで使用します。</span><span class="sxs-lookup"><span data-stu-id="49a99-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="49a99-457">**`kind:externaldata`** : このプロパティと値のペアを使用して、すべてのサードパーティのデータ型を検索します。</span><span class="sxs-lookup"><span data-stu-id="49a99-457">**`kind:externaldata`** : Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="49a99-458">たとえば、サードパーティのデータソースからインポートされ、インポートされたアイテムの Subject プロパティに "contoso" という単語が含まれているアイテムを検索するには、キーワードクエリを使用し  `kind:externaldata AND subject:contoso` ます。</span><span class="sxs-lookup"><span data-stu-id="49a99-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="49a99-459">**`itemclass:ipm.externaldata.<third-party data type>`** : このプロパティと値のペアを使用して、サードパーティのデータの指定した種類のみを検索します。</span><span class="sxs-lookup"><span data-stu-id="49a99-459">**`itemclass:ipm.externaldata.<third-party data type>`** : Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="49a99-460">たとえば、Subject プロパティに "contoso" という単語が含まれる Facebook データのみを検索するには、キーワードクエリを使用し  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` ます。</span><span class="sxs-lookup"><span data-stu-id="49a99-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="49a99-461">プロパティのサードパーティデータ型に使用する値の完全な一覧につい  `itemclass` ては、「 [コンテンツ検索を使用して、Office 365 にインポートされたサードパーティのデータを検索する](use-content-search-to-search-third-party-data-that-was-imported.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="49a99-462">コンテンツ検索の使用方法とキーワード検索クエリの作成方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a99-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="49a99-463">Office 365 のコンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="49a99-463">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="49a99-464">コンテンツ検索のキーワード クエリと検索条件</span><span class="sxs-lookup"><span data-stu-id="49a99-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
