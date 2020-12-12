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
description: スタンドアロン Exchange Online Protection (EOP) の Web 管理インターフェイスについて説明します。
ms.openlocfilehash: fc76ecd6dafcf9453a0c6de14917c96c950f8370
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659668"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="c6972-103">スタンドアロン EOP の Exchange 管理者センター</span><span class="sxs-lookup"><span data-stu-id="c6972-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c6972-104">Exchange 管理センター (EAC) は、スタンドアロン Exchange Online Protection (EOP) 用の Web ベースの管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c6972-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="c6972-105">このトピックの Exchange Online バージョンをお探しの場合は、</span><span class="sxs-lookup"><span data-stu-id="c6972-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="c6972-106">[Exchange Online の Exchange 管理センターを参照してください](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="c6972-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="c6972-107">EOP で EAC を開く</span><span class="sxs-lookup"><span data-stu-id="c6972-107">Open the EAC in EOP</span></span>

<span data-ttu-id="c6972-108">スタンドアロン EOP のお客様は、次の方法を使用して EAC にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c6972-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="c6972-109">**Microsoft 365 管理センターから**:</span><span class="sxs-lookup"><span data-stu-id="c6972-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="c6972-110">[すべて表示 <https://admin.microsoft.com> ] に移動 **してクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6972-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Microsoft 365 管理センターで [すべて表示] をクリックする](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="c6972-112">表示される **[管理センター]** セクションで、[すべての管理センター] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6972-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Microsoft 365 管理センターで [すべての管理センター] をクリックします。](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="c6972-114">表示された **[すべての管理センター]** ページで **、[Exchange Online Protection] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c6972-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="c6972-115">に直接移動します `https://admin.protection.outlook.com/ecp/` 。</span><span class="sxs-lookup"><span data-stu-id="c6972-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="c6972-116">EOP の EAC の一般的なユーザー インターフェイス要素</span><span class="sxs-lookup"><span data-stu-id="c6972-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="c6972-117">ここでは、EAC のユーザー インターフェイス要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6972-117">This section describes the user interface elements that are found in the EAC.</span></span>

![Exchange Online Protection の Exchange 管理センター](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="c6972-119">機能ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="c6972-119">Feature Pane</span></span>

<span data-ttu-id="c6972-p102">EAC で実行する多くのタスクで、これがナビゲーションの第 1 階層になります。[機能] ウィンドウは、機能領域ごとに整理されています。</span><span class="sxs-lookup"><span data-stu-id="c6972-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="c6972-122">**受信者**: グループと外部の連絡先を表示する場所です。</span><span class="sxs-lookup"><span data-stu-id="c6972-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="c6972-123">**アクセス許可**: 管理者ロールを管理する場所です。</span><span class="sxs-lookup"><span data-stu-id="c6972-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="c6972-124">**コンプライアンス管理**: 管理者の役割グループ レポートと管理者監査ログ レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c6972-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="c6972-125">**保護**: マルウェア対策ポリシー、既定の接続フィルター ポリシー、および DKIM を管理できます。</span><span class="sxs-lookup"><span data-stu-id="c6972-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c6972-126">セキュリティ/コンプライアンス センターでマルウェア対策ポリシーと既定の接続フィルター ポリシー&する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6972-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="c6972-127">詳細については、「EOP でマルウェア対策ポリシーを構成する」および [「EOP](configure-anti-malware-policies.md) で接続フィルターを構成する」を [参照してください](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="c6972-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="c6972-128">**メール フロー**: ここでは、メール フロー ルール (トランスポート ルールとも呼ばれる)、承認されたドメイン、コネクタ、およびメッセージ追跡を実行できる場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="c6972-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="c6972-129">**ハイブリッド**: ハイブリッド構成ウィザードを実行 [](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)できる場所と [、Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)モジュールをインストールできる場所です。</span><span class="sxs-lookup"><span data-stu-id="c6972-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="c6972-130">タブ</span><span class="sxs-lookup"><span data-stu-id="c6972-130">Tabs</span></span>

<span data-ttu-id="c6972-p104">タブは、ナビゲーションの第 2 階層になります。各機能領域にはさまざまなタブがあり、それぞれのタブは各機能を表しています。</span><span class="sxs-lookup"><span data-stu-id="c6972-p104">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="c6972-133">ツールバー</span><span class="sxs-lookup"><span data-stu-id="c6972-133">Toolbar</span></span>

<span data-ttu-id="c6972-p105">ほとんどのタブは、クリックするとツールバーが表示されます。ツールバーには、特定のアクションを実行する複数のアイコンがあります。次の表は、各アイコンとそのアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="c6972-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="c6972-137">Icon</span><span class="sxs-lookup"><span data-stu-id="c6972-137">Icon</span></span>|<span data-ttu-id="c6972-138">名前</span><span class="sxs-lookup"><span data-stu-id="c6972-138">Name</span></span>|<span data-ttu-id="c6972-139">Action</span><span class="sxs-lookup"><span data-stu-id="c6972-139">Action</span></span>|
|---|---|---|
|![[追加] アイコン](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="c6972-141">追加、新規</span><span class="sxs-lookup"><span data-stu-id="c6972-141">Add, New</span></span>|<span data-ttu-id="c6972-p106">このアイコンを使用して、新しいオブジェクトを作成します。これらの一部のアイコンには下方向キーが関連付けられており、これをクリックして、作成可能な追加のオブジェクトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c6972-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![編集アイコン](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="c6972-145">編集</span><span class="sxs-lookup"><span data-stu-id="c6972-145">Edit</span></span>|<span data-ttu-id="c6972-146">このアイコンを使用してオブジェクトを編集します。</span><span class="sxs-lookup"><span data-stu-id="c6972-146">Use this icon to edit an object.</span></span>|
|![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="c6972-148">削除</span><span class="sxs-lookup"><span data-stu-id="c6972-148">Delete</span></span>|<span data-ttu-id="c6972-p107">このアイコンを使用してオブジェクトを削除します。一部の削除アイコンには下方向キーがあり、これをクリックして追加オプションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c6972-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![[検索] アイコン](../../media/ITPro-EAC-.gif)|<span data-ttu-id="c6972-152">検索</span><span class="sxs-lookup"><span data-stu-id="c6972-152">Search</span></span>|<span data-ttu-id="c6972-153">このアイコンを使用して、検索するオブジェクトの検索文字列を入力できる検索ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6972-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![[最新の情報に更新] アイコン](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="c6972-155">最新の情報に更新</span><span class="sxs-lookup"><span data-stu-id="c6972-155">Refresh</span></span>|<span data-ttu-id="c6972-156">このアイコンを使用してリスト ビューを更新します。</span><span class="sxs-lookup"><span data-stu-id="c6972-156">Use this icon to refresh the list view.</span></span>|
|![[その他のオプション] アイコン](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="c6972-158">その他のオプション</span><span class="sxs-lookup"><span data-stu-id="c6972-158">More options</span></span>|<span data-ttu-id="c6972-p108">このアイコンを使用して、そのタブのオブジェクトに対して実行できる他のアクションを表示します。たとえば、 **受信者 \> ユーザー** のアイコンをクリックすると、 **詳細検索** のオプションが表示されます。  </span><span class="sxs-lookup"><span data-stu-id="c6972-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.gif)![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="c6972-163">上方向キーと下方向キー</span><span class="sxs-lookup"><span data-stu-id="c6972-163">Up arrow and down arrow</span></span>|<span data-ttu-id="c6972-164">これらのアイコンを使用して、オブジェクトの優先度を上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6972-164">Use these icons to move an object's priority up or down.</span></span>|
|![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="c6972-166">削除</span><span class="sxs-lookup"><span data-stu-id="c6972-166">Remove</span></span>|<span data-ttu-id="c6972-167">このアイコンを使用して、一覧からオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="c6972-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="c6972-168">リスト ビュー</span><span class="sxs-lookup"><span data-stu-id="c6972-168">List View</span></span>

<span data-ttu-id="c6972-p109">タブを選択すると、通常、リスト ビューが表示されます。EAC リスト ビューの表示可能限度は、ほぼ 10,000 オブジェクトです。さらに、ページングが含まれているため、結果をページングできます。</span><span class="sxs-lookup"><span data-stu-id="c6972-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="c6972-172">詳細ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="c6972-172">Details Pane</span></span>

<span data-ttu-id="c6972-p110">リスト ビューからオブジェクトを選択すると、そのオブジェクトに関する情報が詳細ウィンドウに表示されます。場合によっては、[詳細] ウィンドウに管理タスクが含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="c6972-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="c6972-175">[自分] タイルとヘルプ</span><span class="sxs-lookup"><span data-stu-id="c6972-175">Me tile and Help</span></span>

<span data-ttu-id="c6972-176">**[自分]** タイルでは、EAC からのサインアウトおよび他のユーザーとしてサインインが行えます。</span><span class="sxs-lookup"><span data-stu-id="c6972-176">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="c6972-177">[ヘルプ **アイコン]** ドロップダウン メニュー ![ ](../../media/ITPro-EAC-HelpIcon.gif) から、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6972-177">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="c6972-178">**Help**: Click ![ Help Icon to view the online help ](../../media/ITPro-EAC-HelpIcon.gif) content.</span><span class="sxs-lookup"><span data-stu-id="c6972-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="c6972-179">**フィードバック**: フィードバックを送信します。</span><span class="sxs-lookup"><span data-stu-id="c6972-179">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="c6972-180">**コミュニティ**: コミュニティ フォーラムで、検索の回答に関する質問を投稿します。</span><span class="sxs-lookup"><span data-stu-id="c6972-180">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="c6972-181">**ヘルプ バブルを無効** にする : ヘルプ バブルは、オブジェクトを作成または編集するときにフィールドのコンテキスト ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="c6972-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="c6972-182">ヘルプ バブルをオフにしたり、無効になっている場合はオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c6972-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="c6972-183">**コマンド ログの表示**: EAC で構成した結果に基づいて、同等の PowerShell コマンドを表示する新しいウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="c6972-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="c6972-184">サポートされているブラウザー</span><span class="sxs-lookup"><span data-stu-id="c6972-184">Supported Browsers</span></span>

<span data-ttu-id="c6972-185">EAC を最大限に活用できるように、常に最新のブラウザー、Office クライアント、アプリを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6972-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="c6972-186">また、ソフトウェア更新プログラムも、利用可能になり次第インストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6972-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="c6972-187">サポートされているブラウザーとサービスのシステム要件の詳細については、「サービスのシステム要件」を[Office。](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="c6972-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="c6972-188">サポートされている言語</span><span class="sxs-lookup"><span data-stu-id="c6972-188">Supported languages</span></span>

<span data-ttu-id="c6972-189">次の言語がサポートされ、スタンドアロン EOP の EAC で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6972-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="c6972-190">アムハラ語</span><span class="sxs-lookup"><span data-stu-id="c6972-190">Amharic</span></span>
- <span data-ttu-id="c6972-191">アラビア語</span><span class="sxs-lookup"><span data-stu-id="c6972-191">Arabic</span></span>
- <span data-ttu-id="c6972-192">バスク語 (バスク)</span><span class="sxs-lookup"><span data-stu-id="c6972-192">Basque (Basque)</span></span>
- <span data-ttu-id="c6972-193">バングラ語 (インド)</span><span class="sxs-lookup"><span data-stu-id="c6972-193">Bengali (India)</span></span>
- <span data-ttu-id="c6972-194">ブルガリア語</span><span class="sxs-lookup"><span data-stu-id="c6972-194">Bulgarian</span></span>
- <span data-ttu-id="c6972-195">カタルニア語</span><span class="sxs-lookup"><span data-stu-id="c6972-195">Catalan</span></span>
- <span data-ttu-id="c6972-196">簡体字中国語</span><span class="sxs-lookup"><span data-stu-id="c6972-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="c6972-197">繁体字中国語</span><span class="sxs-lookup"><span data-stu-id="c6972-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="c6972-198">クロアチア語</span><span class="sxs-lookup"><span data-stu-id="c6972-198">Croatian</span></span>
- <span data-ttu-id="c6972-199">チェコ語</span><span class="sxs-lookup"><span data-stu-id="c6972-199">Czech</span></span>
- <span data-ttu-id="c6972-200">デンマーク語</span><span class="sxs-lookup"><span data-stu-id="c6972-200">Danish</span></span>
- <span data-ttu-id="c6972-201">オランダ語</span><span class="sxs-lookup"><span data-stu-id="c6972-201">Dutch</span></span>
- <span data-ttu-id="c6972-202">英語</span><span class="sxs-lookup"><span data-stu-id="c6972-202">English</span></span>
- <span data-ttu-id="c6972-203">エストニア語</span><span class="sxs-lookup"><span data-stu-id="c6972-203">Estonian</span></span>
- <span data-ttu-id="c6972-204">フィリピン語 (フィリピン)</span><span class="sxs-lookup"><span data-stu-id="c6972-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="c6972-205">フィンランド語</span><span class="sxs-lookup"><span data-stu-id="c6972-205">Finnish</span></span>
- <span data-ttu-id="c6972-206">フランス語</span><span class="sxs-lookup"><span data-stu-id="c6972-206">French</span></span>
- <span data-ttu-id="c6972-207">ガリシア語</span><span class="sxs-lookup"><span data-stu-id="c6972-207">Galician</span></span>
- <span data-ttu-id="c6972-208">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="c6972-208">German</span></span>
- <span data-ttu-id="c6972-209">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="c6972-209">Greek</span></span>
- <span data-ttu-id="c6972-210">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="c6972-210">Gujarati</span></span>
- <span data-ttu-id="c6972-211">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="c6972-211">Hebrew</span></span>
- <span data-ttu-id="c6972-212">ヒンディー語</span><span class="sxs-lookup"><span data-stu-id="c6972-212">Hindi</span></span>
- <span data-ttu-id="c6972-213">ハンガリー語</span><span class="sxs-lookup"><span data-stu-id="c6972-213">Hungarian</span></span>
- <span data-ttu-id="c6972-214">アイスランド語</span><span class="sxs-lookup"><span data-stu-id="c6972-214">Icelandic</span></span>
- <span data-ttu-id="c6972-215">インドネシア語</span><span class="sxs-lookup"><span data-stu-id="c6972-215">Indonesian</span></span>
- <span data-ttu-id="c6972-216">イタリア語</span><span class="sxs-lookup"><span data-stu-id="c6972-216">Italian</span></span>
- <span data-ttu-id="c6972-217">日本語</span><span class="sxs-lookup"><span data-stu-id="c6972-217">Japanese</span></span>
- <span data-ttu-id="c6972-218">カンナダ語</span><span class="sxs-lookup"><span data-stu-id="c6972-218">Kannada</span></span>
- <span data-ttu-id="c6972-219">カザフ語</span><span class="sxs-lookup"><span data-stu-id="c6972-219">Kazakh</span></span>
- <span data-ttu-id="c6972-220">スワヒリ語</span><span class="sxs-lookup"><span data-stu-id="c6972-220">Kiswahili</span></span>
- <span data-ttu-id="c6972-221">韓国語</span><span class="sxs-lookup"><span data-stu-id="c6972-221">Korean</span></span>
- <span data-ttu-id="c6972-222">ラトビア語</span><span class="sxs-lookup"><span data-stu-id="c6972-222">Latvian</span></span>
- <span data-ttu-id="c6972-223">リトアニア語</span><span class="sxs-lookup"><span data-stu-id="c6972-223">Lithuanian</span></span>
- <span data-ttu-id="c6972-224">マレー語 (ブルネイ・ダルサラーム国)</span><span class="sxs-lookup"><span data-stu-id="c6972-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="c6972-225">マレー語 (マレーシア)</span><span class="sxs-lookup"><span data-stu-id="c6972-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="c6972-226">マラヤーラム語</span><span class="sxs-lookup"><span data-stu-id="c6972-226">Malayalam</span></span>
- <span data-ttu-id="c6972-227">マラーティー語</span><span class="sxs-lookup"><span data-stu-id="c6972-227">Marathi</span></span>
- <span data-ttu-id="c6972-228">ノルウェー語 (ブークモール)</span><span class="sxs-lookup"><span data-stu-id="c6972-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="c6972-229">ノルウェー語 (ニーノシュク)</span><span class="sxs-lookup"><span data-stu-id="c6972-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="c6972-230">オリヤー語</span><span class="sxs-lookup"><span data-stu-id="c6972-230">Oriya</span></span>
- <span data-ttu-id="c6972-231">ペルシャ語</span><span class="sxs-lookup"><span data-stu-id="c6972-231">Persian</span></span>
- <span data-ttu-id="c6972-232">ポーランド語</span><span class="sxs-lookup"><span data-stu-id="c6972-232">Polish</span></span>
- <span data-ttu-id="c6972-233">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="c6972-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="c6972-234">ポルトガル語 (ポルトガル)</span><span class="sxs-lookup"><span data-stu-id="c6972-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="c6972-235">ルーマニア語</span><span class="sxs-lookup"><span data-stu-id="c6972-235">Romanian</span></span>
- <span data-ttu-id="c6972-236">ロシア語</span><span class="sxs-lookup"><span data-stu-id="c6972-236">Russian</span></span>
- <span data-ttu-id="c6972-237">セルビア語 (キリル、セルビア)</span><span class="sxs-lookup"><span data-stu-id="c6972-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="c6972-238">セルビア語 (ラテン)</span><span class="sxs-lookup"><span data-stu-id="c6972-238">Serbian (Latin)</span></span>
- <span data-ttu-id="c6972-239">スロバキア語</span><span class="sxs-lookup"><span data-stu-id="c6972-239">Slovak</span></span>
- <span data-ttu-id="c6972-240">スロベニア語</span><span class="sxs-lookup"><span data-stu-id="c6972-240">Slovenian</span></span>
- <span data-ttu-id="c6972-241">スペイン語</span><span class="sxs-lookup"><span data-stu-id="c6972-241">Spanish</span></span>
- <span data-ttu-id="c6972-242">スウェーデン語</span><span class="sxs-lookup"><span data-stu-id="c6972-242">Swedish</span></span>
- <span data-ttu-id="c6972-243">タミール語</span><span class="sxs-lookup"><span data-stu-id="c6972-243">Tamil</span></span>
- <span data-ttu-id="c6972-244">テルグ語</span><span class="sxs-lookup"><span data-stu-id="c6972-244">Telugu</span></span>
- <span data-ttu-id="c6972-245">タイ語</span><span class="sxs-lookup"><span data-stu-id="c6972-245">Thai</span></span>
- <span data-ttu-id="c6972-246">トルコ語</span><span class="sxs-lookup"><span data-stu-id="c6972-246">Turkish</span></span>
- <span data-ttu-id="c6972-247">ウクライナ語</span><span class="sxs-lookup"><span data-stu-id="c6972-247">Ukrainian</span></span>
- <span data-ttu-id="c6972-248">ウルドゥ語</span><span class="sxs-lookup"><span data-stu-id="c6972-248">Urdu</span></span>
- <span data-ttu-id="c6972-249">ベトナム語</span><span class="sxs-lookup"><span data-stu-id="c6972-249">Vietnamese</span></span>
- <span data-ttu-id="c6972-250">ウェールズ語</span><span class="sxs-lookup"><span data-stu-id="c6972-250">Welsh</span></span>
