---
title: Python の基本 SDK のテスト
description: テスト ベースの SDK for Python の理解に関する詳細
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323127"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="4fcec-103">Python の基本 SDK のテスト</span><span class="sxs-lookup"><span data-stu-id="4fcec-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="4fcec-104">概要</span><span class="sxs-lookup"><span data-stu-id="4fcec-104">Overview</span></span>
<span data-ttu-id="4fcec-105">Test Base SDK を使用して、Azure テスト ベース リソースを操作できます。</span><span class="sxs-lookup"><span data-stu-id="4fcec-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="4fcec-106">(つまり、アプリケーション パッケージの管理、パッケージの作成、パッケージの編集、パッケージの削除を含む)</span><span class="sxs-lookup"><span data-stu-id="4fcec-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="4fcec-107">SDK では、取得できるテストの概要と分析結果が含まれます。scriptExecution、信頼性、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression。</span><span class="sxs-lookup"><span data-stu-id="4fcec-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="4fcec-108">テストベース SDK を使用すると、CI/CD パイプラインにテスト ベースを統合できます。</span><span class="sxs-lookup"><span data-stu-id="4fcec-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="4fcec-109">クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="4fcec-109">Client Library</span></span>

<span data-ttu-id="4fcec-110">ピップを使用してテストベース パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4fcec-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="4fcec-111">例</span><span class="sxs-lookup"><span data-stu-id="4fcec-111">Example</span></span>
