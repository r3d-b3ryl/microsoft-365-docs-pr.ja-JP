---
title: パイロット Microsoft の脅威保護プロジェクトを計画する
description: パイロットに対して、目標を管理し、成果を確実にするための関係者による Microsoft の脅威保護プロジェクトを計画します。
keywords: Microsoft の脅威保護のパイロット、パイロットのための microsoft の脅威保護プロジェクトの計画、microsoft threat protection の運用プロジェクト、サイバーセキュリティ、高度な脅威、企業セキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 7d1870d1b8972009bed657f476810ca011dc2621
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367979"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="ab9af-104">パイロット Microsoft の脅威保護プロジェクトを計画する</span><span class="sxs-lookup"><span data-stu-id="ab9af-104">Planning your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ab9af-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ab9af-105">**Applies to:**</span></span>
- <span data-ttu-id="ab9af-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ab9af-106">Microsoft Threat Protection</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="パイロットを計画する Microsoft の脅威保護プロジェクト" />
      <br/><span data-ttu-id="ab9af-108">プラン</a></span><span class="sxs-lookup"><span data-stu-id="ab9af-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境の準備" />
      <br/><span data-ttu-id="ab9af-110">準備</a></span><span class="sxs-lookup"><span data-stu-id="ab9af-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Microsoft の脅威保護攻撃のシミュレーションを実行する" />
     <br/><span data-ttu-id="ab9af-112">攻撃のシミュレーション</a></span><span class="sxs-lookup"><span data-stu-id="ab9af-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Microsoft の脅威保護パイロットの終了と概要" />
     <br/><span data-ttu-id="ab9af-114">閉じて要約する</a></span><span class="sxs-lookup"><span data-stu-id="ab9af-114">Close and summarize</a></span></span><br>
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

<span data-ttu-id="ab9af-115">現在、計画段階になっています。</span><span class="sxs-lookup"><span data-stu-id="ab9af-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="ab9af-116">パイロットプロジェクトが成功したかどうかを確認するには、最初に利害関係者に対して綿密な計画を行い、承認を得ることが重要です。</span><span class="sxs-lookup"><span data-stu-id="ab9af-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="ab9af-117">計画の要素には、範囲の識別、ユースケース、要件、および成功の条件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab9af-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="ab9af-118">このガイドでは、パイロットプロジェクトを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab9af-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="ab9af-119">最適な結果を得るには、パイロットの手順をできるだけ忠実に実行します。</span><span class="sxs-lookup"><span data-stu-id="ab9af-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="ab9af-120">範囲</span><span class="sxs-lookup"><span data-stu-id="ab9af-120">Scope</span></span>

<span data-ttu-id="ab9af-121">パイロットのスコープによって、環境および使用可能なテスト方法に基づいて、テストの頻度を決定します。</span><span class="sxs-lookup"><span data-stu-id="ab9af-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="ab9af-122">考慮すべきスコープの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ab9af-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="ab9af-123">エンドポイント、サーバー、ドメインコントローラーを含む開発環境またはテスト環境。</span><span class="sxs-lookup"><span data-stu-id="ab9af-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="ab9af-124">Microsoft 365、Azure、Active Directory サービス、エンドポイント、およびサーバーを使用した運用環境</span><span class="sxs-lookup"><span data-stu-id="ab9af-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="ab9af-125">まだ完全なライセンスを持っていない場合は、試用版ライセンスを取得して、 [Microsoft の脅威保護を評価](https://aka.ms/mtp-trial-lab) します。試験プロジェクトを計画、準備、セットアップ、構成、実行します。</span><span class="sxs-lookup"><span data-stu-id="ab9af-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="ab9af-126">関係者は、開始から終了までのプロセスを容易にするために、大きな役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="ab9af-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="ab9af-127">評価するオペレーティングシステムの種類も、組織の編成に基づいて定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="ab9af-128">これには次のようなものがあります: [Mac エンドポイント](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)、 [Linux サーバー](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)、 [windows 10 エンドポイント](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)、 [windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)。</span><span class="sxs-lookup"><span data-stu-id="ab9af-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="ab9af-129">使用例</span><span class="sxs-lookup"><span data-stu-id="ab9af-129">Use cases</span></span>

