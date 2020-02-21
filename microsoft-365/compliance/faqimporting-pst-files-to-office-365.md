---
title: Office 365 への PST ファイルのインポートに関するよくあるご質問
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '管理者にとってよく寄せられる質問。 Office 365 インポートサービスを使用して組織の PST ファイルを Office 365 メールボックスにインポートする方法について説明します。 '
ms.openlocfilehash: 31df33ffe2c69478f0304bd27b49254995d8b89c
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170487"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="8fe90-103">Office 365 への PST ファイルのインポートに関するよくあるご質問</span><span class="sxs-lookup"><span data-stu-id="8fe90-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="8fe90-104">**この記事は、管理者を対象としています。PST ファイルを自分のメールボックスにインポートしますか?「 [Outlook .pst ファイルからメール、連絡先、予定表をインポートする](https://go.microsoft.com/fwlink/p/?LinkID=785075)」を参照してください。**|</span><span class="sxs-lookup"><span data-stu-id="8fe90-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="8fe90-105">Office 365 インポートサービスを使用して PST ファイルを Office 365 メールボックスに一括インポートする方法についてよく寄せられる質問を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8fe90-105">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="8fe90-106">PST ファイルのインポート方法の詳細については、「 [365 Office 2010 への pst ファイルのインポートの概要](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-106">For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="8fe90-107">ネットワーク アップロードを使用して PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="8fe90-107">Using network upload to import PST files</span></span>

<span data-ttu-id="8fe90-108">詳細な手順については、「[ネットワークアップロードを使用して PST ファイルを Office 365 にインポート](use-network-upload-to-import-pst-files.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="8fe90-109">**Office 365 インポート サービスでインポート ジョブを作成するにはどのようなアクセス許可が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="8fe90-110">PST ファイルを Office 365 メールボックスにインポートするには、Exchange Online で Mailbox Import Export の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-110">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="8fe90-111">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-111">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8fe90-112">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-112">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="8fe90-113">または、新しい役割グループを作成し、Mailbox Import Export 役割を割り当て、自分や他のユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="8fe90-114">詳細については、「[Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」 (Exchange Online の役割グループの管理) の "Add a role to a role group" (役割グループに役割を追加する) または "Create a role group" (役割グループを作成する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-114">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="8fe90-115">さらに、セキュリティ/コンプライアンス センターでインポート ジョブを作成するには、次のいずれかを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-115">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="8fe90-116">Exchange Online で Mail Recipients の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-116">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="8fe90-117">既定では、この役割は Organization Management 役割グループと Recipient Management 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="8fe90-118">または</span><span class="sxs-lookup"><span data-stu-id="8fe90-118">Or</span></span>
    
- <span data-ttu-id="8fe90-119">Office 365 組織の全体の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="8fe90-120">PST ファイルを Office 365 にインポートするための新しい役割グループを Exchange Online で作成することを検討します。</span><span class="sxs-lookup"><span data-stu-id="8fe90-120">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="8fe90-121">PST ファイルをインポートするのに必要な最小レベルの権限では、新しい役割グループに Mailbox Import Export の役割および Mail Recipients の役割を割り当て、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8fe90-121">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="8fe90-122">**ネットワーク アップロードはどこで利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="8fe90-123">ネットワークアップロードは現在、米国、カナダ、ブラジル、英国、フランス、ヨーロッパ、インド、東アジア、東南アジア、日本、韓国、オーストラリアの地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-123">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="8fe90-124">Network upload will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="8fe90-124">Network upload will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="8fe90-125">現時点では、PST ファイルのネットワークアップロードはドイツおよびスイスでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-125">At this time, network upload of PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="8fe90-126">この FAQ は、ネットワークアップロードがこれらの国で利用可能になったときに更新されます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-126">This FAQ will be updated when network upload is available in these countries.</span></span>
  
 <span data-ttu-id="8fe90-127">**ネットワーク アップロードを使用して PST ファイルをインポートすると、料金はいくらですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-127">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="8fe90-128">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="8fe90-128">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="8fe90-129">つまり、PST ファイルが Azure Storage 領域から削除されると、Microsoft 365 管理センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-129">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8fe90-130">インポート ジョブは引き続き [**Office 365 へのデータのインポート**] ページに表示されることがありますが、古いインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-130">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="8fe90-131">**Office 365 へのインポートがサポートされている PST ファイル形式のバージョンは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-131">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="8fe90-132">PST ファイル形式には、ANSI と Unicode という 2 つのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-132">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="8fe90-133">Unicode PST ファイル形式を使用したファイルをインポートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fe90-133">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="8fe90-134">ただし、2 バイト文字セット (DBCS) を使用する言語のファイルのように、ANSI PST ファイル形式を使用したファイルも Office 365 にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-134">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="8fe90-135">ANSI PST ファイルのインポートの詳細については、「[ネットワークアップロードを使用して組織の pst ファイルを Office 365 にインポートする](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)」の手順4を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-135">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="8fe90-136">また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にもインポートできます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-136">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="8fe90-137">**Azure Storage 領域に PST ファイルをアップロードした後、ファイルが削除されるまで、どれくらいの期間 Azure に保持されますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-137">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="8fe90-138">ネットワーク アップロードの方法を使用して PST ファイルをインポートする場合、ファイルは **ingestiondata** という Azure の blob コンテナーにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8fe90-138">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**.</span></span> <span data-ttu-id="8fe90-139">セキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページで進捗中のインポート ジョブがない場合、一番新しいインポート ジョブが セキュリティ/コンプライアンス センター で作成されてから 30 日後に、Azure の **ingestiondata** コンテナーにあるすべての PST ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-139">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="8fe90-140">つまり、ユーザーは PST ファイルを Azure にアップロードしてから 30 日以内に、(ネットワークのアップロード手順の手順 5 で示すように) セキュリティ/コンプライアンス センター で新しいインポート ジョブを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-140">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="8fe90-141">つまり、PST ファイルが Azure Storage 領域から削除されると、セキュリティ/コンプライアンス センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-141">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="8fe90-142">インポート ジョブがセキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページの一覧に引き続き表示されていても、以前のインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-142">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="8fe90-143">**メールボックスに PST ファイルをインポートするには、どれぐらい時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-143">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="8fe90-144">ネットワークの性能によって異なりますが、一般的には組織の Azure Storage 領域にアップロードするデータ 1 TB あたり数時間かかります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-144">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="8fe90-145">PST ファイルが Azure Storage 領域にコピーされると、各 PST ファイルは 1 日あたり 24 GB 以上の速度で Office 365 のメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-145">After the PST files are copied to the Azure Storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="8fe90-146">この速度ではニーズを満たさない場合、メール データを Office 365 に移行するための他の方法も検討できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-146">If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365.</span></span> <span data-ttu-id="8fe90-147">詳細については、「[複数のメール アカウントを Office 365 に移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-147">For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="8fe90-148">複数の PST ファイルを異なる複数のメールボックスにインポートする場合、インポート プロセスは並行して実行されます。つまり、対になるそれぞれの PST とメールボックスが同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-148">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="8fe90-149">同様に、複数の PST ファイルを同じメールボックスにインポートする場合も、同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-149">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="8fe90-150">**PST ファイルをインポートするときにメッセージ サイズに制限はありますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-150">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="8fe90-151">はい。</span><span class="sxs-lookup"><span data-stu-id="8fe90-151">Yes.</span></span> <span data-ttu-id="8fe90-152">PST ファイルに 150 MB を超えるメールボックス アイテムが含まれる場合、インポート プロセスではアイテムがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-152">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="8fe90-153">**メッセージの送受信時刻や受信者のリストなどのメッセージ プロパティは、PST ファイルを Office 365 メールボックスにインポートするときに保持されますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-153">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="8fe90-154">はい。</span><span class="sxs-lookup"><span data-stu-id="8fe90-154">Yes.</span></span> <span data-ttu-id="8fe90-155">インポート プロセス中は、元のメッセージのメタデータが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-155">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="8fe90-156">**メールボックスにインポートする PST ファイルのフォルダー階層のレベルの数に制限はありますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-156">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="8fe90-p115">はい。300 以上のネストされたフォルダーのレベルを持つ PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-p115">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="8fe90-159">**ネットワーク アップロードを使用して PST ファイルを Office 365 の非アクティブなメールボックスにインポートすることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-159">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="8fe90-160">Yes, this capability is now available. </span><span class="sxs-lookup"><span data-stu-id="8fe90-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="8fe90-161">**ネットワーク アップロードを使用して、Exchange ハイブリッド展開のオンライン アーカイブ メールボックスに PST ファイルをインポートできますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-161">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="8fe90-162">はい、この機能は現在利用できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="8fe90-162">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="8fe90-163">**ネットワーク アップロードを使用して PST ファイルを Exchange Online のパブリック フォルダーにインポートできますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-163">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="8fe90-164">いいえ、PST ファイルをパブリック フォルダーにはインポートできません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-164">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="8fe90-165">ドライブ送付を使用して PST ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="8fe90-165">Using drive shipping to import PST files</span></span>

<span data-ttu-id="8fe90-166">詳細な手順については、「 [drive 送料を使用して PST ファイルを Office 365 にインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-166">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="8fe90-167">**Office 365 インポート サービスでインポート ジョブを作成するにはどのようなアクセス許可が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-167">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="8fe90-168">PST ファイルを Office 365 メールボックス にインポートするには、Mailbox Import Export の役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-168">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="8fe90-169">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-169">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="8fe90-170">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-170">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="8fe90-171">または、新しい役割グループを作成し、Mailbox Import Export 役割を割り当て、自分や他のユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-171">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="8fe90-172">詳細については、「[Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)」 (Exchange Online の役割グループの管理) の "Add a role to a role group" (役割グループに役割を追加する) または "Create a role group" (役割グループを作成する) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-172">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="8fe90-173">さらに、セキュリティ/コンプライアンス センターでインポート ジョブを作成するには、次のいずれかを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-173">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="8fe90-174">Exchange Online で Mail Recipients の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-174">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="8fe90-175">既定では、この役割は Organization Management 役割グループと Recipient Management 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-175">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="8fe90-176">または</span><span class="sxs-lookup"><span data-stu-id="8fe90-176">Or</span></span>
    
- <span data-ttu-id="8fe90-177">Office 365 組織の全体の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-177">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="8fe90-178">PST ファイルを Office 365 にインポートするための新しい役割グループを Exchange Online で作成することを検討します。</span><span class="sxs-lookup"><span data-stu-id="8fe90-178">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="8fe90-179">PST ファイルをインポートするのに必要な最小レベルの権限では、新しい役割グループに Mailbox Import Export の役割および Mail Recipients の役割を割り当て、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8fe90-179">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="8fe90-180">**ドライブ送付はどこで利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-180">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="8fe90-181">現在のところ、ドライブ送付は米国、カナダ、ブラジル、イギリス、欧州、インド、東アジア、東南アジア、日本、韓国、オーストラリアでご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-181">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="8fe90-182">ドライブ送付はその他の地域でも間もなくご利用いただけるようになります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-182">Drive shipping will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="8fe90-183">現時点では、PST ファイルをインポートするためのドライブ配布は、ドイツおよびスイスでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-183">At this time, drive shipping to import PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="8fe90-184">この FAQ は、ドライブの配送がこれらの国で利用可能になったときに更新されます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-184">This FAQ will be updated when drive shipping is available in these countries.</span></span>
  
 <span data-ttu-id="8fe90-185">**ドライブ送付をサポートする商用の使用許諾契約は何ですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-185">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="8fe90-186">Office 365 に PST ファイルをインポートするためのドライブ送付は Microsoft Enterprise Agreement (EA) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-186">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="8fe90-187">Microsoft Products and Services Agreement (MPSA) では、ドライブ送付はご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-187">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="8fe90-188">**ドライブの発送を使用して PST ファイルを Office 365 にインポートすると、料金はいくらですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-188">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="8fe90-189">ドライブの発送を使用して PST ファイルを Office 365 メールボックスにインポートするコストは、1 GB のデータあたり 2 米ドルです。</span><span class="sxs-lookup"><span data-stu-id="8fe90-189">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="8fe90-190">たとえば、1,000 GB (1 TB) の PST ファイルを含むハード ディスク ドライブを発送する場合のコストは、2,000 米ドルです。</span><span class="sxs-lookup"><span data-stu-id="8fe90-190">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="8fe90-191">インポート手数料は、パートナーと分担して支払うことができます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-191">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="8fe90-192">パートナーを探す方法については、「[Office 365 パートナーまたは販売店を探す](https://go.microsoft.com/fwlink/p/?LinkId=785197)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-192">For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="8fe90-193">**ドライブ発送では、どのような種類のハード ドライブがサポートされていますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-193">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="8fe90-194">Office 365 インポート サービスでは、2.5 インチのソリッドステート ドライブ (SSD) または 2.5 インチまたは 3.5 インチの SATA II/III 内部ハード ドライブのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8fe90-194">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="8fe90-195">最大で 10 TB のハード ドライブを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-195">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="8fe90-196">インポート ジョブでは、ハード ドライブの最初のデータ ボリュームのみが処理されます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-196">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="8fe90-197">このデータ ボリュームは、NTFS でフォーマットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-197">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="8fe90-198">データをハード ドライブにコピーする場合、2.5 インチ SSD、2.5 または 3.5 インチ SATA II/III コネクタを使用して直接接続するか、外部 2.5 インチ SSD、2.5 または 3.5 インチ SATA II/III USB アダプターを使用して外付けできます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-198">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8fe90-199">Office 365 インポート サービスでは、USB アダプターが内蔵されている外部ハード ドライブはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-199">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="8fe90-200">また、外部ハード ドライブのケース内にあるディスクは使用できません</span><span class="sxs-lookup"><span data-stu-id="8fe90-200">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="8fe90-201">外部ハード ドライブは発送しないでください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-201">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="8fe90-202">**1 回のインポート ジョブで発送できるハード ディスク ドライブの数はいくつですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-202">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="8fe90-203">1 回のインポート ジョブで最大 10 台のハード ディスク ドライブを発送できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-203">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="8fe90-204">**ハードドライブを送付した後、Microsoft データ センターに到着するまでどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-204">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="8fe90-p125">いくつかの要因によって決まります。Microsoft データ センターからの距離や、ハード ディスク ドライブを発送するために使用した発送オプションの種類 (翌日到、着翌々日到着、数日後到着) などです。ほとんどの運送会社で追跡番号を利用し、発送状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-p125">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="8fe90-207">**Microsoft のデータ センターにハード ドライブが到着してから PST ファイルが Azure にアップロードされるまで、どれくらいかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-207">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="8fe90-208">Microsoft データセンターでハードドライブを受信した後は、組織の Azure ストレージ領域に PST ファイルをアップロードするために、7 ~ 10 営業日かかります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-208">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage area for your organization.</span></span> <span data-ttu-id="8fe90-209">PST ファイルは、 **ingestiondata**という名前の Azure blob コンテナーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-209">The PST files will be uploaded to an Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="8fe90-210">**メールボックスに PST ファイルをインポートするには、どれぐらい時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-210">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="8fe90-211">PST ファイルが Azure Storage 領域にアップロードされると、Office 365 が (セキュリティで保護された安全な方法で) PST ファイル内のデータを分析して、アイテムの経過時間と、PST ファイルに含まれるさまざまなメッセージの種類を識別します。</span><span class="sxs-lookup"><span data-stu-id="8fe90-211">After the PST files are uploaded to the Azure Storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="8fe90-212">この分析が完了したら、PST ファイルのすべてのデータをインポートしたり、フィルターを設定してインポートするデータを制御したりできます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-212">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="8fe90-213">インポート ジョブを開始した後、PST ファイルは 1 日に少なくとも 24 GB の速さで Office 365 メールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-213">After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="8fe90-214">このレートでは要件を満たさない場合は、メール データを Office 365 にインポートするための別の方法も検討できます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-214">If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365.</span></span> <span data-ttu-id="8fe90-215">詳細については、「[複数のメール アカウントを Office 365 に移行する方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-215">For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="8fe90-216">複数の PST ファイルを異なる複数のメールボックスにインポートする場合、インポート プロセスは並行して実行されます。つまり、対になるそれぞれの PST とメールボックスが同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-216">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="8fe90-217">同様に、複数の PST ファイルを同じメールボックスにインポートする場合も、同時にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-217">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="8fe90-218">**Microsoft が私の PST ファイルを Azure にアップロードした後、削除されるまで、どのくらいの期間 Azure に保持されますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-218">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="8fe90-219">**Ingestiondata**という名前の blob コンテナー内の組織の Azure ストレージの場所にあるすべての pst ファイルは、最新のインポートジョブが、セキュリティ & コンプライアンスセンターの [ **PST ファイルのインポート**] ページで作成されてから30日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-219">All PST files in the Azure Storage location for your organization (in blob container named **ingestiondata**), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="8fe90-220">つまり、PST ファイルが Azure Storage 領域から削除されると、セキュリティ/コンプライアンス センターでは、完了済みインポート ジョブのファイル一覧から PST ファイルの表示が消えます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-220">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="8fe90-221">インポート ジョブがセキュリティ/コンプライアンス センター の [**PST ファイルのインポート**] ページの一覧に引き続き表示されていても、以前のインポート ジョブの詳細を表示すると、PST ファイルの一覧は空になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-221">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="8fe90-222">**Office 365 へのインポートがサポートされている PST ファイル形式のバージョンは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-222">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="8fe90-223">PST ファイル形式には、ANSI と Unicode という 2 つのバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-223">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="8fe90-224">Unicode PST ファイル形式を使用したファイルをインポートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fe90-224">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="8fe90-225">ただし、2 バイト文字セット (DBCS) を使用する言語のファイルのように、ANSI PST ファイル形式を使用したファイルも Office 365 にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-225">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="8fe90-226">ANSI PST ファイルのインポートの詳細については、「 [Use drive 送料 To Office 365 に PST ファイルをインポートする](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)」の手順3を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe90-226">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="8fe90-227">また、Outlook 2007 以降のバージョンの PST ファイルを Office 365 にもインポートできます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-227">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="8fe90-228">**PST ファイルをインポートするときにメッセージ サイズに制限はありますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-228">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="8fe90-229">はい。</span><span class="sxs-lookup"><span data-stu-id="8fe90-229">Yes.</span></span> <span data-ttu-id="8fe90-230">PST ファイルに 150 MB を超えるメールボックス アイテムが含まれる場合、インポート プロセスではアイテムがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-230">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="8fe90-231">**メッセージの送受信時刻や受信者のリストなどのメッセージ プロパティは、PST ファイルを Office 365 メールボックスにインポートするときに保持されますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-231">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="8fe90-232">はい。</span><span class="sxs-lookup"><span data-stu-id="8fe90-232">Yes.</span></span> <span data-ttu-id="8fe90-233">インポート プロセス中は、元のメッセージのメタデータが変更されることはありません</span><span class="sxs-lookup"><span data-stu-id="8fe90-233">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="8fe90-234">**メールボックスにインポートする PST ファイルのフォルダー階層のレベルの数に制限はありますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-234">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="8fe90-p133">はい。300 以上のネストされたフォルダーのレベルを持つ PST ファイルをインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-p133">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="8fe90-237">\*\*ドライブ発送を使用して PST ファイルを Office 365 の非アクティブなメールボックスにインポートすることはできますか? \*\*</span><span class="sxs-lookup"><span data-stu-id="8fe90-237">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="8fe90-238">Yes, this capability is now available.</span><span class="sxs-lookup"><span data-stu-id="8fe90-238">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="8fe90-239">**ドライブの発送を使用して、Exchange ハイブリッド展開のオンライン アーカイブ メールボックスに PST ファイルをインポートできますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-239">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="8fe90-240">はい、この機能は現在利用できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="8fe90-240">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="8fe90-241">**ドライブの発送を使用して PST ファイルを Exchange Online のパブリック フォルダーにインポートできますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-241">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="8fe90-242">いいえ、PST ファイルをパブリック フォルダーにはインポートできません。</span><span class="sxs-lookup"><span data-stu-id="8fe90-242">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="8fe90-243">**Microsoft からハード ディスク ドライブが返送される前に、Microsoft はハード ディスク ドライブのデータを消去できますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-243">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="8fe90-p134">いいえ、Microsoft がお客様にハード ディスク ドライブを返送する前にデータを消去することはできません。ハード ディスク ドライブは、Microsoft が受け取ったときと同じ状態で返送されます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-p134">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="8fe90-246">**Microsoft がハード ディスクを返送せずに処分してもかまいませんか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-246">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="8fe90-p135">いいえ、Microsoft はお客様のハード ディスク ドライブを破壊することはできません。ハード ディスク ドライブは、Microsoft が受け取ったときと同じ状態で返送されます。</span><span class="sxs-lookup"><span data-stu-id="8fe90-p135">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="8fe90-249">**返送時はどの宅配会社を利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-249">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="8fe90-p136">米国またはヨーロッパのお客様には FedEx を使ってハード ディスク ドライブを送り返します。その他すべての地域向けには、DHL を使用します。</span><span class="sxs-lookup"><span data-stu-id="8fe90-p136">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="8fe90-252">**返送の料金はいくらですか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-252">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="8fe90-p137">返送料金は、ハード ディスク ドライブ送付先の Microsoft データ センターからの距離によって決まります。ハード ドライブの返送料は、お客様の FedEx または DHL アカウントに請求されます。返送料はお客様のご負担となります。</span><span class="sxs-lookup"><span data-stu-id="8fe90-p137">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="8fe90-256">**Microsoft にハード ディスクを送付するとき、FedEx カスタム送付などの宅配会社のカスタム出荷サービスを使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="8fe90-256">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="8fe90-257">はい。</span><span class="sxs-lookup"><span data-stu-id="8fe90-257">Yes.</span></span>
  
 <span data-ttu-id="8fe90-258">\*\*ハード ドライブを別の国に送付しなければならない場合、何か必要な手続きはありますか? \*\*</span><span class="sxs-lookup"><span data-stu-id="8fe90-258">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="8fe90-p138">Microsoft 宛てに発送するハード ディスク ドライブは、国境を越える場合があります。この場合、ハード ディスク ドライブとドライブに含まれているデータが、輸出入に関して適用される法律に違反しないことを保証するのはお客様の責任になります。ハード ディスク ドライブを発送する前に、指定した Microsoft データ センターへのディスクとデータの送付について、法律違反事項がないことを助言者に確認してください。こうすることで、ドライブが Microsoft に適時に到着します。</span><span class="sxs-lookup"><span data-stu-id="8fe90-p138">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
