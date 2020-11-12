---
title: データの移行中および移行後
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: データの移動は、Microsoft がテナントのサービスと関連データを新しいデータセンター geo に移動するときに発生するバックエンドの操作です。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63536a46e28f264f49e8071710221b0847f62414
ms.sourcegitcommit: 86e878849a8bdd456cee6a3f49939d26223fb626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "48997793"
---
# <a name="during-and-after-your-data-move"></a><span data-ttu-id="3f139-103">データの移行中および移行後</span><span class="sxs-lookup"><span data-stu-id="3f139-103">During and after your data move</span></span>

<span data-ttu-id="3f139-104">データの移行は、エンドユーザーへの影響を最小限に抑えたバックエンドの操作です。</span><span class="sxs-lookup"><span data-stu-id="3f139-104">Data moves are a back-end operation with minimal impact to end-users.</span></span> <span data-ttu-id="3f139-105">Microsoft が各サービスとお客様のテナントの関連データを新しいデータセンター geo に移動する際には、何も行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3f139-105">No action is required while Microsoft moves each service and associated data for your tenant to a new datacenter geo.</span></span> <span data-ttu-id="3f139-106">データの転送および検証は事前にバックグラウンドで行われ、ユーザーへの影響は最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="3f139-106">Data transfer and validation occur in the background in advance with minimal impact to users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f139-p102">移動はサービスごとに、異なる時間に行われます。結果として、サービスごとに異なる時間に、説明されているような機能制限がかかります。</span><span class="sxs-lookup"><span data-stu-id="3f139-p102">Moves occur at different times for each service. As a result, you'll see the described reduced functionality for each service at a different time.</span></span> 
  
<span data-ttu-id="3f139-109">Exchange Online、SharePoint Online、Teams チャットサービスのそれぞれについて移行が完了したら、Microsoft 365 メッセージセンターで確認を行います。</span><span class="sxs-lookup"><span data-stu-id="3f139-109">Watch the Microsoft 365 Message Center for confirmation when moves for each of Exchange Online, SharePoint Online, and Teams chat service complete.</span></span> <span data-ttu-id="3f139-110">次の表に示されているように、登録期間が終了してから最大24か月を経過して、新しいデータセンター geo に移動中のコア顧客データを完成させることができます。</span><span class="sxs-lookup"><span data-stu-id="3f139-110">As shown in the table below, it can take up to 24 months after the end of the enrollment period to complete core customer data at rest moves to the new datacenter geo.</span></span>   

|<span data-ttu-id="3f139-111">**国がサインアップしているお客様**</span><span class="sxs-lookup"><span data-stu-id="3f139-111">**Customers with signup country in**</span></span>|<span data-ttu-id="3f139-112">**完了したすべての移動**</span><span class="sxs-lookup"><span data-stu-id="3f139-112">**All moves completed by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f139-113">オーストラリア、ニュージーランド、フィジー</span><span class="sxs-lookup"><span data-stu-id="3f139-113">Australia, New Zealand, Fiji</span></span>  <br/> |<span data-ttu-id="3f139-114">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-114">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-115">日本</span><span class="sxs-lookup"><span data-stu-id="3f139-115">Japan</span></span>  <br/> |<span data-ttu-id="3f139-116">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-116">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-117">インド</span><span class="sxs-lookup"><span data-stu-id="3f139-117">India</span></span>  <br/> |<span data-ttu-id="3f139-118">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-118">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-119">カナダ</span><span class="sxs-lookup"><span data-stu-id="3f139-119">Canada</span></span>  <br/> |<span data-ttu-id="3f139-120">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-120">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-121">韓国</span><span class="sxs-lookup"><span data-stu-id="3f139-121">South Korea</span></span>  <br/> |<span data-ttu-id="3f139-122">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-122">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-123">英国</span><span class="sxs-lookup"><span data-stu-id="3f139-123">United Kingdom</span></span>  <br/> |<span data-ttu-id="3f139-124">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-124">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-125">フランス</span><span class="sxs-lookup"><span data-stu-id="3f139-125">France</span></span>  <br/> |<span data-ttu-id="3f139-126">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-126">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-127">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="3f139-127">United Arab Emirates</span></span>  <br/> |<span data-ttu-id="3f139-128">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-128">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-129">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="3f139-129">South Africa</span></span>  <br/> |<span data-ttu-id="3f139-130">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-130">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-131">スイス、リヒテンシュタイン</span><span class="sxs-lookup"><span data-stu-id="3f139-131">Switzerland, Liechtenstein</span></span>  <br/> |<span data-ttu-id="3f139-132">2022年7月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-132">July 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-133">ノルウェー</span><span class="sxs-lookup"><span data-stu-id="3f139-133">Norway</span></span>  <br/> |<span data-ttu-id="3f139-134">2022年11月1日</span><span class="sxs-lookup"><span data-stu-id="3f139-134">November 1, 2022</span></span>  <br/> |
|<span data-ttu-id="3f139-135">ドイツ</span><span class="sxs-lookup"><span data-stu-id="3f139-135">Germany</span></span>  <br/> |<span data-ttu-id="3f139-136">2023年5月1</span><span class="sxs-lookup"><span data-stu-id="3f139-136">May 1, 2023</span></span>  <br/> |

