---
title: デバイス タグの作成と管理
description: デバイス タグを使用してデバイスをグループ化してコンテキストをキャプチャし、インシデントの一部として動的なリスト作成を有効にする
keywords: タグ、デバイス タグ、デバイス グループ、グループ、修復、レベル、ルール、aad グループ、役割、割り当て、ランク
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4a64d3242a34ec8bf6d5646513170aa35dd3a94c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068891"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="3f104-104">デバイス タグの作成と管理</span><span class="sxs-lookup"><span data-stu-id="3f104-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3f104-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3f104-105">**Applies to:**</span></span>
- [<span data-ttu-id="3f104-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3f104-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3f104-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f104-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3f104-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="3f104-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3f104-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="3f104-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3f104-110">デバイスにタグを追加して、論理グループ所属を作成します。</span><span class="sxs-lookup"><span data-stu-id="3f104-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="3f104-111">デバイス タグは、ネットワークの適切なマッピングをサポートし、さまざまなタグを添付してコンテキストをキャプチャし、インシデントの一部として動的なリスト作成を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="3f104-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="3f104-112">タグは、[デバイス] リスト ビューの **フィルターとして、** またはデバイスをグループ化するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f104-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="3f104-113">デバイス グループ化の詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="3f104-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="3f104-114">デバイスにタグを追加するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f104-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="3f104-115">ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="3f104-115">Using the portal</span></span>
- <span data-ttu-id="3f104-116">レジストリ キー値の設定</span><span class="sxs-lookup"><span data-stu-id="3f104-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="3f104-117">タグがデバイスに追加される時間と、デバイスリストとデバイス ページの可用性の間に、いくつかの待機時間が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f104-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="3f104-118">API を使用してデバイス タグを追加するには、「デバイス タグ API を [追加または削除する」を参照してください](add-or-remove-machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="3f104-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="3f104-119">ポータルを使用してデバイス タグを追加および管理する</span><span class="sxs-lookup"><span data-stu-id="3f104-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="3f104-120">タグを管理するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f104-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="3f104-121">次のビューからデバイスを選択または検索できます。</span><span class="sxs-lookup"><span data-stu-id="3f104-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="3f104-122">**セキュリティ操作ダッシュボード** - [アクティブな通知を含むトップ デバイス] セクションからデバイス名を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f104-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="3f104-123">**アラート キュー** - 通知キューからデバイス アイコンの横にあるデバイス名を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f104-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="3f104-124">**[デバイスの** 一覧] - デバイスの一覧からデバイス名を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f104-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="3f104-125">**[検索]** ボックス - ドロップダウン メニューから [デバイス] を選択し、デバイス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f104-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="3f104-126">ファイルビューと IP ビューからアラート ページにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3f104-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="3f104-127">応答 **アクションの行から** [タグの管理] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f104-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![[タグの管理] ボタンのイメージ](images/manage-tags.png)

3. <span data-ttu-id="3f104-129">タグを検索または作成する入力</span><span class="sxs-lookup"><span data-stu-id="3f104-129">Type to find or create tags</span></span>

    ![デバイスにタグを追加するイメージ1](images/new-tags.png)

<span data-ttu-id="3f104-131">タグはデバイス ビューに追加され、[デバイス] リスト ビュー **にも反映** されます。</span><span class="sxs-lookup"><span data-stu-id="3f104-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="3f104-132">次に、[タグ] フィルター **を使用** して、関連するデバイスの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3f104-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="3f104-133">かっこを含むタグ名では、フィルター処理が機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f104-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="3f104-134">新しいタグを作成すると、既存のタグの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f104-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="3f104-135">一覧には、ポータルを通じて作成されたタグだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f104-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="3f104-136">クライアント デバイスから作成された既存のタグは表示されません。</span><span class="sxs-lookup"><span data-stu-id="3f104-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="3f104-137">このビューからタグを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f104-137">You can also delete tags from this view.</span></span>

![デバイスにタグを追加するイメージ2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="3f104-139">レジストリ キーの値を設定してデバイス タグを追加する</span><span class="sxs-lookup"><span data-stu-id="3f104-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="3f104-140">次のデバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f104-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="3f104-141">Windows 10 バージョン 1709 以降</span><span class="sxs-lookup"><span data-stu-id="3f104-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="3f104-142">Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="3f104-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="3f104-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3f104-143">Windows Server 2016</span></span>
>- <span data-ttu-id="3f104-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3f104-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="3f104-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="3f104-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="3f104-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3f104-146">Windows 8.1</span></span>
>- <span data-ttu-id="3f104-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="3f104-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="3f104-148">タグに設定できる最大文字数は 200 文字です。</span><span class="sxs-lookup"><span data-stu-id="3f104-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="3f104-149">類似のタグを持つデバイスは、デバイスの特定のリストにコンテキスト アクションを適用する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="3f104-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="3f104-150">デバイスにタグを追加するには、次のレジストリ キー エントリを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f104-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="3f104-151">レジストリ キー: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="3f104-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="3f104-152">レジストリ キーの値 (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="3f104-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="3f104-153">レジストリ キー のデータ: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="3f104-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="3f104-154">デバイス タグは、1 日に 1 回生成されるデバイス情報レポートの一部です。</span><span class="sxs-lookup"><span data-stu-id="3f104-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="3f104-155">代わりに、新しいデバイス情報レポートを転送するエンドポイントを再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f104-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="3f104-156">上記のレジストリ キーを使用して追加されたタグを削除する必要がある場合は、'Group' キーを削除する代わりにレジストリ キー データの内容をクリアします。</span><span class="sxs-lookup"><span data-stu-id="3f104-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
