---
title: データ監視 & レポート作成-セキュリティセンター
description: Microsoft 365 セキュリティセンターで承認されていないデータが漏洩する可能性があるユーザーアクティビティを追跡する方法について説明します。
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 76b70f20a8bbeb3b79fa8f6b3847245449cb8823
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413164"
---
# <a name="data-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="b6215-104">Microsoft 365 セキュリティセンターでのデータの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="b6215-104">Data monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b6215-105">**データ** カテゴリは、無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6215-105">The **Data** category helps track user activity that could lead to unauthorized data disclosure.</span></span> <span data-ttu-id="b6215-106">既存の DLP ポリシーレポートの再作業と、サードパーティの DLP ポリシー一致レポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6215-106">They are the rework of existing DLP policy reports plus a third-party DLP policy match report.</span></span>

<span data-ttu-id="b6215-107">次のことがわかります。</span><span class="sxs-lookup"><span data-stu-id="b6215-107">You can see:</span></span>

- <span data-ttu-id="b6215-108">クラウド アプリから最も多くファイルを共有しているユーザー</span><span class="sxs-lookup"><span data-stu-id="b6215-108">Users who share the most files from cloud apps</span></span>
- <span data-ttu-id="b6215-109">一致した DLP ポリシーの数</span><span class="sxs-lookup"><span data-stu-id="b6215-109">How many DLP policy matches occurred</span></span>
- <span data-ttu-id="b6215-110">DLP ポリシーの上書きの数または報告された誤検出の数</span><span class="sxs-lookup"><span data-stu-id="b6215-110">How many DLP policies overrides or false positives are reported</span></span>
- <span data-ttu-id="b6215-111">Microsoft Cloud App Security を介してサードパーティ製のクラウドサービスで発生した DLP ポリシーの一致数</span><span class="sxs-lookup"><span data-stu-id="b6215-111">How many DLP policy matches happened in third-party cloud services via Microsoft Cloud App Security</span></span>

![レポートページのデータカテゴリ](../../media/data.png)
