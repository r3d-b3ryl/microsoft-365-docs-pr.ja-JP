---
title: Microsoft 365 セキュリティセンターでのデータの監視とレポート
description: 許可されていないデータの開示につながる可能性があるユーザーアクティビティを追跡する方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、データ
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: b79625ba017bd30cc9d6b0153d101b16ec574e8c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600134"
---
# <a name="data-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="66b87-104">Microsoft 365 セキュリティセンターでのデータの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="66b87-104">Data monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="66b87-105">**データ** カテゴリは、無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="66b87-105">The **Data** category helps track user activity that could lead to unauthorized data disclosure.</span></span> <span data-ttu-id="66b87-106">これらは、既存の Office 365 DLP ポリシーレポートに加えて、サードパーティの DLP ポリシー一致レポートを作成したものです。</span><span class="sxs-lookup"><span data-stu-id="66b87-106">These are the rework of existing Office 365 DLP policy reports plus a third-party DLP policy match report.</span></span>

<span data-ttu-id="66b87-107">次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="66b87-107">You can see:</span></span>

* <span data-ttu-id="66b87-108">クラウド アプリから最も多くファイルを共有しているユーザー</span><span class="sxs-lookup"><span data-stu-id="66b87-108">Users who share the most files from cloud apps</span></span>
* <span data-ttu-id="66b87-109">一致した DLP ポリシーの数</span><span class="sxs-lookup"><span data-stu-id="66b87-109">How many DLP policy matches occurred</span></span>
* <span data-ttu-id="66b87-110">DLP ポリシーの上書きの数または報告された誤検出の数</span><span class="sxs-lookup"><span data-stu-id="66b87-110">How many DLP policies overrides or false positives are reported</span></span>
* <span data-ttu-id="66b87-111">Microsoft Cloud App Security を介してサードパーティのクラウドサービスで発生した DLP ポリシーの一致数</span><span class="sxs-lookup"><span data-stu-id="66b87-111">How many DLP policy matches happened in 3rd party cloud services via Microsoft Cloud App Security</span></span>

![レポートページのデータカテゴリ](../images/data.png)