## <a name="exchange-online"></a><span data-ttu-id="3f139-137">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3f139-137">Exchange Online</span></span>

<span data-ttu-id="3f139-138">各ユーザーをシングル テナントの新しいデータセンター geo に移動するのに時間がかかるため、移動中は一部のユーザーが古いデータセンター geo のまま、他のユーザーは新しいデータセンター geo という状態になります。</span><span class="sxs-lookup"><span data-stu-id="3f139-138">Because it takes time to move each user to the new datacenter geo for a single tenant, some users will still be in the old datacenter geo during the move, while others will be in the new datacenter geo.</span></span> <span data-ttu-id="3f139-139">これは、複数のメールボックスへのアクセスを必要とする一部の機能が、移行プロセスの間に完全には機能しない場合があることを意味します。これは、先週まで可能です。</span><span class="sxs-lookup"><span data-stu-id="3f139-139">This means that some features that involve accessing multiple mailboxes may not fully work during a period of the move process, which can last weeks.</span></span> <span data-ttu-id="3f139-140">該当する機能については、この後のセクションで取り上げます。</span><span class="sxs-lookup"><span data-stu-id="3f139-140">These features are described in the following sections.</span></span>
  
### <a name="open-shared-folder-in-outlook-web-access"></a><span data-ttu-id="3f139-141">Outlook Web Access で "共有フォルダー" を開く</span><span class="sxs-lookup"><span data-stu-id="3f139-141">Open "Shared Folder" in Outlook Web Access</span></span>

<span data-ttu-id="3f139-p105">一部のユーザーは、Outlook Web Access で "共有フォルダー" 機能を使用して、別のメールボックスから共有メール フォルダー (ユーザーが読み取りまたは書き込みアクセス許可を持つフォルダー) を開きます。次の表に、メールボックスの移動中に、共有フォルダーへのアクセス権がどのように動作するかを取り上げます。共有メールボックスへのフル アクセス許可があるユーザーは、移動中に Outlook Web Access を使用してメールボックスを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="3f139-p105">Some users open a shared mail folder from another mailbox (that the user has read or write permissions to) in Outlook Web Access using the "Shared Folder" feature. The following table describes how access to shared folders works during a mailbox move. Please note that users with full permissions to a shared mailbox can open the mailbox by using Outlook Web Access during the move.</span></span> 
  
