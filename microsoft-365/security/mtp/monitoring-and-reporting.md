---
title: レポートを監視および表示する-セキュリティセンター
description: Microsoft 365 セキュリティセンターが、保護とセキュリティの状態の概要を一目で確認できるようにする方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、状態
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
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356885"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="83d9d-104">Microsoft 365 セキュリティセンターのレポートを監視および表示する</span><span class="sxs-lookup"><span data-stu-id="83d9d-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="83d9d-105">Microsoft 365 Defender を利用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="83d9d-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="83d9d-106">[ラボ環境で評価](https://aka.ms/mtp-trial-lab)することも、[運用環境でパイロットプロジェクトを実行](https://aka.ms/m365d-pilotplaybook)することもできます。</span><span class="sxs-lookup"><span data-stu-id="83d9d-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="83d9d-107">Microsoft 365 セキュリティセンターは、Microsoft 365 環境全体の保護とセキュリティの状態の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="83d9d-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="83d9d-108">セキュリティセンターには、さまざまな分野をカバーするカードのホストを備えた **レポート** セクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="83d9d-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="83d9d-109">セキュリティアナリストと管理者は、日常業務の一部としてカードを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="83d9d-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="83d9d-110">ドリルダウンの場合、カードは詳細なレポートと、場合によっては管理オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="83d9d-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="83d9d-111">ビューをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="83d9d-111">Customize views</span></span>

<span data-ttu-id="83d9d-112">既定では、カードは次のカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="83d9d-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="83d9d-113">[Identity](monitor-and-report-identities.md) -ユーザーアカウントおよび資格情報</span><span class="sxs-lookup"><span data-stu-id="83d9d-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="83d9d-114">[データ](monitor-data.md) -電子メールとドキュメントのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="83d9d-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="83d9d-115">[デバイス](monitor-devices.md) -コンピューター、携帯電話、その他のデバイス</span><span class="sxs-lookup"><span data-stu-id="83d9d-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="83d9d-116">[アプリ](monitor-apps.md) -プログラムおよび添付されたオンラインサービス</span><span class="sxs-lookup"><span data-stu-id="83d9d-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="83d9d-117">[ **グループ化] トピック** に切り替えてカードを再配置し、次のトピックにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="83d9d-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="83d9d-118">危険にさらされる可能性がある、アカウントやデバイスなどのエンティティを強調する **リスク** カード。</span><span class="sxs-lookup"><span data-stu-id="83d9d-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="83d9d-119">これらのカードは、新しい脅威のキャンペーンや権限のあるクラウドアプリなど、潜在的なリスクのソースも強調しています。</span><span class="sxs-lookup"><span data-stu-id="83d9d-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="83d9d-120">**検出の傾向** -新しい脅威の検出、異常、およびポリシー違反を強調するカード</span><span class="sxs-lookup"><span data-stu-id="83d9d-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="83d9d-121">セキュリティ制御の構成と展開をカバーする **構成および正常性** カード (デバイスのオンボード状態を管理サービスに含める)</span><span class="sxs-lookup"><span data-stu-id="83d9d-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="83d9d-122">**その他-他** のトピックに分類されていない他のすべてのカード</span><span class="sxs-lookup"><span data-stu-id="83d9d-122">**Other** - all other cards not categorized under other topics</span></span>
