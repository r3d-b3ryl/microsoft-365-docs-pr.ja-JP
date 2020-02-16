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
ms.openlocfilehash: 8fa959de5806eccf76b0e83103c0274d0eb86da0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084782"
---
# <a name="data-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="fefbf-104">Microsoft 365 セキュリティセンターでのデータの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="fefbf-104">Data monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="fefbf-105">**データ** カテゴリは、無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fefbf-105">The **Data** category helps track user activity that could lead to unauthorized data disclosure.</span></span> <span data-ttu-id="fefbf-106">これらは、既存の Office 365 DLP ポリシーレポートに加えて、サードパーティの DLP ポリシー一致レポートを作成したものです。</span><span class="sxs-lookup"><span data-stu-id="fefbf-106">These are the rework of existing Office 365 DLP policy reports plus a third-party DLP policy match report.</span></span>

<span data-ttu-id="fefbf-107">次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="fefbf-107">You can see:</span></span>

* <span data-ttu-id="fefbf-108">クラウド アプリから最も多くファイルを共有しているユーザー</span><span class="sxs-lookup"><span data-stu-id="fefbf-108">Users who share the most files from cloud apps</span></span>
* <span data-ttu-id="fefbf-109">一致した DLP ポリシーの数</span><span class="sxs-lookup"><span data-stu-id="fefbf-109">How many DLP policy matches occurred</span></span>
* <span data-ttu-id="fefbf-110">DLP ポリシーの上書きの数または報告された誤検出の数</span><span class="sxs-lookup"><span data-stu-id="fefbf-110">How many DLP policies overrides or false positives are reported</span></span>
* <span data-ttu-id="fefbf-111">Microsoft Cloud App Security を介してサードパーティのクラウドサービスで発生した DLP ポリシーの一致数</span><span class="sxs-lookup"><span data-stu-id="fefbf-111">How many DLP policy matches happened in 3rd party cloud services via Microsoft Cloud App Security</span></span>

![レポートページのデータカテゴリ](../../media/data.png)
