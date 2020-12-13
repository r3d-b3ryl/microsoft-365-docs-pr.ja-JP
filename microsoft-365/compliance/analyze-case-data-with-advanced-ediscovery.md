---
title: Advanced eDiscovery を使用してケース データを分析する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dce7a700-3b6e-435f-88ba-e4b82c0f2b26
description: 'Microsoft 365 Advanced eDiscovery でパラメーターの設定、オプションの実行、結果の表示を行う分析プロセスの概要について説明します。 '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 27b3c6d77ddbfc9d5c7ae7a727a403d93af70b35
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663174"
---
# <a name="analyze-case-data-with-advanced-ediscovery-classic"></a><span data-ttu-id="156b5-103">Advanced eDiscovery (クラシック) を使用してケース データを分析する</span><span class="sxs-lookup"><span data-stu-id="156b5-103">Analyze case data with Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="156b5-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="156b5-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="156b5-106">Advanced **eDiscovery** \> **での** 分析の準備プロセスでは、含まれるファイルに次の機能が適用されます。</span><span class="sxs-lookup"><span data-stu-id="156b5-106">The **Prepare** \> **Analyze** process in Advanced eDiscovery applies the following functionality to the included files:</span></span> 
  
- <span data-ttu-id="156b5-107">読み込まれたファイルを一意のファイル、重複、およびほぼ重複のグループに識別して整理します。</span><span class="sxs-lookup"><span data-stu-id="156b5-107">Identifies and organizes the loaded files into groups of unique files, duplicates, and near-duplicates.</span></span>
    
- <span data-ttu-id="156b5-108">電子メールの段階的な包括性に基づいて、電子メールを識別し、階層的に構造化された電子メール スレッドのグループに整理します。</span><span class="sxs-lookup"><span data-stu-id="156b5-108">Identifies and organizes emails into hierarchically structured groups of email threads, based on the progressive inclusiveness of the emails.</span></span>
    
- <span data-ttu-id="156b5-109">Advanced eDiscovery の処理とファイルのバッチ処理でテーマを使用できます。</span><span class="sxs-lookup"><span data-stu-id="156b5-109">Enables the use of Themes in Advanced eDiscovery processing and file batching.</span></span>
    
 <span data-ttu-id="156b5-110">分析を使用すると、次のように、パラメーターの設定、オプションの実行、結果の表示を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="156b5-110">Analyze allows you to set parameters, run options, and view the results, as follows:</span></span> 
  
- <span data-ttu-id="156b5-111">**セットアップの分析**: ファイルで Analyze を実行する前に設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="156b5-111">**Analyze setup**: Allows settings to be specified before running Analyze on the files.</span></span>
    
- <span data-ttu-id="156b5-112">**結果の分析**: 分析の指標を表示します。</span><span class="sxs-lookup"><span data-stu-id="156b5-112">**Analyze results**: Displays metrics of the analysis.</span></span> 
    
<span data-ttu-id="156b5-113">分析を実行する前に、ファイルを選択して処理する条件を定義します。ファイルの選択と処理には、読み込まれたファイルを分析するファイルや、各種類のファイルを送信する分析の種類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="156b5-113">Before running Analyze, define the criteria for selecting and processing files, including which loaded files will be analyzed and the type of analysis to which each type of file will be submitted.</span></span> 
  
## <a name="additional-resources-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="156b5-114">Advanced eDiscovery (クラシック) 分析に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="156b5-114">Additional resources for Advanced eDiscovery (classic) analysis</span></span>

[<span data-ttu-id="156b5-115">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="156b5-115">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="156b5-116">ドキュメントの類似性について</span><span class="sxs-lookup"><span data-stu-id="156b5-116">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="156b5-117">テキストを無視する設定</span><span class="sxs-lookup"><span data-stu-id="156b5-117">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="156b5-118">分析の詳細設定の設定</span><span class="sxs-lookup"><span data-stu-id="156b5-118">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="156b5-119">分析タスクの表示</span><span class="sxs-lookup"><span data-stu-id="156b5-119">Viewing Analyze tasks</span></span>](view-analyze-results-in-advanced-ediscovery.md)

