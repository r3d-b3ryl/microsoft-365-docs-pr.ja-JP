---
title: Office 365 の管理者として検疫済みメッセージおよびファイルを管理する
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 09/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: '管理者は、Office 365 で誤検知済みの肯定メッセージを表示、リリース、および報告することができます。 Office 365 がメッセージをフィルター処理して、複数の理由で検疫にメッセージを送信するようにポリシーを設定できます。これは、スパム、バルク、フィッシング、マルウェア、またはメールフロールールと一致したためです。 '
ms.openlocfilehash: 615d88f63f738ca443b9ff377bb08fdaa97fe2dc
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970935"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a><span data-ttu-id="225c4-104">Office 365 の管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="225c4-104">Manage quarantined messages and files as an administrator in Office 365</span></span>

<span data-ttu-id="225c4-105">管理者は、検疫済みメッセージを表示、解放、および削除し、Office 365 で誤検知された肯定メッセージを報告することができます。</span><span class="sxs-lookup"><span data-stu-id="225c4-105">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365.</span></span> <span data-ttu-id="225c4-106">SharePoint Online、OneDrive for Business、Microsoft Teams の詳細な脅威保護 (ATP) によってキャプチャされた検疫済みファイルの表示、ダウンロード、削除を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="225c4-106">You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="225c4-107">Office 365 がメッセージをフィルター処理して、いくつかの理由で検疫にメッセージを送信するようにポリシーを設定できます。これは、スパム、バルクメール、フィッシングメール、マルウェアを含む、またはメールフロールールに一致したためです。</span><span class="sxs-lookup"><span data-stu-id="225c4-107">You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>

<span data-ttu-id="225c4-108">既定では、Office 365 は、フィッシング詐欺メッセージとマルウェアを含むメッセージを検疫に直接送信します。</span><span class="sxs-lookup"><span data-stu-id="225c4-108">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine.</span></span> <span data-ttu-id="225c4-109">その他のフィルター処理されたメッセージは、検疫に送信するポリシーを設定しない限り、ユーザーの迷惑メールフォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-109">Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>

