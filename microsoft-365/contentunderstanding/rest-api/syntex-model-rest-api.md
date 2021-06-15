---
title: SharePoint Syntex ドキュメント理解モデル REST API
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: SharePoint Syntex ドキュメント理解モデル REST API の概要。
ms.openlocfilehash: 279c624bb818e5d8d33b476f997290269ff634cb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904313"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="56d61-103">SharePoint Syntex ドキュメント理解モデル REST API</span><span class="sxs-lookup"><span data-stu-id="56d61-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="56d61-104">SharePoint REST インターフェイスを使用して、ドキュメント理解モデルの作成、1 つ以上のライブラリへのモデルの適用または削除、モデルに関する情報の取得または更新を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="56d61-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="56d61-105">SharePoint Online (および SharePoint 2016 以降のオンプレミス) REST サービスでは、OData $batch クエリ オプションを使って、サービスに対する複数の要求を 1 つの呼び出しに統合できます。</span><span class="sxs-lookup"><span data-stu-id="56d61-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="56d61-106">詳細とコード サンプルへのリンクについては、[「REST API によりバッチ要求を発行する」](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d61-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56d61-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="56d61-107">Prerequisites</span></span>

<span data-ttu-id="56d61-108">作業の開始前に、次に示す事項について十分に理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="56d61-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="56d61-109">SharePoint REST サービスの概要</span><span class="sxs-lookup"><span data-stu-id="56d61-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [<span data-ttu-id="56d61-110">SharePoint REST エンドポイントを使用して基本的な操作を完了する</span><span class="sxs-lookup"><span data-stu-id="56d61-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a><span data-ttu-id="56d61-111">REST コマンド</span><span class="sxs-lookup"><span data-stu-id="56d61-111">REST commands</span></span>

<span data-ttu-id="56d61-112">Syntex ドキュメント理解モデルを操作するには、次の REST コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="56d61-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="56d61-113">[モデルの作成](rest-createmodel-method.md) – モデルとそれに関連付けられたコンテンツ タイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="56d61-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="56d61-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – SharePoint Syntex ドキュメント理解モデルに関する情報を取得または更新します。</span><span class="sxs-lookup"><span data-stu-id="56d61-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="56d61-115">[GetByTitle](rest-getbytitle-method.md) – モデル タイトルを使用して SharePoint Syntex ドキュメント理解モデルに関する情報を取得または更新します。</span><span class="sxs-lookup"><span data-stu-id="56d61-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="56d61-116">[モデルの適用](rest-applymodel-method.md) –トレーニング済みのドキュメント理解モデルを 1 つ以上のライブラリに適用 (または同期) します。</span><span class="sxs-lookup"><span data-stu-id="56d61-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="56d61-117">[モデルとライブラリの情報を取得](rest-getmodelandlibraryinfo.md) – モデルと、それが適用されているライブラリに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="56d61-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="56d61-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – SharePoint Syntex ドキュメント理解モデルの使用可能なモデル設定 (関連する保持ラベルとモデルの説明) を更新します。</span><span class="sxs-lookup"><span data-stu-id="56d61-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="56d61-119">[BatchDelete](rest-batchdelete-method.md) – 適用されたドキュメント理解モデルを 1 つ以上のライブラリから削除します。</span><span class="sxs-lookup"><span data-stu-id="56d61-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="56d61-120">[分類要求 の作成](rest-createclassificationrequest.md) – 適用されたモデルを使用して、指定したファイルを分類する要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="56d61-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="56d61-121">シナリオ</span><span class="sxs-lookup"><span data-stu-id="56d61-121">Scenarios</span></span>

<span data-ttu-id="56d61-122">メソッドの名前からは直感的に理解できないような、次に示すシナリオ例にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="56d61-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="56d61-123">詳細については、各手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d61-123">For more information, see each article.</span></span>

<span data-ttu-id="56d61-124">[モデル作成] メソッドは、モデル オブジェクトとそれに関連付けられたコンテンツ タイプのみを作成します。</span><span class="sxs-lookup"><span data-stu-id="56d61-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="56d61-125">ライブラリに適用する前に、まずコンテンツ センターでモデルをトレーニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56d61-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="56d61-126">[モデル適用] メソッドを使用して、ドキュメントを分類し、必要に応じて追加情報を抽出するようにターゲット ライブラリのモデルを構成します。</span><span class="sxs-lookup"><span data-stu-id="56d61-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="56d61-127">この API では、モデルを複数のライブラリにバッチ適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="56d61-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="56d61-128">[モデル削除] メソッドは、以前に適用された 1 つ以上のライブラリからモデルを削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="56d61-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="56d61-129">モデルを削除する場合は、まず、モデルが適用されたすべてのライブラリから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56d61-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="56d61-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="56d61-130">See also</span></span>

[<span data-ttu-id="56d61-131">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="56d61-131">Document understanding overview</span></span>](../document-understanding-overview.md)