|<span data-ttu-id="3f139-145">**構成**</span><span class="sxs-lookup"><span data-stu-id="3f139-145">**Configuration**</span></span>|<span data-ttu-id="3f139-146">**説明**</span><span class="sxs-lookup"><span data-stu-id="3f139-146">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f139-147">別のメールボックスへのメールボックス フォルダー アクセス許可があるユーザー</span><span class="sxs-lookup"><span data-stu-id="3f139-147">User has mailbox folder permission to another mailbox</span></span>  <br/> |<span data-ttu-id="3f139-148">制限される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f139-148">Potentially limited.</span></span>  <br/> <span data-ttu-id="3f139-149">テナントの移動中にユーザー A とメールボックス B が同じ geo になく、ユーザー A が持っているアクセス許可がメールボックス B の特定のフォルダーに対してのみの場合、ユーザー A は Outlook Web Access でメールボックス B のフォルダーを開くことができません。</span><span class="sxs-lookup"><span data-stu-id="3f139-149">If User A and Mailbox B aren't in the same geo during the tenant move, User A can't open Mailbox B's folder in Outlook Web Access if User A only has permission to a specific folder in Mailbox B.</span></span>  <br/> <span data-ttu-id="3f139-150">共有フォルダーを追加するには、左側のナビゲーション ウィンドウでユーザー名を右クリックし、 **[共有フォルダーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f139-150">To add a shared folder, right-click the user name in the left navigation panel and select **Add shared folder**.</span></span>  <br/> |
|<span data-ttu-id="3f139-151">別のメールボックスへのメールボックス フル アクセス許可があるユーザー</span><span class="sxs-lookup"><span data-stu-id="3f139-151">User with full mailbox permission to another mailbox</span></span>  <br/> |<span data-ttu-id="3f139-152">完全にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3f139-152">Fully supported.</span></span>  <br/> <span data-ttu-id="3f139-153">ユーザー A がメールボックス B に "フルアクセス" アクセス許可を持っている場合、ユーザー A は Outlook Web Access の左側のナビゲーションパネルで共有フォルダーをクリックして、メールボックス B が表示されているウィンドウを開くことができます。 ユーザーは、移動中に Outlook Web Access を使用して共有メールボックスを開くことができ、悪影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="3f139-153">If User A has "Full Access" permission to Mailbox B, then User A can click the shared folder in the left navigation panel in Outlook Web Access to open a window showing Mailbox B.  A user can open a shared mailbox using Outlook Web Access during the move without any adverse impact.</span></span> <span data-ttu-id="3f139-154">制限は、メールボックス内のフォルダー レベルの共有だけに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f139-154">The limitation only applies to folder-level sharing in a mailbox.</span></span>           |
  
## <a name="sharepoint-online"></a><span data-ttu-id="3f139-155">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3f139-155">SharePoint Online</span></span>

<span data-ttu-id="3f139-156">SharePoint Online を移行すると、以下のサービスのデータも移行されます。</span><span class="sxs-lookup"><span data-stu-id="3f139-156">When SharePoint Online is moved, data for the following services is also moved:</span></span>
  
- <span data-ttu-id="3f139-157">One Drive for Business</span><span class="sxs-lookup"><span data-stu-id="3f139-157">One Drive for Business</span></span>
    
- <span data-ttu-id="3f139-158">Microsoft 365 Video services</span><span class="sxs-lookup"><span data-stu-id="3f139-158">Microsoft 365 Video services</span></span>
    
- <span data-ttu-id="3f139-159">ブラウザー内の Office</span><span class="sxs-lookup"><span data-stu-id="3f139-159">Office in a browser</span></span>
    
- <span data-ttu-id="3f139-160">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="3f139-160">Microsoft 365 Apps for enterprise</span></span>
    
- <span data-ttu-id="3f139-161">Visio Pro for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f139-161">Visio Pro for Microsoft 365</span></span>
    
<span data-ttu-id="3f139-162">SharePoint Online データの移行が完了すると、次に示す影響が現れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f139-162">After we've completed moving your SharePoint Online data, you might see the some of the following effects.</span></span>
  
### <a name="microsoft-365-video-services"></a><span data-ttu-id="3f139-163">Microsoft 365 Video Services</span><span class="sxs-lookup"><span data-stu-id="3f139-163">Microsoft 365 Video Services</span></span>

- <span data-ttu-id="3f139-164">ビデオのデータの移動は、SharePoint Online にある残りのコンテンツの移動より時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="3f139-164">The data move for video takes longer than the moves for the rest of your content in SharePoint Online.</span></span>
    
- <span data-ttu-id="3f139-165">SharePoint Online のコンテンツを移行すると、ビデオが再生できない時間が生じます。</span><span class="sxs-lookup"><span data-stu-id="3f139-165">After the SharePoint Online content is moved, there will be a time frame when videos aren't able to be played.</span></span>
    
