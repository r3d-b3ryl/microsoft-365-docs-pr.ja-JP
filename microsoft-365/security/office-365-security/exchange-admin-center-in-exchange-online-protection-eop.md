---
title: スタンドアロン EOP の Exchange 管理者センター
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
description: スタンドアロン Exchange Online Protection (EOP) の web 管理インターフェイスについて説明します。
ms.openlocfilehash: 777597489e54c642220cb42f0c686b675101897f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617000"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="c8fed-103">スタンドアロン EOP の Exchange 管理者センター</span><span class="sxs-lookup"><span data-stu-id="c8fed-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="c8fed-104">Exchange 管理センター (EAC) は、スタンドアロンの Exchange Online Protection (EOP) 用の web ベースの管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c8fed-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="c8fed-105">このトピックの Exchange Online バージョンについては、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8fed-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="c8fed-106">「Exchange [Online の exchange 管理センター」を](https://docs.microsoft.com/exchange/exchange-admin-center)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8fed-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="c8fed-107">EOP で EAC を開きます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-107">Open the EAC in EOP</span></span>

<span data-ttu-id="c8fed-108">スタンドアロン EOP のお客様は、以下の方法を使用して EAC にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="c8fed-109">**Microsoft 365 管理センターから**:</span><span class="sxs-lookup"><span data-stu-id="c8fed-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="c8fed-110">に移動し <https://admin.microsoft.com> 、[**すべて表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8fed-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Microsoft 365 管理センターで [すべて表示] をクリックする](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="c8fed-112">表示される [**管理センター** ] セクションで、[**すべての管理センター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8fed-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Microsoft 365 管理センターの [すべての管理センター] をクリックします。](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="c8fed-114">表示される [**すべての管理センター** ] ページで、[ **Exchange Online Protection**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8fed-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="c8fed-115">に直接移動 `https://admin.protection.outlook.com/ecp/` します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="c8fed-116">EOP の EAC の一般的なユーザーインターフェイス要素</span><span class="sxs-lookup"><span data-stu-id="c8fed-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="c8fed-117">ここでは、EAC のユーザー インターフェイス要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="c8fed-119">機能ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="c8fed-119">Feature Pane</span></span>

<span data-ttu-id="c8fed-p102">EAC で実行する多くのタスクで、これがナビゲーションの第 1 階層になります。[機能] ウィンドウは、機能領域ごとに整理されています。</span><span class="sxs-lookup"><span data-stu-id="c8fed-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="c8fed-122">**受信者**: グループと外部の連絡先を表示します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="c8fed-123">**権限**: 管理者の役割を管理します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="c8fed-124">**コンプライアンス管理**: 管理者の役割グループレポートおよび管理者監査ログレポートを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="c8fed-125">**保護**: これにより、マルウェア対策ポリシー、既定の接続フィルターポリシー、および dkim を管理できます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c8fed-126">セキュリティ & コンプライアンスセンターで、マルウェア対策ポリシーと既定の接続フィルターポリシーを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8fed-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="c8fed-127">詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」および「 [configure CONNECTION filtering in EOP](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8fed-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="c8fed-128">**メールフロー**: メールフロールール (トランスポートルールとも呼ばれます)、承認済みドメイン、コネクタ、および [メッセージ追跡の実行] に移動できる場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="c8fed-129">**ハイブリッド**:[ハイブリッド構成ウィザード](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)を実行して、 [Exchange Online の PowerShell モジュール](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="c8fed-130">タブ</span><span class="sxs-lookup"><span data-stu-id="c8fed-130">Tabs</span></span>

<span data-ttu-id="c8fed-p104">タブは、ナビゲーションの第 2 階層になります。各機能領域にはさまざまなタブがあり、それぞれのタブは各機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="c8fed-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="c8fed-133">ツールバー</span><span class="sxs-lookup"><span data-stu-id="c8fed-133">Toolbar</span></span>

<span data-ttu-id="c8fed-p105">ほとんどのタブは、クリックするとツールバーが表示されます。ツールバーには、特定のアクションを実行する複数のアイコンがあります。次の表は、各アイコンとそのアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="c8fed-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

||||
|---|---|---|
|<span data-ttu-id="c8fed-137">**アイコン**</span><span class="sxs-lookup"><span data-stu-id="c8fed-137">**Icon**</span></span>|<span data-ttu-id="c8fed-138">**名前**</span><span class="sxs-lookup"><span data-stu-id="c8fed-138">**Name**</span></span>|<span data-ttu-id="c8fed-139">**Action**</span><span class="sxs-lookup"><span data-stu-id="c8fed-139">**Action**</span></span>|
|![[追加] アイコン](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="c8fed-141">追加、新規</span><span class="sxs-lookup"><span data-stu-id="c8fed-141">Add, New</span></span>|<span data-ttu-id="c8fed-p106">このアイコンを使用して、新しいオブジェクトを作成します。これらの一部のアイコンには下方向キーが関連付けられており、これをクリックして、作成可能な追加のオブジェクトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![編集アイコン](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="c8fed-145">編集</span><span class="sxs-lookup"><span data-stu-id="c8fed-145">Edit</span></span>|<span data-ttu-id="c8fed-146">このアイコンを使用してオブジェクトを編集します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-146">Use this icon to edit an object.</span></span>|
|![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="c8fed-148">削除</span><span class="sxs-lookup"><span data-stu-id="c8fed-148">Delete</span></span>|<span data-ttu-id="c8fed-p107">このアイコンを使用してオブジェクトを削除します。一部の削除アイコンには下方向キーがあり、これをクリックして追加オプションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![[検索] アイコン](../../media/ITPro-EAC-.gif)|<span data-ttu-id="c8fed-152">検索</span><span class="sxs-lookup"><span data-stu-id="c8fed-152">Search</span></span>|<span data-ttu-id="c8fed-153">このアイコンを使用して、検索するオブジェクトの検索文字列を入力できる検索ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![[最新の情報に更新] アイコン](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="c8fed-155">最新の情報に更新</span><span class="sxs-lookup"><span data-stu-id="c8fed-155">Refresh</span></span>|<span data-ttu-id="c8fed-156">このアイコンを使用してリスト ビューを更新します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-156">Use this icon to refresh the list view.</span></span>|
|![[その他のオプション] アイコン](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="c8fed-158">その他のオプション</span><span class="sxs-lookup"><span data-stu-id="c8fed-158">More options</span></span>|<span data-ttu-id="c8fed-p108">このアイコンを使用して、そのタブのオブジェクトに対して実行できる他のアクションを表示します。たとえば、 **受信者 \> ユーザー**のアイコンをクリックすると、 **詳細検索**のオプションが表示されます。  </span><span class="sxs-lookup"><span data-stu-id="c8fed-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.gif)![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="c8fed-163">上方向キーと下方向キー</span><span class="sxs-lookup"><span data-stu-id="c8fed-163">Up arrow and down arrow</span></span>|<span data-ttu-id="c8fed-164">これらのアイコンを使用して、オブジェクトの優先度を上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-164">Use these icons to move an object's priority up or down.</span></span>|
|![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="c8fed-166">削除</span><span class="sxs-lookup"><span data-stu-id="c8fed-166">Remove</span></span>|<span data-ttu-id="c8fed-167">このアイコンを使用して、一覧からオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="c8fed-168">リスト ビュー</span><span class="sxs-lookup"><span data-stu-id="c8fed-168">List View</span></span>

<span data-ttu-id="c8fed-p109">タブを選択すると、通常、リスト ビューが表示されます。EAC リスト ビューの表示可能限度は、ほぼ 10,000 オブジェクトです。さらに、ページングが含まれているため、結果をページングできます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="c8fed-172">詳細ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="c8fed-172">Details Pane</span></span>

<span data-ttu-id="c8fed-p110">リスト ビューからオブジェクトを選択すると、そのオブジェクトに関する情報が詳細ウィンドウに表示されます。場合によっては、[詳細] ウィンドウに管理タスクが含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="c8fed-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="c8fed-175">[自分] タイルとヘルプ</span><span class="sxs-lookup"><span data-stu-id="c8fed-175">Me tile and Help</span></span>

<span data-ttu-id="c8fed-p111">**[自分]** タイルでは、EAC からのサインアウトおよび他のユーザーとしてサインインが行えます。 **[ヘルプ]**![ヘルプ アイコン](../../media/ITPro-EAC-HelpIcon.gif) ドロップ ダウン メニューから次のアクションを行えます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-p111">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="c8fed-178">**ヘルプ**: ![ ヘルプアイコンをクリックし ](../../media/ITPro-EAC-HelpIcon.gif) て、オンラインヘルプコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="c8fed-179">**フィードバック**: フィードバックを投稿します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="c8fed-180">**Community**: コミュニティフォーラムに質問を投稿して、答えを見つけてください。</span><span class="sxs-lookup"><span data-stu-id="c8fed-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="c8fed-181">**ヘルプバブルを無効に**する: ヘルプバブルは、オブジェクトを作成または編集するときに、フィールドのコンテキストヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="c8fed-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="c8fed-182">ヘルプ バブルをオフにしたり、無効になっている場合はオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="c8fed-183">[**コマンドログの表示**]: EAC で構成した内容に基づいて、同等の PowerShell コマンドを示す新しいウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="c8fed-184">サポートされているブラウザー</span><span class="sxs-lookup"><span data-stu-id="c8fed-184">Supported Browsers</span></span>

<span data-ttu-id="c8fed-185">EAC を最大限に活用できるように、常に最新のブラウザー、Office クライアント、アプリを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8fed-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="c8fed-186">また、ソフトウェア更新プログラムも、利用可能になり次第インストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8fed-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="c8fed-187">サポートされるブラウザーおよびサービスのシステム要件の詳細については、「 [Office のシステム要件](https://products.office.com/office-system-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8fed-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="c8fed-188">サポートされている言語</span><span class="sxs-lookup"><span data-stu-id="c8fed-188">Supported languages</span></span>

<span data-ttu-id="c8fed-189">EAC では、以下の言語がサポートされており、スタンドアロン EOP で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8fed-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="c8fed-190">アムハラ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-190">Amharic</span></span>

- <span data-ttu-id="c8fed-191">アラビア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-191">Arabic</span></span>

- <span data-ttu-id="c8fed-192">バスク語 (バスク)</span><span class="sxs-lookup"><span data-stu-id="c8fed-192">Basque (Basque)</span></span>

- <span data-ttu-id="c8fed-193">バングラ語 (インド)</span><span class="sxs-lookup"><span data-stu-id="c8fed-193">Bengali (India)</span></span>

- <span data-ttu-id="c8fed-194">ブルガリア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-194">Bulgarian</span></span>

- <span data-ttu-id="c8fed-195">カタルニア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-195">Catalan</span></span>

- <span data-ttu-id="c8fed-196">簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="c8fed-196">Chinese (Simplified)</span></span>

- <span data-ttu-id="c8fed-197">繁体字中国語</span><span class="sxs-lookup"><span data-stu-id="c8fed-197">Chinese (Traditional)</span></span>

- <span data-ttu-id="c8fed-198">クロアチア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-198">Croatian</span></span>

- <span data-ttu-id="c8fed-199">チェコ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-199">Czech</span></span>

- <span data-ttu-id="c8fed-200">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="c8fed-200">Danish</span></span>

- <span data-ttu-id="c8fed-201">オランダ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-201">Dutch</span></span>

- <span data-ttu-id="c8fed-202">オランダ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-202">Dutch</span></span>

- <span data-ttu-id="c8fed-203">英語</span><span class="sxs-lookup"><span data-stu-id="c8fed-203">English</span></span>

- <span data-ttu-id="c8fed-204">エストニア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-204">Estonian</span></span>

- <span data-ttu-id="c8fed-205">フィリピン語 (フィリピン)</span><span class="sxs-lookup"><span data-stu-id="c8fed-205">Filipino (Philippines)</span></span>

- <span data-ttu-id="c8fed-206">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="c8fed-206">Finnish</span></span>

- <span data-ttu-id="c8fed-207">フランス語</span><span class="sxs-lookup"><span data-stu-id="c8fed-207">French</span></span>

- <span data-ttu-id="c8fed-208">ガリシア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-208">Galician</span></span>

- <span data-ttu-id="c8fed-209">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-209">German</span></span>

- <span data-ttu-id="c8fed-210">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-210">Greek</span></span>

- <span data-ttu-id="c8fed-211">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="c8fed-211">Gujarati</span></span>

- <span data-ttu-id="c8fed-212">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-212">Hebrew</span></span>

- <span data-ttu-id="c8fed-213">ヒンディー語</span><span class="sxs-lookup"><span data-stu-id="c8fed-213">Hindi</span></span>

- <span data-ttu-id="c8fed-214">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="c8fed-214">Hungarian</span></span>

- <span data-ttu-id="c8fed-215">アイスランド語</span><span class="sxs-lookup"><span data-stu-id="c8fed-215">Icelandic</span></span>

- <span data-ttu-id="c8fed-216">インドネシア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-216">Indonesian</span></span>

- <span data-ttu-id="c8fed-217">イタリア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-217">Italian</span></span>

- <span data-ttu-id="c8fed-218">日本語</span><span class="sxs-lookup"><span data-stu-id="c8fed-218">Japanese</span></span>

- <span data-ttu-id="c8fed-219">カンナダ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-219">Kannada</span></span>

- <span data-ttu-id="c8fed-220">カザフ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-220">Kazakh</span></span>

- <span data-ttu-id="c8fed-221">スワヒリ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-221">Kiswahili</span></span>

- <span data-ttu-id="c8fed-222">韓国語</span><span class="sxs-lookup"><span data-stu-id="c8fed-222">Korean</span></span>

- <span data-ttu-id="c8fed-223">ラトビア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-223">Latvian</span></span>

- <span data-ttu-id="c8fed-224">リトアニア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-224">Lithuanian</span></span>

- <span data-ttu-id="c8fed-225">マレー語 (ブルネイ・ダルサラーム国)</span><span class="sxs-lookup"><span data-stu-id="c8fed-225">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="c8fed-226">マレー語 (マレーシア)</span><span class="sxs-lookup"><span data-stu-id="c8fed-226">Malay (Malaysia)</span></span>

- <span data-ttu-id="c8fed-227">マラヤーラム語</span><span class="sxs-lookup"><span data-stu-id="c8fed-227">Malayalam</span></span>

- <span data-ttu-id="c8fed-228">マラーティー語</span><span class="sxs-lookup"><span data-stu-id="c8fed-228">Marathi</span></span>

- <span data-ttu-id="c8fed-229">ノルウェー語 (ブークモール)</span><span class="sxs-lookup"><span data-stu-id="c8fed-229">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="c8fed-230">ノルウェー語 (ニーノシュク)</span><span class="sxs-lookup"><span data-stu-id="c8fed-230">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="c8fed-231">オリヤー語</span><span class="sxs-lookup"><span data-stu-id="c8fed-231">Oriya</span></span>

- <span data-ttu-id="c8fed-232">ペルシャ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-232">Persian</span></span>

- <span data-ttu-id="c8fed-233">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="c8fed-233">Polish</span></span>

- <span data-ttu-id="c8fed-234">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="c8fed-234">Portuguese (Brazil)</span></span>

- <span data-ttu-id="c8fed-235">ポルトガル語 (ポルトガル)</span><span class="sxs-lookup"><span data-stu-id="c8fed-235">Portuguese (Portugal)</span></span>

- <span data-ttu-id="c8fed-236">ルーマニア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-236">Romanian</span></span>

- <span data-ttu-id="c8fed-237">ロシア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-237">Russian</span></span>

- <span data-ttu-id="c8fed-238">セルビア語 (キリル、セルビア)</span><span class="sxs-lookup"><span data-stu-id="c8fed-238">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="c8fed-239">セルビア語 (ラテン)</span><span class="sxs-lookup"><span data-stu-id="c8fed-239">Serbian (Latin)</span></span>

- <span data-ttu-id="c8fed-240">スロバキア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-240">Slovak</span></span>

- <span data-ttu-id="c8fed-241">スロベニア語</span><span class="sxs-lookup"><span data-stu-id="c8fed-241">Slovenian</span></span>

- <span data-ttu-id="c8fed-242">スペイン語</span><span class="sxs-lookup"><span data-stu-id="c8fed-242">Spanish</span></span>

- <span data-ttu-id="c8fed-243">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="c8fed-243">Swedish</span></span>

- <span data-ttu-id="c8fed-244">タミール語</span><span class="sxs-lookup"><span data-stu-id="c8fed-244">Tamil</span></span>

- <span data-ttu-id="c8fed-245">テルグ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-245">Telugu</span></span>

- <span data-ttu-id="c8fed-246">タイ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-246">Thai</span></span>

- <span data-ttu-id="c8fed-247">トルコ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-247">Turkish</span></span>

- <span data-ttu-id="c8fed-248">ウクライナ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-248">Ukrainian</span></span>

- <span data-ttu-id="c8fed-249">ウルドゥ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-249">Urdu</span></span>

- <span data-ttu-id="c8fed-250">ベトナム語</span><span class="sxs-lookup"><span data-stu-id="c8fed-250">Vietnamese</span></span>

- <span data-ttu-id="c8fed-251">ウェールズ語</span><span class="sxs-lookup"><span data-stu-id="c8fed-251">Welsh</span></span>
