---
title: レポートの監視と表示 - セキュリティ センター
description: Microsoft 365 セキュリティ センターが保護とセキュリティの状態の概要を一目で示す方法について説明します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, 状態
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
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930404"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="45e5d-104">Microsoft 365 セキュリティ センターでレポートを監視および表示する</span><span class="sxs-lookup"><span data-stu-id="45e5d-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="45e5d-105">Microsoft 365 Defender を体験したい場合</span><span class="sxs-lookup"><span data-stu-id="45e5d-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="45e5d-106">ラボ環境 [で評価したり、](https://aka.ms/mtp-trial-lab) パイロット プロジェクトを実 [稼働環境で実行することができます](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="45e5d-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="45e5d-107">Microsoft 365 セキュリティ センターは、Microsoft 365 環境全体の保護とセキュリティの状態の概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="45e5d-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="45e5d-108">セキュリティ センターには、 **さまざまな領域** をカバーするカードのホストを備えている [レポート] セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="45e5d-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="45e5d-109">セキュリティ アナリストと管理者は、毎日の運用の一環としてカードを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="45e5d-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="45e5d-110">ドリルダウン時に、カードは詳細なレポートを提供し、場合によっては管理オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="45e5d-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="45e5d-111">ビューをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="45e5d-111">Customize views</span></span>

<span data-ttu-id="45e5d-112">既定では、カードは次のカテゴリにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="45e5d-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="45e5d-113">[ID](monitor-and-report-identities.md) - ユーザー アカウントと資格情報</span><span class="sxs-lookup"><span data-stu-id="45e5d-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="45e5d-114">[データ](monitor-data.md) - 電子メールとドキュメントのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="45e5d-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="45e5d-115">[デバイス](monitor-devices.md) - コンピューター、携帯電話、その他のデバイス</span><span class="sxs-lookup"><span data-stu-id="45e5d-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="45e5d-116">[アプリ](monitor-apps.md) - プログラムと添付されたオンライン サービス</span><span class="sxs-lookup"><span data-stu-id="45e5d-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="45e5d-117">トピック別 **にグループ化に** 切り替え、カードを再配置し、次のトピックにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="45e5d-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="45e5d-118">**リスク** : リスクが高い可能性があるエンティティ (アカウントやデバイスなど) を強調表示するカード。</span><span class="sxs-lookup"><span data-stu-id="45e5d-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="45e5d-119">これらのカードは、新しい脅威キャンペーンや特権を持つクラウド アプリなど、リスクの可能性のあるソースも強調しています。</span><span class="sxs-lookup"><span data-stu-id="45e5d-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="45e5d-120">**検出の傾向** - 新しい脅威の検出、異常、ポリシー違反を強調表示するカード</span><span class="sxs-lookup"><span data-stu-id="45e5d-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="45e5d-121">**構成と正常性** - 管理サービスへのデバイス オンボーディング状態を含む、セキュリティ制御の構成と展開をカバーするカード</span><span class="sxs-lookup"><span data-stu-id="45e5d-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="45e5d-122">**その** 他 - 他のトピックに分類されていない他のすべてのカード</span><span class="sxs-lookup"><span data-stu-id="45e5d-122">**Other** - all other cards not categorized under other topics</span></span>
