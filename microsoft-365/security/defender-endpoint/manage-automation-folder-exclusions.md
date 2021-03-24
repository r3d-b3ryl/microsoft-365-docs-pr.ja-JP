---
title: オートメーション フォルダーの除外を管理する
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
ms.openlocfilehash: fb398f1acbea4bd8f388c072f9706f9b2ca25175
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062156"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="da2c1-104">オートメーション フォルダーの除外を管理する</span><span class="sxs-lookup"><span data-stu-id="da2c1-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="da2c1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="da2c1-105">**Applies to:**</span></span>
- [<span data-ttu-id="da2c1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="da2c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="da2c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da2c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="da2c1-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="da2c1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="da2c1-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="da2c1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="da2c1-110">オートメーション フォルダーの除外を使用すると、自動調査がスキップするフォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="da2c1-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="da2c1-111">スキップするフォルダーに関する次の属性を制御できます。</span><span class="sxs-lookup"><span data-stu-id="da2c1-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="da2c1-112">Folders</span><span class="sxs-lookup"><span data-stu-id="da2c1-112">Folders</span></span> 
- <span data-ttu-id="da2c1-113">ファイルの拡張機能</span><span class="sxs-lookup"><span data-stu-id="da2c1-113">Extensions of the files</span></span>
- <span data-ttu-id="da2c1-114">ファイル名</span><span class="sxs-lookup"><span data-stu-id="da2c1-114">File names</span></span>


<span data-ttu-id="da2c1-115">**フォルダー**</span><span class="sxs-lookup"><span data-stu-id="da2c1-115">**Folders**</span></span><br>
<span data-ttu-id="da2c1-116">スキップするフォルダーとそのサブフォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="da2c1-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="da2c1-117">現時点では、ディレクトリ内のファイルを除外する方法としてワイルドカードを使用する方法はまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="da2c1-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="da2c1-118">**拡張機能**</span><span class="sxs-lookup"><span data-stu-id="da2c1-118">**Extensions**</span></span><br>
<span data-ttu-id="da2c1-119">特定のディレクトリで除外する拡張機能を指定できます。</span><span class="sxs-lookup"><span data-stu-id="da2c1-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="da2c1-120">拡張機能は、攻撃者が除外フォルダーを使用して悪用を隠すのを防ぐ方法です。</span><span class="sxs-lookup"><span data-stu-id="da2c1-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="da2c1-121">拡張機能は、無視するファイルを明示的に定義します。</span><span class="sxs-lookup"><span data-stu-id="da2c1-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="da2c1-122">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="da2c1-122">**File names**</span></span><br>
<span data-ttu-id="da2c1-123">特定のディレクトリで除外するファイル名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="da2c1-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="da2c1-124">名前は、攻撃者が除外されたフォルダーを使用して悪用を隠すのを防ぐ方法です。</span><span class="sxs-lookup"><span data-stu-id="da2c1-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="da2c1-125">名前は、無視するファイルを明示的に定義します。</span><span class="sxs-lookup"><span data-stu-id="da2c1-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="da2c1-126">オートメーション フォルダーの除外を追加する</span><span class="sxs-lookup"><span data-stu-id="da2c1-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="da2c1-127">ナビゲーション ウィンドウで、[設定オートメーション]**フォルダー**  >  **の除外を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da2c1-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="da2c1-128">[新 **しいフォルダーの除外] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="da2c1-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="da2c1-129">フォルダーの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="da2c1-129">Enter the folder details:</span></span>

    - <span data-ttu-id="da2c1-130">フォルダー</span><span class="sxs-lookup"><span data-stu-id="da2c1-130">Folder</span></span>
    - <span data-ttu-id="da2c1-131">拡張機能</span><span class="sxs-lookup"><span data-stu-id="da2c1-131">Extensions</span></span>
    - <span data-ttu-id="da2c1-132">ファイル名</span><span class="sxs-lookup"><span data-stu-id="da2c1-132">File names</span></span>
    - <span data-ttu-id="da2c1-133">説明</span><span class="sxs-lookup"><span data-stu-id="da2c1-133">Description</span></span>
    

4. <span data-ttu-id="da2c1-134">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da2c1-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="da2c1-135">除外されたファイルを収集または調べる Live Response コマンドは、"ファイルが除外されました" というエラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="da2c1-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="da2c1-136">さらに、自動調査では除外されたアイテムは無視されます。</span><span class="sxs-lookup"><span data-stu-id="da2c1-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="da2c1-137">オートメーション フォルダーの除外を編集する</span><span class="sxs-lookup"><span data-stu-id="da2c1-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="da2c1-138">ナビゲーション ウィンドウで、[設定オートメーション]**フォルダー**  >  **の除外を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da2c1-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="da2c1-139">フォルダーの **除外で** [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da2c1-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="da2c1-140">ルールの詳細を更新し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="da2c1-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="da2c1-141">オートメーション フォルダーの除外を削除する</span><span class="sxs-lookup"><span data-stu-id="da2c1-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="da2c1-142">ナビゲーション ウィンドウで、[設定オートメーション]**フォルダー**  >  **の除外を選択します**。</span><span class="sxs-lookup"><span data-stu-id="da2c1-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="da2c1-143">[除外 **の削除] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="da2c1-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="da2c1-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="da2c1-144">Related topics</span></span>
- [<span data-ttu-id="da2c1-145">許可/ブロックされたリストの自動化を管理する</span><span class="sxs-lookup"><span data-stu-id="da2c1-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="da2c1-146">オートメーション ファイルのアップロードを管理する</span><span class="sxs-lookup"><span data-stu-id="da2c1-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
