---
title: 自動化フォルダーの除外を管理する
description: 自動化フォルダーの除外を追加して、自動調査から除外されるファイルを制御します。
keywords: 管理, 自動化, 除外, ブロック, クリーン, 悪意のある
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
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185839"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="501ef-104">自動化フォルダーの除外を管理する</span><span class="sxs-lookup"><span data-stu-id="501ef-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="501ef-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="501ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="501ef-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="501ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="501ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="501ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="501ef-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="501ef-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="501ef-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="501ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="501ef-110">オートメーション フォルダーの除外を使用すると、自動調査がスキップするフォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="501ef-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="501ef-111">スキップするフォルダーに関する次の属性を制御できます。</span><span class="sxs-lookup"><span data-stu-id="501ef-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="501ef-112">Folders</span><span class="sxs-lookup"><span data-stu-id="501ef-112">Folders</span></span> 
- <span data-ttu-id="501ef-113">ファイルの拡張機能</span><span class="sxs-lookup"><span data-stu-id="501ef-113">Extensions of the files</span></span>
- <span data-ttu-id="501ef-114">ファイル名</span><span class="sxs-lookup"><span data-stu-id="501ef-114">File names</span></span>


<span data-ttu-id="501ef-115">**フォルダー**</span><span class="sxs-lookup"><span data-stu-id="501ef-115">**Folders**</span></span><br>
<span data-ttu-id="501ef-116">スキップするフォルダーとそのサブフォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="501ef-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="501ef-117">現時点では、ディレクトリ内のファイルを除外する方法としてワイルドカードを使用する方法はまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="501ef-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="501ef-118">**拡張機能**</span><span class="sxs-lookup"><span data-stu-id="501ef-118">**Extensions**</span></span><br>
<span data-ttu-id="501ef-119">特定のディレクトリで除外する拡張機能を指定できます。</span><span class="sxs-lookup"><span data-stu-id="501ef-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="501ef-120">拡張機能は、攻撃者が除外フォルダーを使用して悪用を隠すのを防ぐ方法です。</span><span class="sxs-lookup"><span data-stu-id="501ef-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="501ef-121">拡張機能は、無視するファイルを明示的に定義します。</span><span class="sxs-lookup"><span data-stu-id="501ef-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="501ef-122">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="501ef-122">**File names**</span></span><br>
<span data-ttu-id="501ef-123">特定のディレクトリで除外するファイル名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="501ef-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="501ef-124">名前は、攻撃者が除外されたフォルダーを使用して悪用を隠すのを防ぐ方法です。</span><span class="sxs-lookup"><span data-stu-id="501ef-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="501ef-125">名前は、無視するファイルを明示的に定義します。</span><span class="sxs-lookup"><span data-stu-id="501ef-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="501ef-126">オートメーション フォルダーの除外を追加する</span><span class="sxs-lookup"><span data-stu-id="501ef-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="501ef-127">ナビゲーション ウィンドウで、[オートメーション]**フォルダー設定**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="501ef-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="501ef-128">[新 **しいフォルダーの除外] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="501ef-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="501ef-129">フォルダーの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="501ef-129">Enter the folder details:</span></span>

    - <span data-ttu-id="501ef-130">Folder</span><span class="sxs-lookup"><span data-stu-id="501ef-130">Folder</span></span>
    - <span data-ttu-id="501ef-131">拡張機能</span><span class="sxs-lookup"><span data-stu-id="501ef-131">Extensions</span></span>
    - <span data-ttu-id="501ef-132">ファイル名</span><span class="sxs-lookup"><span data-stu-id="501ef-132">File names</span></span>
    - <span data-ttu-id="501ef-133">説明</span><span class="sxs-lookup"><span data-stu-id="501ef-133">Description</span></span>
    

4. <span data-ttu-id="501ef-134">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="501ef-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="501ef-135">除外されたファイルを収集または調べる Live Response コマンドは、"ファイルが除外されました" というエラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="501ef-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="501ef-136">さらに、自動調査では除外されたアイテムは無視されます。</span><span class="sxs-lookup"><span data-stu-id="501ef-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="501ef-137">オートメーション フォルダーの除外を編集する</span><span class="sxs-lookup"><span data-stu-id="501ef-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="501ef-138">ナビゲーション ウィンドウで、[オートメーション]**フォルダー設定**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="501ef-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="501ef-139">フォルダーの **除外で** [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="501ef-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="501ef-140">ルールの詳細を更新し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="501ef-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="501ef-141">オートメーション フォルダーの除外を削除する</span><span class="sxs-lookup"><span data-stu-id="501ef-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="501ef-142">ナビゲーション ウィンドウで、[オートメーション]**フォルダー設定**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="501ef-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="501ef-143">[除外 **の削除] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="501ef-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="501ef-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="501ef-144">Related topics</span></span>
- [<span data-ttu-id="501ef-145">許可/ブロックされたリストの自動化を管理する</span><span class="sxs-lookup"><span data-stu-id="501ef-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="501ef-146">自動化ファイルのアップロードを管理する</span><span class="sxs-lookup"><span data-stu-id="501ef-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
