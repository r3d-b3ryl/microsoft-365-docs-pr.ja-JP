---
title: 高度な電子情報開示でケースデータをエクスポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 高度な電子情報開示ケースでプレゼンテーションや外部レビューのためにレビューセットからコンテンツをエクスポートまたはダウンロードする方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 114264f342a51f3ce68696f321cf7c6e929dc6d1
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726476"
---
# <a name="export-case-data-in-advanced-ediscovery"></a><span data-ttu-id="49d69-103">高度な電子情報開示でケースデータをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="49d69-103">Export case data in Advanced eDiscovery</span></span>

<span data-ttu-id="49d69-104">レビューセットからデータをエクスポートするには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="49d69-104">There are three ways to export data from a review set:</span></span>

<span data-ttu-id="49d69-105">**ダウンロード:** ネイティブファイルの小さなセットを (ブラウザーを使用して) ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="49d69-105">**Download:** Download (by using a browser) a small set of native files.</span></span> <span data-ttu-id="49d69-106">これは、データの小さなセットをエクスポートする最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="49d69-106">This is the quickest way to export a small set of data.</span></span> <span data-ttu-id="49d69-107">このメソッドは、ネイティブファイル名を保持します。</span><span class="sxs-lookup"><span data-stu-id="49d69-107">This method preserves the native file names.</span></span>

<span data-ttu-id="49d69-108">**エクスポート:** エクスポートするデータをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="49d69-108">**Export:** Customize what data is exported.</span></span> <span data-ttu-id="49d69-109">これには、PDF ファイルに保存されているファイルメタデータ、ネイティブファイル、テキストファイル、およびがドキュメントをエクスポートすることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="49d69-109">This includes exporting file metadata, native files, text files, and redacted documents that have been saved to a PDF file.</span></span> <span data-ttu-id="49d69-110">エクスポートされたデータを Azure ストレージの場所にアップロードした後、それをローカルコンピューターにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="49d69-110">After the exported data is uploaded to an Azure Storage location, you can download it to a local computer.</span></span> <span data-ttu-id="49d69-111">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49d69-111">For more information, see:</span></span>

- [<span data-ttu-id="49d69-112">レビュー セットからドキュメントをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="49d69-112">Export documents from a review set</span></span>](export-documents-from-review-set.md)

- [<span data-ttu-id="49d69-113">エクスポート ジョブのダウンロード</span><span class="sxs-lookup"><span data-stu-id="49d69-113">Download export jobs</span></span>](download-export-jobs.md)

<span data-ttu-id="49d69-114">**別のレビューセットに追加します。** 1つのレビューセットから別のレビューセットにデータをコピーします。</span><span class="sxs-lookup"><span data-stu-id="49d69-114">**Add to another review set:** Copy data from one review set to a different review set.</span></span> <span data-ttu-id="49d69-115">詳細については、「 [1 つのレビューセットから別のレビューセットにデータを追加する](add-data-to-review-set-from-another-review-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49d69-115">For more information, see [Add data from one review set to another review set](add-data-to-review-set-from-another-review-set.md).</span></span>

> [!NOTE]
> <span data-ttu-id="49d69-116">Microsoft 365 では、データがハッシュされ、検証のために出力ファイルにこれらのハッシュが提供されます。</span><span class="sxs-lookup"><span data-stu-id="49d69-116">In Microsoft 365, data is hashed and those hashes are provided in the output file for verification purposes.</span></span> <span data-ttu-id="49d69-117">これは、コレクション統計、ロードセットレポート、エクスポートレポート (エクスポートロードファイルを含む) など、監査ログおよびレポート機能によって補完されます。</span><span class="sxs-lookup"><span data-stu-id="49d69-117">This is supplemented by audit logs and reporting functionality, such as collection statistics, load set reports, and export reports (including the export load file).</span></span>
