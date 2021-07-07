---
title: レビュー
description: オンボーディング後にセクションを確認します。
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323284"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a><span data-ttu-id="7fcf9-103">手順 6: 選択内容を確認してパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-103">Step 6: Review your selections to create your package.</span></span>

1.  <span data-ttu-id="7fcf9-104">このタブでは、サービスはテストの詳細を表示し、クイック完了チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-104">On this tab, the service displays your test details and runs a quick completeness check.</span></span> 

    <span data-ttu-id="7fcf9-105">メッセージ ```Validation passed``` は ```Validation failed``` 、次の手順に進めるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-105">A ```Validation passed``` or ```Validation failed``` message shows whether you can proceed to next steps or not.</span></span>

2.  <span data-ttu-id="7fcf9-106">テストの詳細を確認し、満たされた場合は、ボタンをクリック ```Create``` します。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-106">Review your test details and if satisfied, click on the ```Create``` button.</span></span> 

![検証の表示](Media/validation.png)

3.  <span data-ttu-id="7fcf9-108">これにより、パッケージが Test Base 環境にオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-108">This will onboard your package to the Test Base environment.</span></span> <span data-ttu-id="7fcf9-109">パッケージが正常に作成されると、Azure でパッケージを正常に実行できるかどうかを確認する自動テストがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-109">If your package is successfully created, an automated test which verifys whether your package can be successfully executed on Azure will be triggered.</span></span>

![成功した結果](Media/successful.png)

> [!Note]
> <span data-ttu-id="7fcf9-111">Azure portal から通知を受け取り、パッケージ検証の成功または失敗を通知します。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-111">You will get a notification from the Azure portal to notify you on the success or failure of the package verification.</span></span> 
>
> <span data-ttu-id="7fcf9-112">このプロセスには最大 24 時間かかる場合があるため、アクティブではない場合は Web ページがタイムアウトする可能性があるため、このオンデマンド実行が完了したという通知は通知されません。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-112">Please note that the process can take up to 24 hours, so it is likely your webpage will timeout if you are not active on it and hence, the notification will not inform you of the completion of this on-demand run.</span></span> 

  - <span data-ttu-id="7fcf9-113">Peradventure この問題が発生すると、タブでパッケージの状態を表示 ```Manage packages``` できます。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-113">Peradventure this happens, you can view the status of your package on the ```Manage packages``` tab.</span></span>

![パッケージを管理するためのイメージ](Media/managepackages.png)

  - <span data-ttu-id="7fcf9-115">テストの結果は、アップロード後数日後にスケジュールされた間隔で 、およびページを介して ```Test Summary``` ```Security Updates Results``` ```Feature Updates Results``` 確認できます。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-115">For succesful tests, their results can be seen via the ```Test Summary```, ```Security Updates Results``` and ```Feature Updates Results``` pages at scheduled intervals, often starting a few days after your upload.</span></span>
  
  - <span data-ttu-id="7fcf9-116">テストに失敗した場合は、新しいパッケージをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-116">While failed tests, require you to upload a new package.</span></span> 
  
    <span data-ttu-id="7fcf9-117">詳細な分析については ```test logs``` 、'とページから ```Security update results``` ダウンロード ```Feature updates results``` できます。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-117">You can download the ```test logs``` for further analysis from the ‘```Security update results``` and ```Feature updates results``` pages.</span></span>

  - <span data-ttu-id="7fcf9-118">テストエラーが繰り返し発生する場合は、エラーの testbasepreview@microsoft.com を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-118">If you experience repeated test failures, please reach out to testbasepreview@microsoft.com with details of your error.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7fcf9-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="7fcf9-119">Next steps</span></span>

<span data-ttu-id="7fcf9-120">以下のリンクからコンテンツ ガイドラインをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7fcf9-120">Discover our Content Guidelines via the link below.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="7fcf9-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="7fcf9-121">Next step</span></span>](contentguideline.md)
