---
title: Microsoft Defender ウイルス対策を評価する
description: すべてのサイズの企業は、このガイドを使用して、ユーザーが提供する保護を評価し、Microsoft Defender ウイルス対策テストWindows 10。
keywords: Microsoft Defender ウイルス対策、クラウド保護、クラウド、マルウェア対策、セキュリティ、防御者、評価、テスト、保護、比較、リアルタイム保護
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4f789ab80d48966d4cf922811d05d74882d728fe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274738"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="07fa3-104">Microsoft Defender ウイルス対策を評価する</span><span class="sxs-lookup"><span data-stu-id="07fa3-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="07fa3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="07fa3-105">**Applies to:**</span></span>

- [<span data-ttu-id="07fa3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="07fa3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="07fa3-107">このガイドを使用して、ウイルス、マルウェアMicrosoft Defender ウイルス対策望ましくない可能性のあるアプリケーションからユーザーを保護する方法を判断します。</span><span class="sxs-lookup"><span data-stu-id="07fa3-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="07fa3-108">Microsoft Defender for Endpoint のデモ Web サイト demo.wd.microsoft.com、次 [の機能が](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 動作し、動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="07fa3-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="07fa3-109">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="07fa3-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="07fa3-110">高速学習 (一目でブロックを含む)</span><span class="sxs-lookup"><span data-stu-id="07fa3-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="07fa3-111">望ましくない可能性があるアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="07fa3-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="07fa3-112">小規模企業と大規模企業の両方で利用できる Microsoft Defender ウイルス対策の重要な次世代保護機能と、ネットワーク全体でマルウェアの検出と保護を強化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07fa3-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="07fa3-113">各設定を個別に構成して評価するか、一度にすべて構成するか選択できます。</span><span class="sxs-lookup"><span data-stu-id="07fa3-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="07fa3-114">一般的な評価シナリオに基づいて同様の設定をグループ化し、PowerShell を使用して設定を有効にする手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="07fa3-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="07fa3-115">このガイドは、オフラインで表示するために PDF 形式で提供されています。</span><span class="sxs-lookup"><span data-stu-id="07fa3-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="07fa3-116">ガイドを PDF 形式でダウンロードする</span><span class="sxs-lookup"><span data-stu-id="07fa3-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="07fa3-117">また、ガイドに記載されている設定を自動的に有効にする PowerShell をダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="07fa3-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="07fa3-118">上記の PDF ダウンロードと共にスクリプトを取得するか、PowerShell ギャラリーから個別にスクリプトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="07fa3-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="07fa3-119">PowerShell スクリプトをダウンロードして、設定を自動的に構成する</span><span class="sxs-lookup"><span data-stu-id="07fa3-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="07fa3-120">このガイドは現在、コンピューターの単一コンピューター評価を目的Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="07fa3-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="07fa3-121">このガイドのすべての設定を有効にすると、実際の展開に適していない場合があります。</span><span class="sxs-lookup"><span data-stu-id="07fa3-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="07fa3-122">ネットワーク全体での実際の展開と監視に関する最新の推奨事項については、「deploy Microsoft Defender ウイルス対策」を[参照Microsoft Defender ウイルス対策。](deploy-manage-report-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="07fa3-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="07fa3-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="07fa3-123">Related topics</span></span>

- [<span data-ttu-id="07fa3-124">Microsoft Defender ウイルス対策のWindows 10</span><span class="sxs-lookup"><span data-stu-id="07fa3-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="07fa3-125">展開Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="07fa3-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)