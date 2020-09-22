---
title: パイロットの Microsoft の脅威保護プロジェクトの結果の概要
description: パイロットは、スコアカードを完成させる、レポートに関する調査結果を分析すること、および前進する方法を決定することによって、パイロットによる Microsoft の脅威保護プロジェクトを終了します。
keywords: Microsoft Threat Protection パイロット、パイロットによる microsoft の脅威保護プロジェクトを評価した後の作業、microsoft threat protection パイロットから展開への移行、サイバーセキュリティ、高度な脅威、企業セキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、および自動調査と修復、高度な検索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: d6e9dbc214cdbb7aaf6bf8922ca4eaf986f8a91c
ms.sourcegitcommit: dcbcd5ef278949c777059b0aa6db072e821f72dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "48173286"
---
# <a name="closing-and-summarizing-your-microsoft-threat-protection-pilot"></a><span data-ttu-id="76600-104">Microsoft の脅威保護パイロットの終了および概要</span><span class="sxs-lookup"><span data-stu-id="76600-104">Closing and summarizing your Microsoft Threat Protection pilot</span></span>  

<span data-ttu-id="76600-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="76600-105">**Applies to:**</span></span>
- <span data-ttu-id="76600-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="76600-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="76600-107">ドメインコントローラーでリモートでコードを実行する、高度なメモリのみ攻撃をシミュレートしています。</span><span class="sxs-lookup"><span data-stu-id="76600-107">You’ve just simulated an advanced memory-only attack that executed code remotely on a domain controller.</span></span> <span data-ttu-id="76600-108">Stealthy 悪意のあるアクティビティについて、Microsoft Defender ATP および Azure ATP が検出し、通知する方法を確認しました。</span><span class="sxs-lookup"><span data-stu-id="76600-108">You’ve seen how Microsoft Defender ATP and Azure ATP detects and alerts on stealthy malicious activity.</span></span> <span data-ttu-id="76600-109">また、Microsoft 365 セキュリティセンターポータルでは、さまざまなソースからのアラートが他のコンテキスト情報と共に1つのインシデントに配信され、SOC アナリストが調査して必要なアクションを実行できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="76600-109">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal, enabling SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="76600-110">また、ユーザーが添付ファイルを開いたときや保存したときに、そのクエリに基づいて検出を作成した受信メールを識別する高度な検索クエリも作成されています。</span><span class="sxs-lookup"><span data-stu-id="76600-110">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="76600-111">すべてのテストが終了した後、プロセスの最後に到達しました。</span><span class="sxs-lookup"><span data-stu-id="76600-111">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="76600-112">最終的な出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="76600-112">The final output should be:</span></span>
- <span data-ttu-id="76600-113">完了したスコアカード</span><span class="sxs-lookup"><span data-stu-id="76600-113">A completed scorecard</span></span>
- <span data-ttu-id="76600-114">パイロットの結果についての詳細なレポート</span><span class="sxs-lookup"><span data-stu-id="76600-114">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="76600-115">前方へ移動する方法の決定</span><span class="sxs-lookup"><span data-stu-id="76600-115">A decision on how to move forward</span></span>

<span data-ttu-id="76600-116">この情報は、社内関係者 ( [準備](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) 段階で特定したもの) と Microsoft の連絡先の両方に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76600-116">This information should be presented to both internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase)  and Microsoft contacts.</span></span> <span data-ttu-id="76600-117">これにより、すべてのフィードバックを使用して製品とドキュメントを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="76600-117">This ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="76600-118">このシミュレーションを楽しんでいただき、学んだことを実装し始めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76600-118">We hope you enjoyed this simulation and are encouraged to start implementing what you've learned.</span></span>


## <a name="next-step"></a><span data-ttu-id="76600-119">次のステップ</span><span class="sxs-lookup"><span data-stu-id="76600-119">Next step</span></span>
||
|:-------|
|<span data-ttu-id="76600-120">[Microsoft 365 ソリューションとアーキテクチャセンター](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center)を参照して、組織に適したソリューションとアーキテクチャを設計する方法について理解します。</span><span class="sxs-lookup"><span data-stu-id="76600-120">Browse through the [Microsoft 365 solution and architecture center](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center) to Understand how to design the solution and architecture that is right for your organization.</span></span>

