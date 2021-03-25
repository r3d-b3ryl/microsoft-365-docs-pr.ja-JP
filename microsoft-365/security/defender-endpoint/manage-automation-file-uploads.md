---
title: オートメーション ファイルのアップロードを管理する
description: コンテンツ分析を有効にし、分析用に送信されるファイル拡張子とメール添付ファイル拡張機能を構成する
keywords: オートメーション、ファイル、アップロード、コンテンツ、分析、ファイル、拡張子、電子メール、添付ファイル
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
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185851"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="f2fc8-104">オートメーション ファイルのアップロードを管理する</span><span class="sxs-lookup"><span data-stu-id="f2fc8-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2fc8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f2fc8-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2fc8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f2fc8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2fc8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2fc8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f2fc8-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f2fc8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2fc8-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f2fc8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="f2fc8-110">コンテンツ分析機能を有効にして、特定のファイルと電子メールの添付ファイルをクラウドに自動的にアップロードして、自動調査で追加の検査を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2fc8-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="f2fc8-111">ファイル拡張子名とメール添付ファイル拡張子名を指定して、ファイルと電子メールの添付ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="f2fc8-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="f2fc8-112">たとえば、ファイルまたは添付ファイルの拡張子名として *exe* と *bat* を追加すると、それらの拡張子を持つすべてのファイルまたは添付ファイルが自動的にクラウドに送信され、自動調査中に追加の検査が行われます。</span><span class="sxs-lookup"><span data-stu-id="f2fc8-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="f2fc8-113">ファイル拡張子名と添付ファイル拡張名を追加します。</span><span class="sxs-lookup"><span data-stu-id="f2fc8-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="f2fc8-114">ナビゲーション ウィンドウで、[設定オートメーション ファイル  >  **のアップロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f2fc8-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="f2fc8-115">コンテンツ分析の設定を [オン] と [オフ]**の間で切り\*\*\*\*替えます**。</span><span class="sxs-lookup"><span data-stu-id="f2fc8-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="f2fc8-116">次の内線番号を構成し、内線番号をコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f2fc8-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="f2fc8-117">**ファイル拡張子の名前** - 電子メールの添付ファイルを除く疑わしいファイルは、追加の検査のために提出されます</span><span class="sxs-lookup"><span data-stu-id="f2fc8-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="f2fc8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2fc8-118">Related topics</span></span>
- [<span data-ttu-id="f2fc8-119">オートメーション フォルダーの除外を管理する</span><span class="sxs-lookup"><span data-stu-id="f2fc8-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)