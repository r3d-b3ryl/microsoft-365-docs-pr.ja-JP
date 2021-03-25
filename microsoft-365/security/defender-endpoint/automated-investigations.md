---
title: 自動調査を使用して脅威を調査および修復する
description: Microsoft Defender for Endpoint の自動調査フローについて説明します。
keywords: 自動化, 調査, 検出, Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 7143a360fb7093f94c6f66373587e1c895dd3213
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200307"
---
# <a name="overview-of-automated-investigations"></a><span data-ttu-id="6373b-104">自動調査の概要</span><span class="sxs-lookup"><span data-stu-id="6373b-104">Overview of automated investigations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6373b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6373b-105">**Applies to:**</span></span>
- [<span data-ttu-id="6373b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6373b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6373b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6373b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="6373b-108">どのように動作するのかを確認したいですか?</span><span class="sxs-lookup"><span data-stu-id="6373b-108">Want to see how it works?</span></span> <span data-ttu-id="6373b-109">次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6373b-109">Watch the following video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

<span data-ttu-id="6373b-110">自動調査のテクノロジは、さまざまな検査アルゴリズムを使用し、セキュリティ アナリストが使用するプロセスに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="6373b-110">The technology in automated investigation uses various inspection algorithms and is based on processes that are used by security analysts.</span></span> <span data-ttu-id="6373b-111">AIR 機能は、アラートを調べ、侵害を解決するために直ちにアクションを実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6373b-111">AIR capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="6373b-112">AIR 機能により、アラートの量が大幅に削減され、セキュリティ操作は、より高度な脅威や他の価値の高いイニシアチブに集中できます。</span><span class="sxs-lookup"><span data-stu-id="6373b-112">AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives.</span></span> <span data-ttu-id="6373b-113">保留中か完了かの修復アクションはすべて、アクション センターで [追跡されます](auto-investigation-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6373b-113">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="6373b-114">アクション センターでは、保留中のアクションが承認 (または拒否) され、必要に応じて完了したアクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="6373b-114">In the Action center, pending actions are approved (or rejected), and completed actions can be undone if needed.</span></span>

<span data-ttu-id="6373b-115">この記事では、AIR の概要を説明し、次の手順と追加のリソースへのリンクを含みます。</span><span class="sxs-lookup"><span data-stu-id="6373b-115">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="6373b-116">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6373b-116">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="6373b-117">[無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="6373b-117">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span></span>

## <a name="how-the-automated-investigation-starts"></a><span data-ttu-id="6373b-118">自動調査の開始方法</span><span class="sxs-lookup"><span data-stu-id="6373b-118">How the automated investigation starts</span></span>

<span data-ttu-id="6373b-119">自動調査は、アラートがトリガーされた場合、またはセキュリティオペレーターが調査を開始するときに開始できます。</span><span class="sxs-lookup"><span data-stu-id="6373b-119">An automated investigation can start when an alert is triggered or when a security operator initiates the investigation.</span></span>

|<span data-ttu-id="6373b-120">状況</span><span class="sxs-lookup"><span data-stu-id="6373b-120">Situation</span></span>  |<span data-ttu-id="6373b-121">結果</span><span class="sxs-lookup"><span data-stu-id="6373b-121">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="6373b-122">アラートがトリガーされる</span><span class="sxs-lookup"><span data-stu-id="6373b-122">An alert is triggered</span></span>     | <span data-ttu-id="6373b-123">一般に、アラートがトリガーされると自動調査[](review-alerts.md)が開始され、インシデント[が](view-incidents-queue.md)作成されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-123">In general, an automated investigation starts when an [alert](review-alerts.md) is triggered, and an [incident](view-incidents-queue.md) is created.</span></span> <span data-ttu-id="6373b-124">たとえば、悪意のあるファイルがデバイスに存在するとします。</span><span class="sxs-lookup"><span data-stu-id="6373b-124">For example, suppose a malicious file resides on a device.</span></span> <span data-ttu-id="6373b-125">そのファイルが検出されると、アラートがトリガーされ、インシデントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-125">When that file is detected, an alert is triggered, and incident is created.</span></span> <span data-ttu-id="6373b-126">自動調査プロセスは、デバイスで開始されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-126">An automated investigation process begins on the device.</span></span> <span data-ttu-id="6373b-127">他のデバイス上の同じファイルのために他のアラートが生成されると、関連付けられたインシデントと自動調査に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-127">As other alerts are generated because of the same file on other devices, they are added to the associated incident and to the automated investigation.</span></span>         |
|<span data-ttu-id="6373b-128">調査が手動で開始される</span><span class="sxs-lookup"><span data-stu-id="6373b-128">An investigation is started manually</span></span>     | <span data-ttu-id="6373b-129">自動調査は、セキュリティ運用チームが手動で開始できます。</span><span class="sxs-lookup"><span data-stu-id="6373b-129">An automated investigation can be started manually by your security operations team.</span></span> <span data-ttu-id="6373b-130">たとえば、セキュリティオペレーターがデバイスのリストを確認し、デバイスのリスクレベルが高いという通知を行ったとします。</span><span class="sxs-lookup"><span data-stu-id="6373b-130">For example, suppose a security operator is reviewing a list of devices and notices that a device has a high risk level.</span></span> <span data-ttu-id="6373b-131">セキュリティオペレーターは、一覧でデバイスを選択してフライアウトを開き、[自動調査の開始] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6373b-131">The security operator can select the device in the list to open its flyout, and then select **Initiate Automated Investigation**.</span></span> |

## <a name="how-an-automated-investigation-expands-its-scope"></a><span data-ttu-id="6373b-132">自動調査によって範囲が拡大される方法</span><span class="sxs-lookup"><span data-stu-id="6373b-132">How an automated investigation expands its scope</span></span>

<span data-ttu-id="6373b-133">調査の実行中、デバイスから生成された他のアラートは、その調査が完了するまで、継続的な自動調査に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-133">While an investigation is running, any other alerts generated from the device are added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="6373b-134">さらに、他のデバイスで同じ脅威が見られる場合は、それらのデバイスが調査に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-134">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>

<span data-ttu-id="6373b-135">特定のエンティティが別のデバイスで見られる場合、自動調査プロセスはスコープを拡大してそのデバイスを含め、そのデバイスで一般的なセキュリティ プレイブックを開始します。</span><span class="sxs-lookup"><span data-stu-id="6373b-135">If an incriminated entity is seen in another device, the automated investigation process expands its scope to include that device, and a general security playbook starts on that device.</span></span> <span data-ttu-id="6373b-136">同じエンティティからこの拡張プロセス中に 10 台以上のデバイスが見つかった場合、その展開アクションには承認が必要であり、[保留中のアクション] タブ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-136">If 10 or more devices are found during this expansion process from the same entity, then that expansion action requires an approval, and is visible on the **Pending actions** tab.</span></span>

## <a name="how-threats-are-remediated"></a><span data-ttu-id="6373b-137">脅威の修復方法</span><span class="sxs-lookup"><span data-stu-id="6373b-137">How threats are remediated</span></span>

<span data-ttu-id="6373b-138">アラートがトリガーされ、自動調査が実行されると、調査された証拠ごとに評決が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-138">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="6373b-139">評決は次の場合があります。</span><span class="sxs-lookup"><span data-stu-id="6373b-139">Verdicts can be</span></span> 
- <span data-ttu-id="6373b-140">*悪意のある*;</span><span class="sxs-lookup"><span data-stu-id="6373b-140">*Malicious*;</span></span>
- <span data-ttu-id="6373b-141">*疑わしい*。または</span><span class="sxs-lookup"><span data-stu-id="6373b-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="6373b-142">*脅威が見つかりません*。</span><span class="sxs-lookup"><span data-stu-id="6373b-142">*No threats found*.</span></span> 

<span data-ttu-id="6373b-143">評決に達すると、自動調査によって 1 つ以上の修復アクションが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6373b-143">As verdicts are reached, automated investigations can result in one or more remediation actions.</span></span> <span data-ttu-id="6373b-144">修復アクションの例としては、検疫にファイルを送信する、サービスを停止する、スケジュールされたタスクを削除する、などです。</span><span class="sxs-lookup"><span data-stu-id="6373b-144">Examples of remediation actions include sending a file to quarantine, stopping a service, removing a scheduled task, and more.</span></span> <span data-ttu-id="6373b-145">詳細については、「修復アクション [」を参照してください](manage-auto-investigation.md#remediation-actions)。</span><span class="sxs-lookup"><span data-stu-id="6373b-145">To learn more, see [Remediation actions](manage-auto-investigation.md#remediation-actions).</span></span>  

<span data-ttu-id="6373b-146">組織のオートメーション [セット](automation-levels.md) のレベルや他のセキュリティ設定に応じて、修復アクションは自動的に行われるか、セキュリティ運用チームの承認を得た場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="6373b-146">Depending on the [level of automation](automation-levels.md) set for your organization, as well as other security settings, remediation actions can occur automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="6373b-147">自動修復に影響を与える可能性のある追加のセキュリティ設定には、望ましくない可能性のあるアプリケーション (PUA) [からの](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) 保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6373b-147">Additional security settings that can affect automatic remediation include [protection from potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span></span> 

<span data-ttu-id="6373b-148">保留中か完了かの修復アクションはすべて、アクション センターで [追跡されます](auto-investigation-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6373b-148">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="6373b-149">必要に応じて、セキュリティ運用チームは修復アクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="6373b-149">If necessary, your security operations team can undo a remediation action.</span></span> <span data-ttu-id="6373b-150">詳細については、「自動調査後 [の修復アクションの確認と承認」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)。</span><span class="sxs-lookup"><span data-stu-id="6373b-150">To learn more, see [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).</span></span>

> [!TIP]
> <span data-ttu-id="6373b-151">Microsoft 365 セキュリティ センターの新しい統合調査ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6373b-151">Check out the new, unified investigation page in the Microsoft 365 security center.</span></span> <span data-ttu-id="6373b-152">詳細については [、「(NEW!)」を参照してください。統合された調査ページ](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page)。</span><span class="sxs-lookup"><span data-stu-id="6373b-152">To learn more, see [(NEW!) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span></span>


## <a name="requirements-for-air"></a><span data-ttu-id="6373b-153">AIR の要件</span><span class="sxs-lookup"><span data-stu-id="6373b-153">Requirements for AIR</span></span>

<span data-ttu-id="6373b-154">組織には Defender for Endpoint が必要です (「エンドポイント用 Microsoft Defender の最小[要件」を参照)。](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="6373b-154">Your organization must have Defender for Endpoint (see [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)).</span></span>

<span data-ttu-id="6373b-155">現在、AIR は次の OS バージョンのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6373b-155">Currently, AIR only supports the following OS versions:</span></span>
- <span data-ttu-id="6373b-156">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="6373b-156">Windows Server 2019</span></span>
- <span data-ttu-id="6373b-157">Windows 10 バージョン 1709 (OS ビルド 16299.1085 [および KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) 以降</span><span class="sxs-lookup"><span data-stu-id="6373b-157">Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) or later</span></span>
- <span data-ttu-id="6373b-158">Windows 10 バージョン 1803 (OS ビルド 17134.704 [および KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) 以降</span><span class="sxs-lookup"><span data-stu-id="6373b-158">Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) or later</span></span>
- <span data-ttu-id="6373b-159">Windows 10 バージョン [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) 以降</span><span class="sxs-lookup"><span data-stu-id="6373b-159">Windows 10, version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) or later</span></span>

## <a name="next-steps"></a><span data-ttu-id="6373b-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="6373b-160">Next steps</span></span>

- [<span data-ttu-id="6373b-161">オートメーション レベルの詳細</span><span class="sxs-lookup"><span data-stu-id="6373b-161">Learn more about automation levels</span></span>](automation-levels.md)
- [<span data-ttu-id="6373b-162">対話型ガイドを参照してください。 Microsoft Defender for Endpoint を使用して脅威を調査して修復する</span><span class="sxs-lookup"><span data-stu-id="6373b-162">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
- [<span data-ttu-id="6373b-163">Microsoft Defender for Endpoint で自動調査および修復機能を構成する</span><span class="sxs-lookup"><span data-stu-id="6373b-163">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>](configure-automated-investigations-remediation.md)

## <a name="see-also"></a><span data-ttu-id="6373b-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="6373b-164">See also</span></span>

- [<span data-ttu-id="6373b-165">PUA 保護</span><span class="sxs-lookup"><span data-stu-id="6373b-165">PUA protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="6373b-166">Microsoft Defender for Office 365 での自動調査と対応</span><span class="sxs-lookup"><span data-stu-id="6373b-166">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="6373b-167">Microsoft 365 Defender での自動調査と対応</span><span class="sxs-lookup"><span data-stu-id="6373b-167">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
