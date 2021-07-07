---
title: 機能更新プログラムの検証
description: 機能更新プログラムの検証のためにアプリケーションをアップロードする方法の詳細
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
ms.openlocfilehash: ce048796acd52e6daf8d4694cf72a0bd17c75ab4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323331"
---
# <a name="windows-feature-update-validation"></a><span data-ttu-id="ed669-103">Windows機能更新プログラムの検証</span><span class="sxs-lookup"><span data-stu-id="ed669-103">Windows Feature update validation</span></span>

<span data-ttu-id="ed669-104">Windows 10 または Windows 11 の次のリリースでアプリケーションがどのように実行されるのか、新しい機能を検証するための環境を維持せずに、Windows 必要ですか?</span><span class="sxs-lookup"><span data-stu-id="ed669-104">Do you need insights on how your applications will perform with the next release of Windows 10 or Windows 11 - without you maintaining an environment to validate new Windows features?</span></span> 

<span data-ttu-id="ed669-105">Azure 環境で Insider Program Windowsに対して検証テストを実行しますか?</span><span class="sxs-lookup"><span data-stu-id="ed669-105">Do you want to run your validation tests against Windows Insider Program builds in our Azure environment?</span></span>

<span data-ttu-id="ed669-106"> M365 のテスト ベースの機能更新プログラムの検証は、これらすべての機能を実現するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ed669-106">**Feature update** validation on Test Base for M365 can help you achieve all these and more!</span></span>

<span data-ttu-id="ed669-107">以下の手順の概要を参照して、M365 サービスの Test Base でこの新しい機能にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed669-107">Check out the step-by-step outline below to find out how to access this new capability in Test Base for M365 service.</span></span>

<span data-ttu-id="ed669-108">M365 のテスト ベースで始めるには、セルフサービス オンボーディング ポータルを使用してアプリケーション (および関連ファイル ```Feature update validation``` ) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ed669-108">To get started with ```Feature update validation``` in Test Base for M365, upload your applications (and related files) through the self-service onboarding portal.</span></span> 

<span data-ttu-id="ed669-109">以下に、テストの詳細を入力する手順を **示します**。</span><span class="sxs-lookup"><span data-stu-id="ed669-109">Highlighted below are the steps to take as you fill out the **Test details**:</span></span>

1. <span data-ttu-id="ed669-110">OS **更新プログラムの種類として** [機能更新プログラム] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed669-110">Select **Feature Update** as your OS update type:</span></span>

![機能更新プログラムの検証 OS の種類](Media/Feature-update-validation-01.png)

2. <span data-ttu-id="ed669-112">アプリケーションをWindowsする Insider チャネルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed669-112">Choose the Windows Insider Channel against which you want your application validated.</span></span>  

![機能更新プログラムの検証。](Media/Feature-update-validation-02.png)

3. <span data-ttu-id="ed669-115">テストのベースラインとして Windows 10 または Windows 11 の市場リリースを選択し (結果として得られる分析情報!)、パッケージの正常なオンボードに必要なその他の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="ed669-115">Select an in-market release of Windows 10 or Windows 11 as the baseline for your test (and resulting insights!) and provide the other details required to onboard your package successfully.</span></span>

![11 のリリース済みバージョンの Windows 10とWindows検証](Media/Feature-update-validation-03.png)

4. <span data-ttu-id="ed669-117">事前にリリースされた機能更新プログラムに対するアプリケーションの検証の結果を表示するには、Windows 10を参照してください ```Feature Updates Test Results``` 。</span><span class="sxs-lookup"><span data-stu-id="ed669-117">To view the results from the validation of your application against pre-released Windows 10 feature updates, visit the ```Feature Updates Test Results```.</span></span>

![機能更新プログラムの検証により、結果をすばやく確認できます](Media/Feature-update-validation-04.png)


## <a name="next-steps"></a><span data-ttu-id="ed669-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="ed669-119">Next steps</span></span>

<span data-ttu-id="ed669-120">次の記事に進み、メモリ回帰分析について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed669-120">Advance to the next article to get started with understanding Memory regression analysis.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ed669-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="ed669-121">Next step</span></span>](memory.md)

<!---
Add button for next page
-->