<span data-ttu-id="ab9af-130">ユースケースは、テスト対象のツールが意図したユーザーによって消費されることを意図したステートメントを表します。</span><span class="sxs-lookup"><span data-stu-id="ab9af-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="ab9af-131">これらは、SOC アナリストなどの特定のペルソナの観点から、ユーザーストーリーとして表現できます。</span><span class="sxs-lookup"><span data-stu-id="ab9af-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="ab9af-132">例:</span><span class="sxs-lookup"><span data-stu-id="ab9af-132">For example:</span></span>
- <span data-ttu-id="ab9af-133">SOC アナリストとして、ネットワーク内のデバイス、ユーザー、およびメールボックス全体でアラートとイベントを表示、関連付け、評価、および管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="ab9af-134">[インシデント管理]</span><span class="sxs-lookup"><span data-stu-id="ab9af-134">[Incident management]</span></span>
- <span data-ttu-id="ab9af-135">SOC アナリストとして、ネットワーク内の悪意のあるイベントを自動的に調査して応答するためのツールとプロセスを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="ab9af-136">[自動赤外線]</span><span class="sxs-lookup"><span data-stu-id="ab9af-136">[Auto IR]</span></span>
- <span data-ttu-id="ab9af-137">SOC アナリストとして、環境からデータを検索し、既知の脅威と潜在的な脅威、および疑わしいアクティビティを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="ab9af-138">[高度な検索]</span><span class="sxs-lookup"><span data-stu-id="ab9af-138">[Advanced Hunting]</span></span>

<span data-ttu-id="ab9af-139">これらのユースケースは、定義されたスコープのパラメーター内で作成する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ab9af-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="ab9af-140">たとえば、テストの範囲に Microsoft Cloud App Security などのツールの評価が含まれていない場合は、データソースを作成しないで、これに依存するユースケースを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab9af-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab9af-141">要件</span><span class="sxs-lookup"><span data-stu-id="ab9af-141">Requirements</span></span>

<span data-ttu-id="ab9af-142">ユースケースのリストから、要件の作成を開始できます。</span><span class="sxs-lookup"><span data-stu-id="ab9af-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="ab9af-143">要件には、ツールがユースケースを満たすために必要な機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab9af-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="ab9af-144">これらの要件は、構成と保守、統合のサポート、探している機能やカスタム通知の作成機能などの機能固有の要件に分類できます。</span><span class="sxs-lookup"><span data-stu-id="ab9af-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="ab9af-145">テスト計画</span><span class="sxs-lookup"><span data-stu-id="ab9af-145">Test plan</span></span>

<span data-ttu-id="ab9af-146">要件に応じて、さまざまなテスト方法が適している場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="ab9af-147">たとえば、自動修復の有効性を評価する必要がある場合は、テスト計画に、Microsoft の脅威保護で自動修復アクションをトリガーする動作を生成するための手順を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft Threat Protection.</span></span> <span data-ttu-id="ab9af-148">特定の動作または攻撃を検出する必要がある場合は、テストにさらに手順が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="ab9af-149">その点は、要件を正確にテストするための計画を立てることです。</span><span class="sxs-lookup"><span data-stu-id="ab9af-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="ab9af-150">成功の基準</span><span class="sxs-lookup"><span data-stu-id="ab9af-150">Success criteria</span></span>

<span data-ttu-id="ab9af-151">成功の基準は、最終的にテストの対象に対して測定するように設定されたバーです。</span><span class="sxs-lookup"><span data-stu-id="ab9af-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="ab9af-152">Microsoft の脅威保護 (または、その他の問題に関するその他の技術) を他のツールに対してテストしているかどうか、またはその他のツールに対してテストする場合は、ツールによって提供される値を決定するために定量化可能な条件が</span><span class="sxs-lookup"><span data-stu-id="ab9af-152">Whether you are testing Microsoft Threat Protection (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="ab9af-153">範囲、要件、およびテスト計画に基づいて、成功の基準によってテストのスコアを決定します。</span><span class="sxs-lookup"><span data-stu-id="ab9af-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="ab9af-154">これは、必要に応じて、合格または失敗し、重み付けの採点が多くなります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="ab9af-155">たとえば、特定の重要な領域では、ツールが80% 以上のスコアを必要とすることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab9af-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="ab9af-156">;</span><span class="sxs-lookup"><span data-stu-id="ab9af-156">Scorecard</span></span>

<span data-ttu-id="ab9af-157">プランのすべての要素をまとめる1つの方法は、スコアカードを作成することです。</span><span class="sxs-lookup"><span data-stu-id="ab9af-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="ab9af-158">以下のサンプルスコアカードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9af-158">See a sample scorecard below:</span></span>