- <span data-ttu-id="3f139-166">以前のデータセンターからコード変換されたコピーを削除し、新しいデータセンターでコードを再変換しています。</span><span class="sxs-lookup"><span data-stu-id="3f139-166">We're removing the trans-coded copies from the previous datacenter and transcoding them again in the new datacenter.</span></span>
    
### <a name="search"></a><span data-ttu-id="3f139-167">検索</span><span class="sxs-lookup"><span data-stu-id="3f139-167">Search</span></span>

<span data-ttu-id="3f139-p107">SharePoint Online データを移行する過程で、検索インデックスと検索設定を新しい場所に移行します。SharePoint Onlineデータの移行が **完了** するまで、ユーザーは引き続き元の場所でインデックスを利用できます。SharePoint Online データの移行が完了すると、新しい場所で、検索機能によってコンテンツのクロールが自動的に再開されます。これより以降、ユーザーは移行したインデックスを利用できます。移行後に生じたコンテンツの変更は、クロールで反映されるまで移行したインデックスに組み込まれません。SharePoint Online データの移行が完了した直後に結果の鮮度が低いと感じる顧客はほとんどいませんが、その後の 24 時間から 48 時間には一部の顧客が鮮度の低下に気付く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f139-p107">In the course of moving your SharePoint Online data, we migrate your search index and search settings to a new location. Until we've **completed** the move of your SharePoint Online data, we continue to serve your users from the index in the original location. In the new location, search automatically starts crawling your content after we've completed moving your SharePoint Online data. From this point and onwards we serve your users from the migrated index. Changes to your content that occurred after the migration aren't included in the migrated index until crawling picks them up. Most customers don't notice that results are less fresh right after we've completed moving their SharePoint Online data, but some customers might experience reduced freshness in the first 24-48 hours</span></span> 
  
<span data-ttu-id="3f139-174">次の検索機能が影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="3f139-174">The following search features are affected:</span></span>
  
- <span data-ttu-id="3f139-175">検索結果と検索 Web パーツ:移行後に生じた変更は、クロールで反映されるまで結果に含まれません。</span><span class="sxs-lookup"><span data-stu-id="3f139-175">Search results and Search Web Parts: Results don't include changes that occurred after the migration until crawling picks them up.</span></span> 
    
- <span data-ttu-id="3f139-176">Delve:移行後に生じた変更は、クロールで反映されるまで Delve に含まれません。</span><span class="sxs-lookup"><span data-stu-id="3f139-176">Delve: Delve doesn't include changes that occurred after the migration until crawling picks them up.</span></span>
    
- <span data-ttu-id="3f139-p108">サイトの人気と検索に関するレポート: 新しい場所での Excel レポートのカウントには、移行した数、および SharePoint Online データの移行完了後に実行された利用状況レポートの数のみが含まれます。中間の期間の数はすべて失われ、回復することはできません。この期間は、通常、2、3 日です。顧客によっては情報が失われている期間が増減することもあります。</span><span class="sxs-lookup"><span data-stu-id="3f139-p108">Popularity and Search Reports for the site: Counts for Excel reports in the new location only include migrated counts and counts from usage reports that have run after we completed moving your SharePoint Online data. Any counts from the interim period are lost and can't be recovered. This period is typically a couple of days. Some customers might experience shorter or longer losses.</span></span>
    
- <span data-ttu-id="3f139-181">ビデオ ポータル:ビデオ ポータルの表示回数と統計情報は Excel レポートの統計情報に基づいているため、ビデオ ポータルの表示回数と統計情報は、Excel レポートと同じ期間失われます。</span><span class="sxs-lookup"><span data-stu-id="3f139-181">Video Portal: View counts and statistics for the Video Portal depend on the statistics for Excel Reports, so view counts and statistics for the Video Portal are lost for the same time period as for the Excel reports.</span></span>
    
- <span data-ttu-id="3f139-182">電子情報開示:移行中に変更されたアイテムは、クロールで変更が反映されるまでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3f139-182">eDiscovery: Items that changed during the migration aren't shown until crawling picks up the changes.</span></span>
    
