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
description: ケース内の検索の保管担当者と保管場所を作成、定義、および選択するAdvanced eDiscoveryします。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035769"
---
# <a name="create-a-search"></a><span data-ttu-id="8e776-103">検索を作成する</span><span class="sxs-lookup"><span data-stu-id="8e776-103">Create a search</span></span>

<span data-ttu-id="8e776-104">ケースの **[検索]** タブで、[新しい検索] をクリックし、ウィザードに従って **新しい検索** を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8e776-104">On the **Searches** tab in your case, you can create a new search by clicking **New search** and following the wizard.</span></span>

![検索ケースの検索ウィザードAdvanced eDiscoveryする](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a><span data-ttu-id="8e776-106">検索に名前を付け、説明を付け</span><span class="sxs-lookup"><span data-stu-id="8e776-106">Name the search and give it a description</span></span>

<span data-ttu-id="8e776-107">ケースを含む各検索には、一意の名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="8e776-107">Each search with a case should have a unique name.</span></span> <span data-ttu-id="8e776-108">必要に応じて、検索の説明を入力できます。</span><span class="sxs-lookup"><span data-stu-id="8e776-108">You can optionally provide a description for your search.</span></span> 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a><span data-ttu-id="8e776-109">検索する保管担当者と保管場所を選択する</span><span class="sxs-lookup"><span data-stu-id="8e776-109">Choose the custodians and custodial locations to search</span></span>

<span data-ttu-id="8e776-110">ケースに追加した保管担当者を指定して、検索する保管担当者コンテンツの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="8e776-110">Choose custodian content locations to search by specifying that custodians you have added to the case.</span></span> <span data-ttu-id="8e776-111">カストディアンを選択すると、カストディアンにマップされているすべてのデータ ソースに対して検索が実行されます。</span><span class="sxs-lookup"><span data-stu-id="8e776-111">By selecting a custodian, you will run the search against all data sources mapped to the custodian.</span></span> <span data-ttu-id="8e776-112">また、各保管担当者の選択したデータ ソースに検索を絞り込むオプションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="8e776-112">You also have the option to narrow the search to selected data sources for each custodian.</span></span> <span data-ttu-id="8e776-113">カストディアンを追加してデータ ソースを管理する方法の詳細については、「保管担当者と一緒に作業する [」を参照してください](managing-custodians.md)。</span><span class="sxs-lookup"><span data-stu-id="8e776-113">For more information about how to add custodians and manage their data sources, see [Work with custodians](managing-custodians.md).</span></span>

## <a name="choose-non-custodial-locations"></a><span data-ttu-id="8e776-114">保管以外の場所を選択する</span><span class="sxs-lookup"><span data-stu-id="8e776-114">Choose non-custodial locations</span></span>

<span data-ttu-id="8e776-115">カストディアンに関連付けされていないデータ ソースを検索する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e776-115">In some cases, you may want to search data sources that are not associated with a custodian.</span></span> <span data-ttu-id="8e776-116">この場合、検索する場所を指定するか、特定の Microsoft サービスのすべてのコンテンツの場所 (すべての Exchange メールボックスまたはすべての SharePoint サイトと OneDrive アカウントの検索など) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8e776-116">In this case, you can specify the locations you want to search, or choose to search all content locations for a specific Microsoft service (such as searching all Exchange mailboxes or all SharePoint sites and OneDrive accounts).</span></span>

## <a name="define-the-search-query-and-conditions"></a><span data-ttu-id="8e776-117">検索クエリと条件を定義する</span><span class="sxs-lookup"><span data-stu-id="8e776-117">Define the search query and conditions</span></span>

<span data-ttu-id="8e776-118">あらかじめ構築された条件カードを使用するか、キーワード クエリ言語 (KQL) を使用して、キーワード クエリと検索の条件を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8e776-118">You can define the keywords query and any conditions for the search by using the pre-built condition cards or using Keyword Query Language (KQL).</span></span> <span data-ttu-id="8e776-119">詳細については、「検索クエリの [ビルド」を参照してください](building-search-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="8e776-119">For more information, see [Build search queries](building-search-queries.md).</span></span>
