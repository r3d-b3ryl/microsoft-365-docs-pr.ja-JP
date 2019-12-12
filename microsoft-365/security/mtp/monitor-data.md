---
title: Microsoft 365 セキュリティセンターでのデータの監視とレポート
description: 許可されていないデータの開示につながる可能性があるユーザーアクティビティを追跡する方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、データ
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 9952500b625599f4db588a5c9dc85404be383b6b
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910192"
---
# <a name="data-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="10da2-104">Microsoft 365 セキュリティセンターでのデータの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="10da2-104">Data monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="10da2-105">**データ** カテゴリは、無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="10da2-105">The **Data** category helps track user activity that could lead to unauthorized data disclosure.</span></span> <span data-ttu-id="10da2-106">これらは、既存の Office 365 DLP ポリシーレポートに加えて、サードパーティの DLP ポリシー一致レポートを作成したものです。</span><span class="sxs-lookup"><span data-stu-id="10da2-106">These are the rework of existing Office 365 DLP policy reports plus a third-party DLP policy match report.</span></span>

<span data-ttu-id="10da2-107">次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="10da2-107">You can see:</span></span>

* <span data-ttu-id="10da2-108">クラウド アプリから最も多くファイルを共有しているユーザー</span><span class="sxs-lookup"><span data-stu-id="10da2-108">Users who share the most files from cloud apps</span></span>
* <span data-ttu-id="10da2-109">一致した DLP ポリシーの数</span><span class="sxs-lookup"><span data-stu-id="10da2-109">How many DLP policy matches occurred</span></span>
* <span data-ttu-id="10da2-110">DLP ポリシーの上書きの数または報告された誤検出の数</span><span class="sxs-lookup"><span data-stu-id="10da2-110">How many DLP policies overrides or false positives are reported</span></span>
* <span data-ttu-id="10da2-111">Microsoft Cloud App Security を介してサードパーティのクラウドサービスで発生した DLP ポリシーの一致数</span><span class="sxs-lookup"><span data-stu-id="10da2-111">How many DLP policy matches happened in 3rd party cloud services via Microsoft Cloud App Security</span></span>

![レポートページのデータカテゴリ](../images/data.png)
