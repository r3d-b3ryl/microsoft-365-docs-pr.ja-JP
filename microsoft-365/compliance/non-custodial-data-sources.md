---
title: 詳細な電子情報開示ケースに非 custodial データソースを追加する
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
description: 詳細な電子情報開示ケースに非 custodial データソースを追加して、データソースにホールドを配置することができます。 非 custodial データソースは再インデックス化であるため、部分的にインデックスが作成されていると見なされたコンテンツはすべて再処理され、完全かつ迅速に検索できるようになります。
ms.openlocfilehash: 2009a8cc82dc9407e9871409e85cdcd321ea9bb0
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024747"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="abf6c-104">詳細な電子情報開示ケースに非 custodial データソースを追加する</span><span class="sxs-lookup"><span data-stu-id="abf6c-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="abf6c-105">高度な電子情報開示のケースでは、Microsoft 365 データソースを保管担当者に関連付けするためのニーズを常に満たすわけではありません。</span><span class="sxs-lookup"><span data-stu-id="abf6c-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="abf6c-106">ただし、そのデータを検索して、レビューセットに追加して確認するには、そのデータをケースに関連付ける必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="abf6c-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="abf6c-107">*非 custodial データソース*という新しい機能を使用すると、データを保管担当者に関連付けせずにケースにデータを追加できます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="abf6c-108">また、保管担当者に関連付けられているデータに使用可能な、非 custodial データに対して、同じ高度な電子情報開示機能を適用します。</span><span class="sxs-lookup"><span data-stu-id="abf6c-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="abf6c-109">非 custodial データに適用できる最も便利な機能は2つあります。これは、[拡張インデックス](indexing-custodian-data.md)を使用して、そのデータを保持し、処理することです。</span><span class="sxs-lookup"><span data-stu-id="abf6c-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="abf6c-110">非 custodial データソースを追加する</span><span class="sxs-lookup"><span data-stu-id="abf6c-110">Add a non-custodial data source</span></span>

<span data-ttu-id="abf6c-111">次の手順に従って、高度な電子情報開示ケースで、非 custodial データソースを追加して管理します。</span><span class="sxs-lookup"><span data-stu-id="abf6c-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="abf6c-112">[**高度な電子情報開示**のホーム] ページで、データを追加するケースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="abf6c-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="abf6c-113">[**ソース**] ページで、[**データの場所**] タブをクリックし、[データの**場所の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abf6c-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="abf6c-114">[**データの場所の追加**] をクリックし、ケースに追加するデータソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="abf6c-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="abf6c-115">複数のメールボックスとサイトを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="abf6c-116">ウィザードの [**場所の選択**] ページで、メールボックスまたはサイト (またはその両方) を非 custodial データソースとしてケースに追加します。</span><span class="sxs-lookup"><span data-stu-id="abf6c-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="abf6c-117">データソースを追加した後、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abf6c-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="abf6c-118">[**インプレース保持**] ページで、関連するチェックボックスをオンまたはオフにして、保留にするデータソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="abf6c-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="abf6c-119">保留リストの選択を確認し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="abf6c-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="abf6c-120">追加したそれぞれの非 custodial データソースは、[**データソース**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="abf6c-121">また、"*非 custodial* " という名前のジョブが作成され、ケースの [**ジョブ**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-121">Also, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="abf6c-122">ジョブが作成されると、開始された高度なインデックス作成プロセスとデータソースは再インデックス化になります。</span><span class="sxs-lookup"><span data-stu-id="abf6c-122">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="abf6c-123">非 custodial データソースの保持を管理する</span><span class="sxs-lookup"><span data-stu-id="abf6c-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="abf6c-124">非 custodial データソースにホールドを設定すると、そのケースのすべての非 wi-fi ダイヤルデータソースを含む保持ポリシーが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="abf6c-125">その他の非 custodial データソースを保持するように設定すると、この保留ポリシーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="abf6c-126">ケースの**ホーム**ページで、[**保留**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="abf6c-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="abf6c-127">[**ホールド**] ページで、[ \*\*Ncdshold- \<GUID\> \*\*] をクリックします。この場合、GUID 値はケースに対して一意です。</span><span class="sxs-lookup"><span data-stu-id="abf6c-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="abf6c-128">[ポップアップ] ページで、[**保留リストの編集**] をクリックして、保留中のすべての非 wi-fi ダイヤルデータソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="abf6c-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="abf6c-129">次の管理タスクは、非 custodial データソースで実行できます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="abf6c-130">保持を編集して、すべての非 wi-fi ダイヤルデータソースに適用されるクエリベースの保持を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="abf6c-131">保持から、非 custodial データソースを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="abf6c-132">データソースを解放しても、そのケースからは、非 custodial データソースは削除されません。</span><span class="sxs-lookup"><span data-stu-id="abf6c-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="abf6c-133">データソースに対して行われたホールドのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="abf6c-133">It only removes the hold that was placed on the data source.</span></span>
