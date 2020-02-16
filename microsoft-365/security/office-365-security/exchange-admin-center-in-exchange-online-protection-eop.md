---
title: Exchange Online Protection の Exchange 管理センター
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Exchange 管理センター (EAC) は、Microsoft Exchange Online Protection (EOP) 向けの Web ベース管理コンソールです。
ms.openlocfilehash: f38d36249387fce2ba3b4cac9e187c1cbcadd707
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083286"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="1a08f-103">Exchange Online Protection の Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="1a08f-103">Exchange admin center in Exchange Online Protection</span></span>

<span data-ttu-id="1a08f-104">Exchange 管理センター (EAC) は、Microsoft Exchange Online Protection (EOP) 向けの Web ベース管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="1a08f-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="1a08f-105">このトピックの Exchange Server バージョンについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a08f-105">Looking for the Exchange Server version of this topic?</span></span> <span data-ttu-id="1a08f-106">「Exchange [administration center In Exchange Server」を](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center)参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a08f-106">See [Exchange admin center in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span></span>

<span data-ttu-id="1a08f-107">このトピックの Exchange Online バージョンについては、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a08f-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="1a08f-108">「Exchange [Online の exchange 管理センター」を](https://docs.microsoft.com/exchange/exchange-admin-center)参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a08f-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="accessing-the-eac"></a><span data-ttu-id="1a08f-109">EACへのアクセスについて</span><span class="sxs-lookup"><span data-stu-id="1a08f-109">Accessing the EAC</span></span>

<span data-ttu-id="1a08f-110">ほとんどの場合、EOP のお客様は、Microsoft 365 管理センターを通じて EAC にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1a08f-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="1a08f-111">EOP へのリンクは、 **[自分]** タイルの横にある **[管理]** タイルのドロップ ダウン メニューから選択できます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="1a08f-112">**[管理]** タイルをクリックし、ドロップ ダウン メニューから **[Exchange Online Protection]** を選択すると、EAC にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span>

<span data-ttu-id="1a08f-p104">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.</span><span class="sxs-lookup"><span data-stu-id="1a08f-p104">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.</span></span>

## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="1a08f-116">EAC で共通のユーザー インターフェイス要素</span><span class="sxs-lookup"><span data-stu-id="1a08f-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="1a08f-117">ここでは、EAC のユーザー インターフェイス要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="1a08f-119">機能ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="1a08f-119">Feature Pane</span></span>

<span data-ttu-id="1a08f-p105">EAC で実行する多くのタスクで、これがナビゲーションの第 1 階層になります。[機能] ウィンドウは、機能領域ごとに整理されています。</span><span class="sxs-lookup"><span data-stu-id="1a08f-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

1. <span data-ttu-id="1a08f-122">**受信者**: 内部ユーザーと外部連絡先を表示します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-122">**Recipients**: This is where you'll view internal users and external contacts.</span></span>

2. <span data-ttu-id="1a08f-123">**権限**: 管理者の役割を管理します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-123">**Permissions**: This where you'll manage administrator roles.</span></span>

3. <span data-ttu-id="1a08f-124">**コンプライアンス管理**: ここで、管理者の役割グループレポートなどの監査ログとレポートを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-124">**Compliance Management**: This is where you'll find audit logs and reports, such as the administrator role group report.</span></span>

4. <span data-ttu-id="1a08f-125">**保護**: これにより、組織のマルウェア対策およびスパム対策保護を管理し、検疫でのメッセージの管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-125">**Protection**: This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span>

5. <span data-ttu-id="1a08f-126">**メールフロー**: ルール、承認済みドメイン、およびコネクタを管理し、メッセージ追跡を実行する場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-126">**Mail Flow**: This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span>

### <a name="tabs"></a><span data-ttu-id="1a08f-127">タブ</span><span class="sxs-lookup"><span data-stu-id="1a08f-127">Tabs</span></span>

<span data-ttu-id="1a08f-p106">タブは、ナビゲーションの第 2 階層になります。各機能領域にはさまざまなタブがあり、それぞれのタブは各機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="1a08f-p106">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="1a08f-130">ツールバー</span><span class="sxs-lookup"><span data-stu-id="1a08f-130">Toolbar</span></span>

<span data-ttu-id="1a08f-p107">ほとんどのタブは、クリックするとツールバーが表示されます。ツールバーには、特定のアクションを実行する複数のアイコンがあります。次の表は、各アイコンとそのアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1a08f-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

|<span data-ttu-id="1a08f-134">**アイコン**</span><span class="sxs-lookup"><span data-stu-id="1a08f-134">**Icon**</span></span>|<span data-ttu-id="1a08f-135">**名前**</span><span class="sxs-lookup"><span data-stu-id="1a08f-135">**Name**</span></span>|<span data-ttu-id="1a08f-136">**Action**</span><span class="sxs-lookup"><span data-stu-id="1a08f-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![[追加] アイコン](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="1a08f-138">追加、新規</span><span class="sxs-lookup"><span data-stu-id="1a08f-138">Add, New</span></span>|<span data-ttu-id="1a08f-p108">このアイコンを使用して、新しいオブジェクトを作成します。これらの一部のアイコンには下方向キーが関連付けられており、これをクリックして、作成可能な追加のオブジェクトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![編集アイコン](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="1a08f-142">編集</span><span class="sxs-lookup"><span data-stu-id="1a08f-142">Edit</span></span>|<span data-ttu-id="1a08f-143">このアイコンを使用してオブジェクトを編集します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-143">Use this icon to edit an object.</span></span>|
|![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="1a08f-145">削除</span><span class="sxs-lookup"><span data-stu-id="1a08f-145">Delete</span></span>|<span data-ttu-id="1a08f-p109">このアイコンを使用してオブジェクトを削除します。一部の削除アイコンには下方向キーがあり、これをクリックして追加オプションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![[検索] アイコン](../../media/ITPro-EAC-.gif)|<span data-ttu-id="1a08f-149">検索</span><span class="sxs-lookup"><span data-stu-id="1a08f-149">Search</span></span>|<span data-ttu-id="1a08f-150">このアイコンを使用して、検索するオブジェクトの検索文字列を入力できる検索ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![[最新の情報に更新] アイコン](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="1a08f-152">最新の情報に更新</span><span class="sxs-lookup"><span data-stu-id="1a08f-152">Refresh</span></span>|<span data-ttu-id="1a08f-153">このアイコンを使用してリスト ビューを更新します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-153">Use this icon to refresh the list view.</span></span>|
|![[その他のオプション] アイコン](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="1a08f-155">その他のオプション</span><span class="sxs-lookup"><span data-stu-id="1a08f-155">More options</span></span>|<span data-ttu-id="1a08f-p110">このアイコンを使用して、そのタブのオブジェクトに対して実行できる他のアクションを表示します。たとえば、 **受信者 \> ユーザー**のアイコンをクリックすると、 **詳細検索**のオプションが表示されます。  </span><span class="sxs-lookup"><span data-stu-id="1a08f-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.gif)![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="1a08f-160">上方向キーと下方向キー</span><span class="sxs-lookup"><span data-stu-id="1a08f-160">Up arrow and down arrow</span></span>|<span data-ttu-id="1a08f-161">これらのアイコンを使用して、オブジェクトの優先度を上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-161">Use these icons to move an object's priority up or down.</span></span>|
|![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="1a08f-163">削除</span><span class="sxs-lookup"><span data-stu-id="1a08f-163">Remove</span></span>|<span data-ttu-id="1a08f-164">このアイコンを使用して、一覧からオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-164">Use this icon to remove objects from a list.</span></span>|

### <a name="list-view"></a><span data-ttu-id="1a08f-165">リスト ビュー</span><span class="sxs-lookup"><span data-stu-id="1a08f-165">List View</span></span>

<span data-ttu-id="1a08f-p111">タブを選択すると、通常、リスト ビューが表示されます。EAC リスト ビューの表示可能限度は、ほぼ 10,000 オブジェクトです。さらに、ページングが含まれているため、結果をページングできます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="1a08f-169">詳細ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="1a08f-169">Details Pane</span></span>

<span data-ttu-id="1a08f-p112">リスト ビューからオブジェクトを選択すると、そのオブジェクトに関する情報が詳細ウィンドウに表示されます。場合によっては、[詳細] ウィンドウに管理タスクが含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="1a08f-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="1a08f-172">[自分] タイルとヘルプ</span><span class="sxs-lookup"><span data-stu-id="1a08f-172">Me tile and Help</span></span>

<span data-ttu-id="1a08f-p113">**[自分]** タイルでは、EAC からのサインアウトおよび他のユーザーとしてサインインが行えます。 **[ヘルプ]**![ヘルプ アイコン](../../media/ITPro-EAC-HelpIcon.gif) ドロップ ダウン メニューから次のアクションを行えます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

1. <span data-ttu-id="1a08f-175">**ヘルプ**: ヘルプ![アイコン](../../media/ITPro-EAC-HelpIcon.gif)をクリックして、オンラインヘルプコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-175">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

2. <span data-ttu-id="1a08f-176">**ヘルプバブルを無効に**する: ヘルプバブルは、オブジェクトを作成または編集するときに、フィールドのコンテキストヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-176">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="1a08f-177">ヘルプ バブルをオフにしたり、無効になっている場合はオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a08f-177">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

3. <span data-ttu-id="1a08f-178">**Copyright**: このリンクをクリックして、Exchange Online Protection の著作権に関する情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-178">**Copyright**: Click this link to read the copyright notice for Exchange Online Protection.</span></span>

4. <span data-ttu-id="1a08f-179">**プライバシー**: クリックして、Exchange Online Protection のプライバシーポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a08f-179">**Privacy**: Click to read the privacy policy for Exchange Online Protection.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="1a08f-180">サポートされているブラウザー</span><span class="sxs-lookup"><span data-stu-id="1a08f-180">Supported Browsers</span></span>

<span data-ttu-id="1a08f-181">EAC を最大限に活用できるように、常に最新のブラウザー、Office クライアント、アプリを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a08f-181">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="1a08f-182">また、ソフトウェア更新プログラムも、利用可能になり次第インストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a08f-182">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="1a08f-183">サポートされるブラウザーおよびサービスのシステム要件の詳細については、「 [Office のシステム要件](https://products.office.com/office-system-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a08f-183">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages-in-eop"></a><span data-ttu-id="1a08f-184">EOP でサポートされている言語</span><span class="sxs-lookup"><span data-stu-id="1a08f-184">Supported languages in EOP</span></span>

<span data-ttu-id="1a08f-185">Exchange Online Protection でサポートされ、利用可能な言語は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a08f-185">The following languages are supported and available for Exchange Online Protection.</span></span>

- <span data-ttu-id="1a08f-186">アムハラ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-186">Amharic</span></span>

- <span data-ttu-id="1a08f-187">アラビア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-187">Arabic</span></span>

- <span data-ttu-id="1a08f-188">バスク語 (バスク)</span><span class="sxs-lookup"><span data-stu-id="1a08f-188">Basque (Basque)</span></span>

- <span data-ttu-id="1a08f-189">バングラ語 (インド)</span><span class="sxs-lookup"><span data-stu-id="1a08f-189">Bengali (India)</span></span>

- <span data-ttu-id="1a08f-190">ブルガリア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-190">Bulgarian</span></span>

- <span data-ttu-id="1a08f-191">カタルニア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-191">Catalan</span></span>

- <span data-ttu-id="1a08f-192">簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="1a08f-192">Chinese (Simplified)</span></span>

- <span data-ttu-id="1a08f-193">繁体字中国語</span><span class="sxs-lookup"><span data-stu-id="1a08f-193">Chinese (Traditional)</span></span>

- <span data-ttu-id="1a08f-194">クロアチア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-194">Croatian</span></span>

- <span data-ttu-id="1a08f-195">チェコ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-195">Czech</span></span>

- <span data-ttu-id="1a08f-196">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="1a08f-196">Danish</span></span>

- <span data-ttu-id="1a08f-197">オランダ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-197">Dutch</span></span>

- <span data-ttu-id="1a08f-198">オランダ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-198">Dutch</span></span>

- <span data-ttu-id="1a08f-199">英語</span><span class="sxs-lookup"><span data-stu-id="1a08f-199">English</span></span>

- <span data-ttu-id="1a08f-200">エストニア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-200">Estonian</span></span>

- <span data-ttu-id="1a08f-201">フィリピン語 (フィリピン)</span><span class="sxs-lookup"><span data-stu-id="1a08f-201">Filipino (Philippines)</span></span>

- <span data-ttu-id="1a08f-202">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="1a08f-202">Finnish</span></span>

- <span data-ttu-id="1a08f-203">フランス語</span><span class="sxs-lookup"><span data-stu-id="1a08f-203">French</span></span>

- <span data-ttu-id="1a08f-204">ガリシア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-204">Galician</span></span>

- <span data-ttu-id="1a08f-205">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-205">German</span></span>

- <span data-ttu-id="1a08f-206">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-206">Greek</span></span>

- <span data-ttu-id="1a08f-207">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="1a08f-207">Gujarati</span></span>

- <span data-ttu-id="1a08f-208">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-208">Hebrew</span></span>

- <span data-ttu-id="1a08f-209">ヒンディー語</span><span class="sxs-lookup"><span data-stu-id="1a08f-209">Hindi</span></span>

- <span data-ttu-id="1a08f-210">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="1a08f-210">Hungarian</span></span>

- <span data-ttu-id="1a08f-211">アイスランド語</span><span class="sxs-lookup"><span data-stu-id="1a08f-211">Icelandic</span></span>

- <span data-ttu-id="1a08f-212">インドネシア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-212">Indonesian</span></span>

- <span data-ttu-id="1a08f-213">イタリア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-213">Italian</span></span>

- <span data-ttu-id="1a08f-214">日本語</span><span class="sxs-lookup"><span data-stu-id="1a08f-214">Japanese</span></span>

- <span data-ttu-id="1a08f-215">カンナダ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-215">Kannada</span></span>

- <span data-ttu-id="1a08f-216">カザフ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-216">Kazakh</span></span>

- <span data-ttu-id="1a08f-217">スワヒリ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-217">Kiswahili</span></span>

- <span data-ttu-id="1a08f-218">韓国語</span><span class="sxs-lookup"><span data-stu-id="1a08f-218">Korean</span></span>

- <span data-ttu-id="1a08f-219">ラトビア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-219">Latvian</span></span>

- <span data-ttu-id="1a08f-220">リトアニア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-220">Lithuanian</span></span>

- <span data-ttu-id="1a08f-221">マレー語 (ブルネイ・ダルサラーム国)</span><span class="sxs-lookup"><span data-stu-id="1a08f-221">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="1a08f-222">マレー語 (マレーシア)</span><span class="sxs-lookup"><span data-stu-id="1a08f-222">Malay (Malaysia)</span></span>

- <span data-ttu-id="1a08f-223">マラヤーラム語</span><span class="sxs-lookup"><span data-stu-id="1a08f-223">Malayalam</span></span>

- <span data-ttu-id="1a08f-224">マラーティー語</span><span class="sxs-lookup"><span data-stu-id="1a08f-224">Marathi</span></span>

- <span data-ttu-id="1a08f-225">ノルウェー語 (ブークモール)</span><span class="sxs-lookup"><span data-stu-id="1a08f-225">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="1a08f-226">ノルウェー語 (ニーノシュク)</span><span class="sxs-lookup"><span data-stu-id="1a08f-226">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="1a08f-227">オリヤー語</span><span class="sxs-lookup"><span data-stu-id="1a08f-227">Oriya</span></span>

- <span data-ttu-id="1a08f-228">ペルシャ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-228">Persian</span></span>

- <span data-ttu-id="1a08f-229">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="1a08f-229">Polish</span></span>

- <span data-ttu-id="1a08f-230">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="1a08f-230">Portuguese (Brazil)</span></span>

- <span data-ttu-id="1a08f-231">ポルトガル語 (ポルトガル)</span><span class="sxs-lookup"><span data-stu-id="1a08f-231">Portuguese (Portugal)</span></span>

- <span data-ttu-id="1a08f-232">ルーマニア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-232">Romanian</span></span>

- <span data-ttu-id="1a08f-233">ロシア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-233">Russian</span></span>

- <span data-ttu-id="1a08f-234">セルビア語 (キリル、セルビア)</span><span class="sxs-lookup"><span data-stu-id="1a08f-234">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="1a08f-235">セルビア語 (ラテン)</span><span class="sxs-lookup"><span data-stu-id="1a08f-235">Serbian (Latin)</span></span>

- <span data-ttu-id="1a08f-236">スロバキア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-236">Slovak</span></span>

- <span data-ttu-id="1a08f-237">スロベニア語</span><span class="sxs-lookup"><span data-stu-id="1a08f-237">Slovenian</span></span>

- <span data-ttu-id="1a08f-238">スペイン語</span><span class="sxs-lookup"><span data-stu-id="1a08f-238">Spanish</span></span>

- <span data-ttu-id="1a08f-239">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="1a08f-239">Swedish</span></span>

- <span data-ttu-id="1a08f-240">タミール語</span><span class="sxs-lookup"><span data-stu-id="1a08f-240">Tamil</span></span>

- <span data-ttu-id="1a08f-241">テルグ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-241">Telugu</span></span>

- <span data-ttu-id="1a08f-242">タイ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-242">Thai</span></span>

- <span data-ttu-id="1a08f-243">トルコ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-243">Turkish</span></span>

- <span data-ttu-id="1a08f-244">ウクライナ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-244">Ukrainian</span></span>

- <span data-ttu-id="1a08f-245">ウルドゥ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-245">Urdu</span></span>

- <span data-ttu-id="1a08f-246">ベトナム語</span><span class="sxs-lookup"><span data-stu-id="1a08f-246">Vietnamese</span></span>

- <span data-ttu-id="1a08f-247">ウェールズ語</span><span class="sxs-lookup"><span data-stu-id="1a08f-247">Welsh</span></span>


