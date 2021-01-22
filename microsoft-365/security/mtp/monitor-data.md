---
title: データ監視&レポート - セキュリティ センター
description: Microsoft 365 セキュリティ センターで未承認のデータ漏えいにつながる可能性があるユーザー アクティビティを追跡する方法について説明します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, データ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: a71f7a7284c2734c4cab2d4e9501a17f4e9ec6e7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930440"
---
# <a name="data-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="c8253-104">Microsoft 365 セキュリティ センターでのデータの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="c8253-104">Data monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c8253-105">**データ** カテゴリは、無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c8253-105">The **Data** category helps track user activity that could lead to unauthorized data disclosure.</span></span> <span data-ttu-id="c8253-106">これらは、既存の DLP ポリシー レポートとサードパーティの DLP ポリシー一致レポートの再作業です。</span><span class="sxs-lookup"><span data-stu-id="c8253-106">They are the rework of existing DLP policy reports plus a third-party DLP policy match report.</span></span>

<span data-ttu-id="c8253-107">次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="c8253-107">You can see:</span></span>

- <span data-ttu-id="c8253-108">クラウド アプリから最も多くファイルを共有しているユーザー</span><span class="sxs-lookup"><span data-stu-id="c8253-108">Users who share the most files from cloud apps</span></span>
- <span data-ttu-id="c8253-109">発生した DLP ポリシーの一致の数</span><span class="sxs-lookup"><span data-stu-id="c8253-109">How many DLP policy matches occurred</span></span>
- <span data-ttu-id="c8253-110">DLP ポリシーの上書きの数または報告された誤検出の数</span><span class="sxs-lookup"><span data-stu-id="c8253-110">How many DLP policies overrides or false positives are reported</span></span>
- <span data-ttu-id="c8253-111">Microsoft Cloud App Security を介してサード パーティ製のクラウド サービスで発生した DLP ポリシーの一致の数</span><span class="sxs-lookup"><span data-stu-id="c8253-111">How many DLP policy matches happened in third-party cloud services via Microsoft Cloud App Security</span></span>

![レポート ページのデータ カテゴリ](../../media/data.png)