|<span data-ttu-id="ab9af-159">**ユースケース**</span><span class="sxs-lookup"><span data-stu-id="ab9af-159">**Use case**</span></span>|<span data-ttu-id="ab9af-160">**要件**</span><span class="sxs-lookup"><span data-stu-id="ab9af-160">**Requirements**</span></span>|<span data-ttu-id="ab9af-161">**構成要件**</span><span class="sxs-lookup"><span data-stu-id="ab9af-161">**Configuration requirements**</span></span>|<span data-ttu-id="ab9af-162">**テスト計画**</span><span class="sxs-lookup"><span data-stu-id="ab9af-162">**Test plan**</span></span>|<span data-ttu-id="ab9af-163">**予想結果**</span><span class="sxs-lookup"><span data-stu-id="ab9af-163">**Expected outcome**</span></span>|<span data-ttu-id="ab9af-164">**テストの状態**</span><span class="sxs-lookup"><span data-stu-id="ab9af-164">**Test status**</span></span>|<span data-ttu-id="ab9af-165">**スコア**</span><span class="sxs-lookup"><span data-stu-id="ab9af-165">**Score**</span></span>|<span data-ttu-id="ab9af-166">**注**</span><span class="sxs-lookup"><span data-stu-id="ab9af-166">**Notes**</span></span>|
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="ab9af-167">インシデント管理</span><span class="sxs-lookup"><span data-stu-id="ab9af-167">Incident management</span></span>|<span data-ttu-id="ab9af-168">-Microsoft の脅威保護</span><span class="sxs-lookup"><span data-stu-id="ab9af-168">-  Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="ab9af-169">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ab9af-169">- Azure ATP</span></span> </br></br><span data-ttu-id="ab9af-170">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ab9af-170">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="ab9af-171">-Microsoft Cloud App Security (オプション)</span><span class="sxs-lookup"><span data-stu-id="ab9af-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="ab9af-172">詳細については、準備、セットアップ、および構成の [前提条件](https://aka.ms/mtp-trial-lab) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9af-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="ab9af-173">攻撃のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="ab9af-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="ab9af-174">インシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="ab9af-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="ab9af-175">調査担当は、インシデントの範囲と影響について理解し、インシデントを管理する</span><span class="sxs-lookup"><span data-stu-id="ab9af-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="ab9af-176">自動赤外線</span><span class="sxs-lookup"><span data-stu-id="ab9af-176">AutoIR</span></span>|<span data-ttu-id="ab9af-177">-Microsoft の脅威保護</span><span class="sxs-lookup"><span data-stu-id="ab9af-177">-   Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="ab9af-178">-Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ab9af-178">- Azure ATP</span></span> </br></br><span data-ttu-id="ab9af-179">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ab9af-179">- Microsoft Defender ATP</span></span> |<span data-ttu-id="ab9af-180">詳細については、準備、セットアップ、および構成の [前提条件](https://aka.ms/mtp-trial-lab) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9af-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="ab9af-181">自動赤外線を有効にする</span><span class="sxs-lookup"><span data-stu-id="ab9af-181">Enable AutoIR</span></span>  |[<span data-ttu-id="ab9af-182">攻撃のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="ab9af-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="ab9af-183">自動調査</span><span class="sxs-lookup"><span data-stu-id="ab9af-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="ab9af-184">通知とインシデントは、Microsoft の脅威保護によって自動的に修復されます。</span><span class="sxs-lookup"><span data-stu-id="ab9af-184">Alerts and incidents are automatically remediated by Microsoft Threat Protection</span></span>||||
|<span data-ttu-id="ab9af-185">高度な検出</span><span class="sxs-lookup"><span data-stu-id="ab9af-185">Advanced hunting</span></span>|<span data-ttu-id="ab9af-186">-Microsoft の脅威保護</span><span class="sxs-lookup"><span data-stu-id="ab9af-186">- Microsoft Threat Protection</span></span> </br></br><span data-ttu-id="ab9af-187">-Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ab9af-187">- Microsoft Defender ATP</span></span> </br></br><span data-ttu-id="ab9af-188">-Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ab9af-188">- Office 365 ATP</span></span>   |<span data-ttu-id="ab9af-189">詳細については、準備、セットアップ、および構成の [前提条件](https://aka.ms/mtp-trial-lab) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9af-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="ab9af-190">高度な検索のシナリオ</span><span class="sxs-lookup"><span data-stu-id="ab9af-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="ab9af-191">調査担当者は、高度な検索、影響を受けるエンティティへのピボット、およびカスタム検出の作成によってデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ab9af-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="ab9af-192">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ab9af-192">Next step</span></span>
|<span data-ttu-id="ab9af-193">![準備フェーズ](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="ab9af-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="ab9af-194">準備フェーズ</span><span class="sxs-lookup"><span data-stu-id="ab9af-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="ab9af-195">Microsoft の脅威保護パイロット環境の準備</span><span class="sxs-lookup"><span data-stu-id="ab9af-195">Prepare your Microsoft Threat Protection pilot environment</span></span>
|:-------|:-----|