<span data-ttu-id="225c4-110">検疫済みメッセージや検疫されたファイルを操作するには、Office 365 でグローバル管理者 (GA) のアクセス許可を持っているか、または1つ以上のセキュリティ & コンプライアンスセンターの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c4-110">You must have global administrator (GA) permissions in Office 365, or be a member of one or more Security & Compliance Center role groups, to work with quarantined messages or quarantined files.</span></span> <span data-ttu-id="225c4-111">詳細について[は、「Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center) 」の「アクセス許可」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c4-111">See [Permissions in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center) for more information.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="225c4-112">既定では、スパム、バルクメッセージ、およびフィッシングメッセージは、30日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-112">By default, spam, bulk and phishing messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="225c4-113">メールフロールールに一致したために検疫されたメッセージは、7日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-113">Messages that are quarantined because they matched a mail flow rule are kept in quarantine for 7 days.</span></span> <span data-ttu-id="225c4-114">マルウェアメッセージは、15日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-114">Malware messages are kept in quarantine for 15 days.</span></span> <span data-ttu-id="225c4-115">セキュリティ & コンプライアンスセンターのスパム対策設定でスパム検疫時間をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="225c4-115">You can customize the spam quarantine time in anti-spam settings in the Security & Compliance Center.</span></span> <span data-ttu-id="225c4-116">Office 365 で検疫からメッセージが削除されると、元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="225c4-116">When Office 365 deletes a message from quarantine, you can't get it back.</span></span> <span data-ttu-id="225c4-117">必要に応じて、スパム対策フィルターポリシーの検疫済みメッセージの保持期間を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="225c4-117">If you like, you can change the retention period for quarantined messages in your anti-spam filter policies.</span></span> <span data-ttu-id="225c4-118">詳細については、「[検疫の保存期間の設定](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c4-118">For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="225c4-119">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="225c4-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="225c4-120">検疫はセキュリティ & コンプライアンスセンターに含まれていますが、検疫内のメッセージを管理するためのアクセス許可は、 **Exchange Online**役割グループのメンバーシップによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-120">Although the quarantine is in the Security & Compliance Center, the permissions to manage messages in the quarantine are controlled by membership in **Exchange Online** role groups.</span></span> <span data-ttu-id="225c4-121">Exchange Online の役割グループの詳細については、「 [Manage role groups In Exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c4-121">For more information about role groups in Exchange Online, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="225c4-122">検疫ファイルを管理するためのアクセス許可を付与する Exchange Online 役割グループは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="225c4-122">The Exchange Online role groups that give permissions to manage quarantine files are:</span></span>

- <span data-ttu-id="225c4-123">**組織の管理**: グローバル管理者は、自動的にこのグループのメンバーになります。</span><span class="sxs-lookup"><span data-stu-id="225c4-123">**Organization Management**: Global admins are automatically members of this group.</span></span>

- <span data-ttu-id="225c4-124">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="225c4-124">**Security Administrator**</span></span>

- <span data-ttu-id="225c4-125">**検疫管理**</span><span class="sxs-lookup"><span data-stu-id="225c4-125">**Hygiene Management**</span></span>

<span data-ttu-id="225c4-126">検疫ファイルを表示するためのアクセス許可を付与する Exchange Online 役割グループは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="225c4-126">The Exchange Online role groups that give permissions to view quarantine files are:</span></span>

- <span data-ttu-id="225c4-127">**View-Only Organization Management**</span><span class="sxs-lookup"><span data-stu-id="225c4-127">**View-Only Organization Management**</span></span>

- <span data-ttu-id="225c4-128">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="225c4-128">**Security Reader**</span></span>

## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="225c4-129">組織の検疫済みメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="225c4-129">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="225c4-130">Office 365 組織のグローバル管理者特権 (または適切なセキュリティ & コンプライアンスセンターの役割) を持つ職場または学校のアカウントを使用して、Office 365 にサインインし、[セキュリティ/コンプライアンスセンターに移動](../../compliance/go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="225c4-130">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign into Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="225c4-131">左側のリストで、[脅威の**管理**] を展開し、[**確認**] を選択してから、[**検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-131">In the list on the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

    > [!TIP]
    > <span data-ttu-id="225c4-132">セキュリティ & コンプライアンスセンターの [**検疫**] ページに直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="225c4-132">To go directly to the **Quarantine** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

    <span data-ttu-id="225c4-133">既定では、セキュリティ & コンプライアンスセンターには、スパムとして検疫されたすべての電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-133">By default, the Security & Compliance Center displays all email messages that have been quarantined as spam.</span></span> <span data-ttu-id="225c4-134">メッセージは、受信の [**日付**] に基づいて、最新のものから順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="225c4-134">The messages are sorted from newest to oldest based on the **Date** the message was received.</span></span> <span data-ttu-id="225c4-135">各メッセージに [**送信者**]、[**件名**]、および有効期限 ([**有効期限**]) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-135">**Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message.</span></span> <span data-ttu-id="225c4-136">特定のフィールドで並べ替えるには、その列見出しをクリックします。列見出しをもう一度クリックすると、逆の順番に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="225c4-136">You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span>

3. <span data-ttu-id="225c4-137">すべての検疫済みメッセージの一覧を表示したり、フィルター処理によって結果セットを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="225c4-137">You can view a list of all quarantined messages, or you can reduce the result set by filtering.</span></span> <span data-ttu-id="225c4-138">一括操作は 100 件以下のアイテムにのみ実行できます。そのため、100 件を越える場合は、フィルターを使って結果セットを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="225c4-138">You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that.</span></span> <span data-ttu-id="225c4-139">ページの上部にあるフィルタからオプションを選択することにより、1つの検査理由により、メッセージを簡単にフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-139">You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page.</span></span> <span data-ttu-id="225c4-140">オプションは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="225c4-140">Options include:</span></span>

   - <span data-ttu-id="225c4-141">スパムとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="225c4-141">Mail identified as spam</span></span>

   - <span data-ttu-id="225c4-142">メールフロールール (トランスポートルールとも呼ばれる) によって設定されたポリシーに一致したため、メールが隔離されている</span><span class="sxs-lookup"><span data-stu-id="225c4-142">Mail quarantined because it matched a policy set by a mail flow rule (also known as a transport rule)</span></span>

   - <span data-ttu-id="225c4-143">バルクメールとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="225c4-143">Mail identified as bulk mail</span></span>

   - <span data-ttu-id="225c4-144">フィッシングメールとして識別されたメール</span><span class="sxs-lookup"><span data-stu-id="225c4-144">Mail identified as phishing mail</span></span>

   - <span data-ttu-id="225c4-145">マルウェアを含むメールの検疫</span><span class="sxs-lookup"><span data-stu-id="225c4-145">Mail quarantined because it contains malware</span></span>

<span data-ttu-id="225c4-146">さらに、管理者として、組織のすべてのメッセージをフィルター処理するか、自分に送信されたメッセージのみをフィルター処理するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-146">In addition, as an admin, you can choose to filter all messages for your organization or only messages sent to you.</span></span> <span data-ttu-id="225c4-147">エンドユーザーは、それらに送信されたメッセージの表示と操作のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="225c4-147">End users can only view and work with messages sent to them.</span></span>

<span data-ttu-id="225c4-148">特定のメッセージを検索するために結果をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="225c4-148">You can also filter your results to find specific messages.</span></span> <span data-ttu-id="225c4-149">ヒントについては、この記事の「[結果をフィルター処理して、検疫済みのメッセージおよびファイルを検索するに](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)は」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c4-149">For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span>

<span data-ttu-id="225c4-150">特定の検疫済みメッセージを見つけた後、メッセージをクリックしてそのメッセージの詳細を表示し、他のユーザーのメールボックスにメッセージを解放するなどのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="225c4-150">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's mailbox.</span></span>

## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="225c4-151">組織の検疫済みファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="225c4-151">View your organization's quarantined files</span></span>

1. <span data-ttu-id="225c4-152">Office 365 組織のグローバル管理者特権 (または適切なセキュリティ & コンプライアンスセンターの役割) を持つ職場または学校のアカウントを使用して、Office 365 にサインインし、[セキュリティ/コンプライアンスセンターに移動](../../compliance/go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="225c4-152">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="225c4-153">左側の [**脅威の管理**] を展開し、[**確認**] を選択して、[**検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-153">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>

   > [!TIP]
   > <span data-ttu-id="225c4-154">セキュリティ & コンプライアンスセンターの [**検疫**] ページに直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="225c4-154">To go directly to the **Quarantine** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>

3. <span data-ttu-id="225c4-155">既定では、ページには検疫された電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-155">By default, the page displays quarantined email messages.</span></span> <span data-ttu-id="225c4-156">検疫されたファイルを表示するには、ページの上部にあるフィルターを、**マルウェア**によって検疫された**ファイル**を表示するように設定します。</span><span class="sxs-lookup"><span data-stu-id="225c4-156">To view quarantined files, set the filters at the top of the page to show **files**, quarantined due to **malware**.</span></span> <span data-ttu-id="225c4-157">検疫済みファイルを操作するには、Office 365 で管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c4-157">You must have admin permissions in Office 365 to work with quarantined files.</span></span>

4. <span data-ttu-id="225c4-158">ファイルは、ファイルが検疫された日付に基づいて、最新から最古の順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="225c4-158">The files are sorted from newest to oldest based on the date the file was quarantined.</span></span> <span data-ttu-id="225c4-159">ファイルを最後に変更した**ユーザー** 、ファイルが投稿された**サービス**、ファイル**名**、**場所**、**ファイルのサイズ**、有効期限 (**有効**期限) は、各ファイルにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-159">The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file.</span></span> <span data-ttu-id="225c4-160">ヘッダーをクリックすることで、フィールドに対して並べ替えを行うことができます。並べ替え順序を逆にするには、列見出しをもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="225c4-160">You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>

<span data-ttu-id="225c4-161">検疫されたすべてのファイルの一覧を表示することも、フィルター処理によって特定のファイルを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="225c4-161">You can view a list of all quarantined files, or you can search for specific files by filtering.</span></span> <span data-ttu-id="225c4-162">メッセージと同様に、一括操作は最大100アイテムに対してのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-162">Just like messages, you can only do bulk operations on up to 100 items.</span></span> <span data-ttu-id="225c4-163">現在、セキュリティ & コンプライアンスセンターでは、マルウェアが含まれていると識別されるため、検疫内のファイルを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-163">Currently, the Security & Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware.</span></span> <span data-ttu-id="225c4-164">ヒントについては、この記事の「[結果をフィルター処理して、検疫済みのメッセージおよびファイルを検索するに](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)は」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c4-164">For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span>

## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a><span data-ttu-id="225c4-165">結果をフィルター処理して、検疫済みのメッセージおよびファイルを検索するには</span><span class="sxs-lookup"><span data-stu-id="225c4-165">To filter results and find quarantined messages and files</span></span>
<span data-ttu-id="225c4-166"><a name="BKMK_AdvSearch"> </a></span><span class="sxs-lookup"><span data-stu-id="225c4-166"></span></span>

<span data-ttu-id="225c4-167">設定によっては、検疫されたメッセージとファイルが多数存在することがあります。</span><span class="sxs-lookup"><span data-stu-id="225c4-167">Depending on your settings, there may be a lot of quarantined messages and files.</span></span> <span data-ttu-id="225c4-168">特定のメッセージまたはファイル、あるいは一連のメッセージまたはファイルを検索するには、さまざまな追加情報に基づいて検疫済みアイテムをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-168">To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>

1. <span data-ttu-id="225c4-169">[**検疫**] ページで、フィルターの先頭行が、必要に応じてメッセージまたはファイルを表示するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="225c4-169">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span>

   - <span data-ttu-id="225c4-170">ファイルを検索するには、**マルウェア**によって検疫された**ファイル**を表示するようにフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="225c4-170">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span>

     <span data-ttu-id="225c4-171">検疫されたファイルの場合、ページには、表示するように指示されているかどうかにかかわらず、自分だけでなく、すべての検疫済みファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-171">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>

   - <span data-ttu-id="225c4-172">検疫済みメッセージを検索する**には、** **すべて**の**メール**を表示するようにフィルターを設定します。</span><span class="sxs-lookup"><span data-stu-id="225c4-172">To search for quarantined messages, set filters to show **all** or **only my** **email**.</span></span> <span data-ttu-id="225c4-173">最後のフィルターの場合は、探している検疫済みメッセージの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-173">For the last filter choose the type of quarantined message that you're looking for.</span></span> <span data-ttu-id="225c4-174">メールフロールール (**トランスポートルール**)、**バルク**メール、**フィッシング**メール、または**マルウェア**を含むメールに一致するメッセージに対して、**スパム**として識別された検疫済みメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-174">You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow rule (**transport rule**), **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>

2. <span data-ttu-id="225c4-175">[**結果の並べ替え**] で、ドロップダウンリストから検索するために使用するフィルターを選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-175">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists.</span></span> <span data-ttu-id="225c4-176">オプションは、ファイルまたはメッセージを検索するかどうかに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="225c4-176">The options vary based on whether you are searching for files or messages.</span></span> <span data-ttu-id="225c4-177">この時点では、検索フィールドではワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="225c4-177">Wildcards are not supported in search fields at this time.</span></span>

   <span data-ttu-id="225c4-178">ファイルとメッセージの両方について、メッセージまたはファイルが検疫に送信された日付によってフィルター処理することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-178">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine.</span></span> <span data-ttu-id="225c4-179">日付または日付範囲を指定することができます (時間も指定できます)。</span><span class="sxs-lookup"><span data-stu-id="225c4-179">You can specify the date or a date range, including the time.</span></span> <span data-ttu-id="225c4-180">また、ファイルまたはメッセージが検疫から削除される有効期限の日付で検索結果をフィルター処理したり、フィルターの組み合わせを使用したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="225c4-180">You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters.</span></span> <span data-ttu-id="225c4-181">有効期限を指定して検索するには、[**高度なフィルター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-181">To search by expiration date, choose **Advanced filter**.</span></span> <span data-ttu-id="225c4-182">[**有効期限**] の下で、次の週に、今後24時間以内 (**今日**48)、次の週 (次の**7\*\*\*\*日)** 以内に削除するメッセージを選択できます。または、カスタムの時間間隔を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="225c4-182">Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>

   <span data-ttu-id="225c4-183">メッセージの場合は、次の追加オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="225c4-183">For messages, you have the following additional options:</span></span>

   - <span data-ttu-id="225c4-184">**メッセージ id**: メッセージ id がわかっている場合に、このメッセージを使用して特定のメッセージを特定します。</span><span class="sxs-lookup"><span data-stu-id="225c4-184">**Message ID**: Use this to identify a specific message when you know the message ID.</span></span>

     <span data-ttu-id="225c4-185">たとえば、目的のメッセージの送信者または宛先が組織内のユーザーで、宛先に届かない場合、メッセージ追跡を使用してメッセージを検索できます (「[セキュリティ/コンプライアンス センターのメッセージ追跡](message-trace-scc.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="225c4-185">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Message trace in the Security & Compliance Center](message-trace-scc.md)).</span></span> <span data-ttu-id="225c4-186">メッセージが検疫に送信されたことがわかった場合は、メールフロールールと一致した、またはスパムとして識別されたために、メッセージ ID を指定することによって、このメッセージを検疫で簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="225c4-186">If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID.</span></span> <span data-ttu-id="225c4-187">完全なメッセージ ID 文字列を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="225c4-187">Be sure to include the full message ID string.</span></span> <span data-ttu-id="225c4-188">メッセージ ID には、次のように、山かっこ (\<\>) が含まれる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="225c4-188">This might include angle brackets (\<\>), for example:</span></span>

     `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`

   - <span data-ttu-id="225c4-189">[**送信者のメール アドレス**] 1 つの送信者のメール アドレスによってフィルター処理する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-189">**Sender email address**: Choose to filter by a single sender email address.</span></span>

   - <span data-ttu-id="225c4-190">[**受信者のメール アドレス**] 1 つの受信者のメール アドレスによってフィルター処理する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-190">**Recipient email address**: Choose to filter by a single recipient email address.</span></span>

   - <span data-ttu-id="225c4-191">[**件名**] 検索するメール アドレスの件名を入力します。</span><span class="sxs-lookup"><span data-stu-id="225c4-191">**Subject**: Enter the subject of an email address you want to find.</span></span> <span data-ttu-id="225c4-192">ワイルドカード検索はサポートされていないため、検索でメッセージを結果に返すためには、メッセージの件名全体を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c4-192">Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results.</span></span> <span data-ttu-id="225c4-193">検索では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="225c4-193">The search is not case-sensitive.</span></span>

## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="225c4-194">検疫されたメッセージとファイルの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="225c4-194">View details about quarantined messages and files</span></span>

<span data-ttu-id="225c4-195">検疫リストに表示されているアイテムを選択すると、セキュリティ & コンプライアンスセンターの右側の**詳細**ウィンドウに、そのプロパティの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-195">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security & Compliance Center.</span></span>

### <a name="details-displayed-for-quarantined-messages"></a><span data-ttu-id="225c4-196">検疫済みメッセージに関して表示される詳細情報</span><span class="sxs-lookup"><span data-stu-id="225c4-196">Details displayed for quarantined messages</span></span>

- <span data-ttu-id="225c4-197">[**メッセージ ID**] メッセージの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="225c4-197">**Message ID**: The unique identifier for the message.</span></span>

- <span data-ttu-id="225c4-198">[**送信者のアドレス**] メッセージの送信者。</span><span class="sxs-lookup"><span data-stu-id="225c4-198">**Sender Address**: Who sent the message.</span></span>

- <span data-ttu-id="225c4-199">**Received**: メッセージが受信された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="225c4-199">**Received**: The date and time the message was received.</span></span>

- <span data-ttu-id="225c4-200">**Subject**: メッセージの件名行のテキスト。</span><span class="sxs-lookup"><span data-stu-id="225c4-200">**Subject**: The text of the subject line of the message.</span></span>

- <span data-ttu-id="225c4-201">**型**: メッセージが**スパム**、 **Bulk**、**フィッシング**、またはメールフロールール (**トランスポートルール**) に一致したか、または**マルウェア**が含まれていると識別されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="225c4-201">**Type**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="225c4-202">[**有効期限**]: 検疫からメッセージが自動的に削除される日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="225c4-202">**Expires**: The date and time when the message will automatically be deleted from quarantine.</span></span>

- <span data-ttu-id="225c4-203">[**解放済み**] メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="225c4-203">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="225c4-204">まだリリースされて**いない**: メッセージがまだ解放されていないすべての電子メールアドレス (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="225c4-204">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="details-displayed-for-quarantined-files"></a><span data-ttu-id="225c4-205">検疫されたファイルの詳細情報</span><span class="sxs-lookup"><span data-stu-id="225c4-205">Details displayed for quarantined files</span></span>

- <span data-ttu-id="225c4-206">**ファイル名**検疫に含まれるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="225c4-206">**File Name** The name of the file in quarantine.</span></span>

- <span data-ttu-id="225c4-207">**サイトパス**Office 365 でのファイルの場所を定義する URL。</span><span class="sxs-lookup"><span data-stu-id="225c4-207">**Site path** URL that defines the location of the file in Office 365.</span></span>

- <span data-ttu-id="225c4-208">**検出された日付/時刻**ファイルが検疫された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="225c4-208">**Detected Date / Time** The date and time the file was quarantined.</span></span>

- <span data-ttu-id="225c4-209">**期限切れ**メッセージが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="225c4-209">**Expires** The date when the message will be deleted from quarantine.</span></span>

- <span data-ttu-id="225c4-210">**検出者**ファイル内のマルウェアを検出するために使用されるメソッド。</span><span class="sxs-lookup"><span data-stu-id="225c4-210">**Detected By** The method used to detect the malware in the file.</span></span> <span data-ttu-id="225c4-211">ATP (Advanced Threat Protection) または Microsoft のマルウェア対策エンジンのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-211">This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="225c4-212">**リリース**ファイルがリリースされているかどうかを表します。</span><span class="sxs-lookup"><span data-stu-id="225c4-212">**Released** Describes whether or not the file has been released.</span></span>

- <span data-ttu-id="225c4-213">**マルウェアの名前**ファイル内で検出されたマルウェアのファミリと名前。</span><span class="sxs-lookup"><span data-stu-id="225c4-213">**Malware Name** Family and name of the malware detected in the file.</span></span>

- <span data-ttu-id="225c4-214">**ドキュメント ID**ドキュメントの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="225c4-214">**Document ID** A unique identifier for the document.</span></span>

- <span data-ttu-id="225c4-215">**ファイルサイズ**ファイルのサイズ (KB 単位)。</span><span class="sxs-lookup"><span data-stu-id="225c4-215">**File Size** The size of the file in KB.</span></span>

- <span data-ttu-id="225c4-216">**組織**Office 365 の組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="225c4-216">**Organization** Your organization's unique ID in Office 365.</span></span>

- <span data-ttu-id="225c4-217">**更新者**ファイルを最後に変更したユーザーの職場または学校のアカウント。</span><span class="sxs-lookup"><span data-stu-id="225c4-217">**Modified By** The work or school account of the user who last modified the file.</span></span>

- <span data-ttu-id="225c4-218">**ファイルサイズ**ファイルのサイズ (KB 単位)。</span><span class="sxs-lookup"><span data-stu-id="225c4-218">**File Size** The size of the file in KB.</span></span>

- <span data-ttu-id="225c4-219">**SHA256 ハッシュ**ファイルのハッシュ。</span><span class="sxs-lookup"><span data-stu-id="225c4-219">**SHA256 Hash** The hash of the file.</span></span> <span data-ttu-id="225c4-220">これを使用して、他の評価ストアを検索することもできます。または、ファイルが環境内に存在する可能性があることを調査します。</span><span class="sxs-lookup"><span data-stu-id="225c4-220">You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span>

## <a name="managing-messages-and-files-in-quarantine"></a><span data-ttu-id="225c4-221">検疫でのメッセージとファイルの管理</span><span class="sxs-lookup"><span data-stu-id="225c4-221">Managing messages and files in quarantine</span></span>
<span data-ttu-id="225c4-222"><a name="BKMK_ManageQuarantinedItem"> </a></span><span class="sxs-lookup"><span data-stu-id="225c4-222"></span></span>

<span data-ttu-id="225c4-223">メッセージまたはメッセージのグループを選択したら、検疫内のメッセージを管理するためのいくつかのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-223">After you select a message or group of messages you have several options for managing messages in quarantine.</span></span>

- <span data-ttu-id="225c4-224">何もしない。</span><span class="sxs-lookup"><span data-stu-id="225c4-224">Do nothing.</span></span> <span data-ttu-id="225c4-225">何もしないことを選択すると、メッセージは有効期限日に Office 365 によって自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-225">If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration.</span></span> <span data-ttu-id="225c4-226">既定では、メールフロールールに一致したために検疫されたスパム、バルク、マルウェア、フィッシング、メッセージは、30日間検疫に保存されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-226">By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days.</span></span> <span data-ttu-id="225c4-227">Office 365 で検疫からメッセージが削除されると、元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="225c4-227">When Office 365 deletes a message from quarantine, you can't get it back.</span></span> <span data-ttu-id="225c4-228">必要に応じて、スパム対策ポリシーの [**スパムを保持する (日)** ] の設定を構成することによって、検疫済みメッセージの保持期間を変更できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-228">If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies.</span></span> <span data-ttu-id="225c4-229">詳細については、この記事の「[検疫の保存期間の設定](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c4-229">For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span>

- <span data-ttu-id="225c4-230">**メッセージヘッダーを表示**する: メッセージヘッダーのテキストを表示するには、このリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-230">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="225c4-231">ヘッダーを詳細に分析するには、メッセージヘッダーのテキストをクリップボードにコピーし、[ **Microsoft メッセージヘッダーアナライザー** ] を選択して、リモート接続アナライザーに移動します (このタスクを完了し365ない場合は、右クリックして [**新しいタブで開く]** を選択します)。メッセージヘッダーを [メッセージヘッダーアナライザー] セクションのページに貼り付け、[**ヘッダーの分析**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-231">To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="225c4-232">[**メッセージのプレビュー**] メッセージ本文の raw バージョンまたは HTML バージョンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-232">**Preview message**: Lets you see raw or HTML versions of the message body text.</span></span> <span data-ttu-id="225c4-233">HTML ビューでは、リンクは無効です。</span><span class="sxs-lookup"><span data-stu-id="225c4-233">In the HTML view, links are disabled.</span></span>

- <span data-ttu-id="225c4-234">[**メッセージのダウンロード**またはファイルの**ダウンロード**]: このオプションを選択すると、メッセージまたはファイルのコピーがローカルデバイスにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="225c4-234">**Download message** or **Download file**: Choose this option to download a copy of the message or file to your local device.</span></span> <span data-ttu-id="225c4-235">許可する前に、検疫からのアイテムのダウンロードに関連するリスクを理解していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c4-235">You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so.</span></span> <span data-ttu-id="225c4-236">メッセージは、指定したフォルダーに .eml 形式で保存されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-236">Messages are saved in .eml format to a folder you specify.</span></span> <span data-ttu-id="225c4-237">検疫済みファイルは、元の形式で保存されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-237">Quarantined files are saved in their original format.</span></span>

- <span data-ttu-id="225c4-238">**削除**: 必要に応じて、Office 365 で設定された有効期限を待つ代わりに、検疫されたアイテム (またはアイテムのセット) をすぐに削除できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-238">**Delete**: If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365.</span></span> <span data-ttu-id="225c4-239">メッセージまたはファイルを削除するには、[検疫] ボックスの一覧でアイテムを選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-239">To delete a message or file, in the quarantine list, select the item and then choose **Delete**.</span></span> <span data-ttu-id="225c4-240">一度に複数のアイテムを削除するには、[検疫] リスト内のアイテムの左側にあるチェックボックスをオンにし、表示される [**一括アクション**] ページで、[選択した**メッセージを削除**する] または [**選択したファイルを削除**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-240">To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>

- <span data-ttu-id="225c4-241">**Release**: 検疫されたアイテム (またはアイテムのセット) を解放し、アイテムが誤って検疫された (誤検知) を Microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="225c4-241">**Release**: Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span>

  <span data-ttu-id="225c4-242">1つのメッセージまたはファイルを解放して報告するには、[検疫] の一覧でアイテムを選択し、[**ファイルの解放**] または [**メッセージの解放**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-242">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**.</span></span> <span data-ttu-id="225c4-243">次のページで、[分析の**ために microsoft に**、または**ファイル**を分析用に microsoft に報告する] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="225c4-243">On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span>

  <span data-ttu-id="225c4-244">一度に複数のアイテムを解放するには、[検疫] リスト内のアイテムの左側にあるチェックボックスをオンにし、表示される [**一括アクション**] ページで、[**ファイルの解放**] または [**メッセージの解放**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-244">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**.</span></span> <span data-ttu-id="225c4-245">次のページで、[分析の**ために microsoft に**、または**ファイル**を分析用に microsoft に報告する] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="225c4-245">On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span>

<span data-ttu-id="225c4-246">メッセージを解放するときは、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="225c4-246">When you're releasing messages, be aware of the following:</span></span>

- <span data-ttu-id="225c4-247">一度に複数のメッセージの一括リリースを実行すると、メッセージは元に識別されたすべての受信者に解放されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-247">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients.</span></span> <span data-ttu-id="225c4-248">特定の受信者にのみメッセージを解放する場合は、一度に1つずつメッセージを解放し、受信者を個別に特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c4-248">If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>

- <span data-ttu-id="225c4-249">同じ受信者に2回以上メッセージを解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="225c4-249">A message cannot be released more than once to the same recipient.</span></span>

- <span data-ttu-id="225c4-250">複数の受信者にメッセージを解放すると、メッセージを受信していない受信者のみが、潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-250">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="225c4-251">誤検知を報告することを選択すると、解放されたメッセージまたはメッセージがスパム、バルク、フィッシング、またはマルウェアを含むものとして検疫された場合、そのメッセージも Microsoft スパム分析チームに報告されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-251">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="225c4-252">チームはメッセージの評価と分析を行い、分析結果によっては、サービス全体のスパムコンテンツフィルタールールを調整してメッセージを通過できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="225c4-252">The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>

## <a name="setting-the-quarantine-retention-period"></a><span data-ttu-id="225c4-253">検疫の保存期間の設定</span><span class="sxs-lookup"><span data-stu-id="225c4-253">Setting the quarantine retention period</span></span>
<span data-ttu-id="225c4-254"><a name="BKMK_ModQuarantineTime"> </a></span><span class="sxs-lookup"><span data-stu-id="225c4-254"></span></span>

<span data-ttu-id="225c4-255">期限切れになるまでに、メッセージおよびファイルを検疫に保持する期間を構成できます。</span><span class="sxs-lookup"><span data-stu-id="225c4-255">You can configure how long messages and files will remain in quarantine before they expire.</span></span> <span data-ttu-id="225c4-256">既定では、検疫済みアイテムは30日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-256">By default, quarantined items are kept for 30 days.</span></span> <span data-ttu-id="225c4-257">この設定は、作成するポリシーごとに構成します。</span><span class="sxs-lookup"><span data-stu-id="225c4-257">You configure this setting for each policy that you create.</span></span> <span data-ttu-id="225c4-258">この記事で説明されているように、既定のポリシーの値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="225c4-258">You can also modify the value for the default policy as described in this article.</span></span>

### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a><span data-ttu-id="225c4-259">セキュリティ/コンプライアンスセンターで既定のスパムフィルターポリシーの検疫保持期間を変更するには</span><span class="sxs-lookup"><span data-stu-id="225c4-259">To modify the quarantine retention period for the default spam filter policy in the Security and Compliance Center</span></span>

1. <span data-ttu-id="225c4-260">Office 365 組織のグローバル管理者特権 (または適切なセキュリティ & コンプライアンスセンターの役割) を持つ職場または学校のアカウントを使用して、Office 365 にサインインし、[セキュリティ/コンプライアンスセンターに移動](../../compliance/go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="225c4-260">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

2. <span data-ttu-id="225c4-261">左側の [脅威の**管理**] を展開し、[**ポリシー**] を選択してから、[**スパム対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-261">On the left, expand **Threat Management**, choose **Policy**, and then choose **Anti-spam**.</span></span>

    > [!TIP]
    > <span data-ttu-id="225c4-262">セキュリティ & コンプライアンスセンターの [**スパム対策**] ページに直接移動するには、次の URL を使用します。 >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="225c4-262">To go directly to the **anti-spam** page in the Security & Compliance Center, use this URL: > [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>

3. <span data-ttu-id="225c4-263">**[既定のスパムフィルターポリシー (always ON)** ] 行を展開します。</span><span class="sxs-lookup"><span data-stu-id="225c4-263">Expand the **Default spam filter policy (always ON)** row.</span></span>

4. <span data-ttu-id="225c4-264">[**ポリシーの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-264">Choose **Edit policy**.</span></span> <span data-ttu-id="225c4-265">既定のスパムフィルターポリシーの設定が新しいページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="225c4-265">The settings for the default spam filter policy appear in a new page.</span></span>

5. <span data-ttu-id="225c4-266">**[スパムと一括アクション] を**展開します。</span><span class="sxs-lookup"><span data-stu-id="225c4-266">Expand **Spam and bulk actions**.</span></span>

6. <span data-ttu-id="225c4-267">[**検疫**] の [以下**の期間スパムを保持する (日)** ] テキストボックスに、Office 365 でメッセージおよびファイルを検疫に保持する時間の長さを入力します。</span><span class="sxs-lookup"><span data-stu-id="225c4-267">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine.</span></span> <span data-ttu-id="225c4-268">既定値は 30 日です。</span><span class="sxs-lookup"><span data-stu-id="225c4-268">The default is 30 days.</span></span> <span data-ttu-id="225c4-269">これは最大値でもあります。</span><span class="sxs-lookup"><span data-stu-id="225c4-269">This is also the maximum.</span></span>

7. <span data-ttu-id="225c4-270">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="225c4-270">Choose **Save**.</span></span>
