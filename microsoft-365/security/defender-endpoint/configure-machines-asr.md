---
title: ASR ルールの展開と検出を最適化する
description: 攻撃表面の縮小 (ASR) ルールを最適化して、一般的なマルウェアの悪用を特定して防止します。
keywords: オンボード、Intune 管理、Microsoft Defender for Endpoint、Microsoft Defender、Windows Defender、攻撃表面の縮小、ASR、セキュリティ ベースライン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932849"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="54081-104">ASR ルールの展開と検出を最適化する</span><span class="sxs-lookup"><span data-stu-id="54081-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54081-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="54081-105">**Applies to:**</span></span>
- [<span data-ttu-id="54081-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54081-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="54081-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54081-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="54081-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="54081-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="54081-109">[無料試用版にサインアップします](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="54081-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="54081-110">[攻撃表面の縮小 (ASR) ルールは、一](./attack-surface-reduction.md) 般的なマルウェアの悪用を特定して防止します。</span><span class="sxs-lookup"><span data-stu-id="54081-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="54081-111">悪意のあるコードを実行できる可能性のある時間と方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="54081-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="54081-112">たとえば、JavaScript または VBScript がダウンロードした実行可能ファイルを起動したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行されるプロセスをブロックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="54081-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="54081-113">![攻撃表面管理カード](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="54081-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="54081-114">*攻撃表面管理カード*</span><span class="sxs-lookup"><span data-stu-id="54081-114">*Attack surface management card*</span></span>

<span data-ttu-id="54081-115">攻撃 *表面管理カードは* 、Microsoft 365 セキュリティ センターのツールのエントリ ポイントで、次の使用が可能です。</span><span class="sxs-lookup"><span data-stu-id="54081-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="54081-116">ASR ルールが現在組織に展開されている方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="54081-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="54081-117">ASR 検出を確認し、誤った検出の可能性を特定します。</span><span class="sxs-lookup"><span data-stu-id="54081-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="54081-118">除外の影響を分析し、除外するファイル パスの一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="54081-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="54081-119">[Go **to attack surface management**  >  **Monitoring] &レポート>[除外の>追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="54081-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="54081-120">そこから、Microsoft 365 セキュリティ センターの他のセクションに移動できます。</span><span class="sxs-lookup"><span data-stu-id="54081-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="54081-121">![Microsoft 365 セキュリティ センターの [攻撃表面の縮小ルール] ページの [除外] タブを追加する](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="54081-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="54081-122">Microsoft 365 セキュリティ センターの [攻撃表面縮小ルール] ページの [*除外の追加] タブ*</span><span class="sxs-lookup"><span data-stu-id="54081-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="54081-123">Microsoft 365 セキュリティ センターにアクセスするには、Microsoft 365 E3 または E5 ライセンスと、Azure Active Directory で特定の役割を持つアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="54081-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="54081-124">[必要なライセンスとアクセス許可についてお読みください](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。</span><span class="sxs-lookup"><span data-stu-id="54081-124">[Read about required licenses and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="54081-125">Microsoft 365 セキュリティ センターでの ASR ルールの展開の詳細については [、「ASR](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)ルールの展開と検出の監視と管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54081-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="54081-126">**関連トピック**</span><span class="sxs-lookup"><span data-stu-id="54081-126">**Related topics**</span></span>

* [<span data-ttu-id="54081-127">デバイスが正しく構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="54081-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="54081-128">Microsoft Defender for Endpoint にオンボードされているデバイスを取得する</span><span class="sxs-lookup"><span data-stu-id="54081-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="54081-129">Microsoft Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを監視する</span><span class="sxs-lookup"><span data-stu-id="54081-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
