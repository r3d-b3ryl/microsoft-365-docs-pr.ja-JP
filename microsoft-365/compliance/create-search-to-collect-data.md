---
title: 検索を作成する
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
description: ''
ms.openlocfilehash: 4b740b07b59b7500b8f57584767796b7f31ae87d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635977"
---
# <a name="create-a-search"></a><span data-ttu-id="66fd3-102">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="66fd3-102">Create a search</span></span>

<span data-ttu-id="66fd3-103">ケースの [**検索**] タブで、[**新規検索**] をクリックしてウィザードに従って、新しい検索を作成できます。</span><span class="sxs-lookup"><span data-stu-id="66fd3-103">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![高度な電子情報開示ケースの検索ウィザード](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="66fd3-105">検索の名前を指定して説明を付ける</span><span class="sxs-lookup"><span data-stu-id="66fd3-105">Name the search and give it a description</span></span>

<span data-ttu-id="66fd3-106">ケースを含む各検索には、一意の名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="66fd3-106">Each search with a case should have a unique name.</span></span> <span data-ttu-id="66fd3-107">必要に応じて、検索の説明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="66fd3-107">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="66fd3-108">検索する保管担当者および custodial の場所を選択する</span><span class="sxs-lookup"><span data-stu-id="66fd3-108">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="66fd3-109">ケースに追加した保管担当者を指定して、検索する保管担当者のコンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="66fd3-109">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="66fd3-110">保管担当者を選択すると、保管担当者にマップされているすべてのデータソースに対して検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="66fd3-110">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="66fd3-111">保管担当者ごとに、選択したデータソースに対して検索を絞り込むオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="66fd3-111">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="66fd3-112">保管担当者を追加し、データソースを管理する方法の詳細については、「 [Work with 保管担当者](managing-custodians.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66fd3-112">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="66fd3-113">Custodial のダイヤル場所を選択する</span><span class="sxs-lookup"><span data-stu-id="66fd3-113">Choose non-custodial locations</span></span>

<span data-ttu-id="66fd3-114">場合によっては、保管担当者に関連付けられていないデータソースを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66fd3-114">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="66fd3-115">この場合は、検索する場所を指定するか、特定の Microsoft サービスのすべてのコンテンツの場所を検索する (すべての Exchange メールボックスまたはすべての SharePoint サイトや OneDrive アカウントを検索するなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="66fd3-115">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="66fd3-116">検索クエリと条件を定義する</span><span class="sxs-lookup"><span data-stu-id="66fd3-116">Define the search query and conditions</span></span>

<span data-ttu-id="66fd3-117">作成済みの条件カードを使用するか、またはキーワードクエリ言語 (KQL) を使用して、キーワードクエリと検索条件を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="66fd3-117">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="66fd3-118">詳細については、「 [Build search queries](building-search-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66fd3-118">For more information, see [Build search queries](building-search-queries.md).</span></span>