- <span data-ttu-id="3f139-183">データ損失防止 (DLP):クロールで変更が反映されるまで、変更されたアイテムに対してポリシーは適用されません。</span><span class="sxs-lookup"><span data-stu-id="3f139-183">Data Loss Protection (DLP): Policies aren't enforced on items that change until crawling picks up the changes.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="3f139-184">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f139-184">Microsoft Teams</span></span>

<span data-ttu-id="3f139-185">Microsoft は、Exchange Online、SharePoint Online、OneDrive for Business に加えて、Teams chat service のデータをローカルデータセンターに移行します。</span><span class="sxs-lookup"><span data-stu-id="3f139-185">In addition to Exchange Online, SharePoint Online, and OneDrive for Business, Microsoft will migrate Teams chat service data to the local datacenter.</span></span>

- <span data-ttu-id="3f139-186">Teams のチャットメッセージ (プライベートメッセージやチャネルメッセージを含む)。</span><span class="sxs-lookup"><span data-stu-id="3f139-186">Teams chat messages, including private messages and channel messages.</span></span>
- <span data-ttu-id="3f139-187">チャットで使用される Teams 画像。</span><span class="sxs-lookup"><span data-stu-id="3f139-187">Teams images used in chats.</span></span>

<span data-ttu-id="3f139-188">Teams ファイルは SharePoint Online に格納され、Teams チャットファイルは OneDrive for Business に保存されます。</span><span class="sxs-lookup"><span data-stu-id="3f139-188">Teams files are stored in SharePoint Online and Teams chat files are stored in OneDrive for Business.</span></span> <span data-ttu-id="3f139-189">ボイスメール、予定表、チャット履歴、および連絡先は、Exchange Online に格納されます。</span><span class="sxs-lookup"><span data-stu-id="3f139-189">Voicemail, calendar, chat history, and contacts are stored in Exchange Online.</span></span> <span data-ttu-id="3f139-190">多くの場合、Exchange Online、SharePoint Online、OneDrive for Business は、ローカルのデータセンター geo のお客様によって既に使用されており、資格のあるお客様の国の Microsoft 365 移行プログラムの一部でもあります。</span><span class="sxs-lookup"><span data-stu-id="3f139-190">In many cases, Exchange Online, SharePoint Online and OneDrive for Business are already used by the customer in the local datacenter geo and are also part of the Microsoft 365 migration program for eligible customer countries.</span></span>

## <a name="skype-for-business"></a><span data-ttu-id="3f139-191">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3f139-191">Skype for Business</span></span>

<span data-ttu-id="3f139-192">Skype for Business の移動は利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3f139-192">Skype for Business moves are no longer available.</span></span>  <span data-ttu-id="3f139-193">[Skype For Business Online は](https://docs.microsoft.com/lifecycle/announcements/skype-for-business-online-retirement) 、2021年7月31日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="3f139-193">[Skype for Business Online will be retired](https://docs.microsoft.com/lifecycle/announcements/skype-for-business-online-retirement) on July 31, 2021.</span></span> <span data-ttu-id="3f139-194">その時間が過ぎると、サービスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="3f139-194">After that time, the service will no longer be accessible.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="3f139-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f139-195">Related topics</span></span> 
 
[<span data-ttu-id="3f139-196">データ移行を申請する方法</span><span class="sxs-lookup"><span data-stu-id="3f139-196">How to request your data move</span></span>](request-your-data-move.md)
    
[<span data-ttu-id="3f139-197">データ移行についての一般的な FAQ</span><span class="sxs-lookup"><span data-stu-id="3f139-197">Data move general FAQ</span></span>](data-move-faq.md)
  
[<span data-ttu-id="3f139-198">Microsoft Dynamics CRM Online の新しいデータ センター geo</span><span class="sxs-lookup"><span data-stu-id="3f139-198">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[<span data-ttu-id="3f139-199">Azure のリージョン</span><span class="sxs-lookup"><span data-stu-id="3f139-199">Azure services by region</span></span>](https://azure.microsoft.com/regions/)
