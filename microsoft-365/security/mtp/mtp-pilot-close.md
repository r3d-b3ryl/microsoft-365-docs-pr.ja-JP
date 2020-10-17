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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: e56ba8933947c37db3e558ef36dd6d305915040f
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487626"
---
# <a name="closing-and-summarizing-your-microsoft-threat-protection-pilot"></a><span data-ttu-id="4f547-104">Microsoft の脅威保護パイロットの終了および概要</span><span class="sxs-lookup"><span data-stu-id="4f547-104">Closing and summarizing your Microsoft Threat Protection pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4f547-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4f547-105">**Applies to:**</span></span>
- <span data-ttu-id="4f547-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4f547-106">Microsoft Threat Protection</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="パイロットを計画する Microsoft の脅威保護プロジェクト" />
      <br/><span data-ttu-id="4f547-108">計画 </a></span><span class="sxs-lookup"><span data-stu-id="4f547-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境の準備" />
      <br/><span data-ttu-id="4f547-110">作る </a></span><span class="sxs-lookup"><span data-stu-id="4f547-110">Prepare </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Microsoft の脅威保護攻撃のシミュレーションを実行する" />
      <br/><span data-ttu-id="4f547-112">攻撃をシミュレートする </a></span><span class="sxs-lookup"><span data-stu-id="4f547-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Microsoft の脅威保護パイロットの終了と概要" />
      <br/><span data-ttu-id="4f547-114">閉じて概要をまとめる </a></span><span class="sxs-lookup"><span data-stu-id="4f547-114">Close and summarize </a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="4f547-115">現在、決算フェーズと要約段階になっています。</span><span class="sxs-lookup"><span data-stu-id="4f547-115">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="4f547-116">ドメインコントローラー上でコードをリモートで実行する、高度なメモリのみのアタックシミュレーションが実行されました。</span><span class="sxs-lookup"><span data-stu-id="4f547-116">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="4f547-117">Microsoft Defender ATP と Azure ATP が stealthy 悪意のあるアクティビティについての通知を検出して作成する方法について説明してきました。</span><span class="sxs-lookup"><span data-stu-id="4f547-117">You’ve seen how Microsoft Defender ATP and Azure ATP detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="4f547-118">また、Microsoft 365 セキュリティセンターポータルでは、さまざまなソースからのアラートが他のコンテキスト情報と共に1つのインシデントに配信される方法についても説明してきました。</span><span class="sxs-lookup"><span data-stu-id="4f547-118">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="4f547-119">このような統合が発生すると、SOC アナリストが調査し、必要なアクションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4f547-119">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="4f547-120">また、ユーザーが添付ファイルを開いたときや保存したときに、そのクエリに基づいて検出を作成した受信メールを識別する高度な検索クエリも作成されています。</span><span class="sxs-lookup"><span data-stu-id="4f547-120">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="4f547-121">すべてのテストが終了した後、プロセスの最後に到達しました。</span><span class="sxs-lookup"><span data-stu-id="4f547-121">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="4f547-122">最終的な出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4f547-122">The final output should be:</span></span>

- <span data-ttu-id="4f547-123">完了したスコアカード</span><span class="sxs-lookup"><span data-stu-id="4f547-123">A completed scorecard</span></span>
- <span data-ttu-id="4f547-124">パイロットの結果についての詳細なレポート</span><span class="sxs-lookup"><span data-stu-id="4f547-124">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="4f547-125">前方へ移動する方法の決定</span><span class="sxs-lookup"><span data-stu-id="4f547-125">A decision on how to move forward</span></span>

<span data-ttu-id="4f547-126">最終的な出力からのレポートを、社内関係者 ( [準備](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) 段階で確認したもの) と Microsoft の連絡先に提示します。</span><span class="sxs-lookup"><span data-stu-id="4f547-126">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="4f547-127">このような作業により、製品やドキュメントを改善するためにフィードバックを確実に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4f547-127">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="4f547-128">このシミュレーションを楽しんでいただければ幸いです。</span><span class="sxs-lookup"><span data-stu-id="4f547-128">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="4f547-129">組織内の大規模なスケールで学んだ内容の実装を開始して、統合セキュリティソリューションを最大限に活用してください。</span><span class="sxs-lookup"><span data-stu-id="4f547-129">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="4f547-130">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4f547-130">Next step</span></span>
<span data-ttu-id="4f547-131">Microsoft Threat Protection の柱の詳細については、次の対話型のガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f547-131">Learn more about the Microsoft Threat Protection pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="4f547-132">Microsoft Defender for Office 365 を使用して組織を保護する</span><span class="sxs-lookup"><span data-stu-id="4f547-132">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="4f547-133">身元を確認するために Microsoft Defender を使用して疑わしいアクティビティおよび潜在的な攻撃を検出する</span><span class="sxs-lookup"><span data-stu-id="4f547-133">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="4f547-134">Microsoft Cloud App Security を使用して脅威を検出し、アラートを管理する</span><span class="sxs-lookup"><span data-stu-id="4f547-134">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="4f547-135">エンドポイントの Microsoft Defender を使用して脅威を調査および修復する</span><span class="sxs-lookup"><span data-stu-id="4f547-135">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
