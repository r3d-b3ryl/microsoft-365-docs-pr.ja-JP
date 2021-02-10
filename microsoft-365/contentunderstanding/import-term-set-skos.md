---
title: SKOS ベースの形式を使用して用語セットをインポートする
description: SKOS ベースのフォーマットを使用して用語セットをインポートする方法を学ぶ
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 3d6efce9b6414444793da54d9c6d7be47d6a9a5c
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145081"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="6c17d-103">SKOS ベースの形式を使用して用語セットをインポートする</span><span class="sxs-lookup"><span data-stu-id="6c17d-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="6c17d-104">SKOS ベースの形式を使用して用語セットをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="6c17d-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="6c17d-105">形式の詳細については、[SharePoint 分類 SKOS フォーマットのリファレンス](skos-format-reference.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c17d-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="6c17d-106">この機能には、[SharePoint Syntex](index.md) ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c17d-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="6c17d-107">インポートファイルは 20,000 語未満に保つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c17d-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="6c17d-108">ファイルが大きいと、検証とインポートにかかる時間が長くなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c17d-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="6c17d-109">SharePoint 管理センターで、[**コンテンツサービス**] を展開し、**用語ストア** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c17d-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="6c17d-110">用語セットをインポートする用語グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c17d-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="6c17d-111">コマンドバーで、[**用語セットのインポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c17d-111">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="6c17d-112">テンプレートとして使用するサンプルファイルをダウンロードする場合は、**sample-metadata.ttl** をクリックして、SKOS ベースの形式を使用するサンプル ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c17d-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="6c17d-113">インポートする用語セットと、用語を含むインポートファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c17d-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="6c17d-114">[**ファイル形式**]で、[**SKOS (\*.ttl)**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c17d-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="6c17d-115">[**参照**] をクリックして、インポートファイルに移動して追加します。</span><span class="sxs-lookup"><span data-stu-id="6c17d-115">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="6c17d-116">[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c17d-116">Click **Import**.</span></span> <span data-ttu-id="6c17d-117">インポートが完了するまでパネルを閉じないでください。</span><span class="sxs-lookup"><span data-stu-id="6c17d-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="6c17d-118">ファイルのインポートが成功すると、成功メッセージが表示され、用語ストアが更新され、新しく作成された用語セットに移動できます。</span><span class="sxs-lookup"><span data-stu-id="6c17d-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c17d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c17d-119">See also</span></span>

[<span data-ttu-id="6c17d-120">管理されたメタデータの概要</span><span class="sxs-lookup"><span data-stu-id="6c17d-120">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="6c17d-121">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="6c17d-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="6c17d-122">用語セット (サイトレベル) をインポートする</span><span class="sxs-lookup"><span data-stu-id="6c17d-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
