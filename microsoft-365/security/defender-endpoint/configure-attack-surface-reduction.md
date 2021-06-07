---
title: 攻撃表面の縮小機能を構成する
description: 攻撃Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell コマンドレット、およびグループ ポリシーを使用して、攻撃表面の縮小を構成します。
keywords: asr, 攻撃表面の縮小, Windows Defender, microsoft Defender, ウイルス対策, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770963"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="379d5-104">攻撃表面の縮小機能を構成する</span><span class="sxs-lookup"><span data-stu-id="379d5-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="379d5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="379d5-105">**Applies to:**</span></span>
- [<span data-ttu-id="379d5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="379d5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="379d5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="379d5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="379d5-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="379d5-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="379d5-109">[無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="379d5-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="379d5-110">Defender for Endpoint には、攻撃表面の縮小機能がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="379d5-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="379d5-111">詳細については、「攻撃表面 [の縮小機能の概要」を参照してください](overview-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="379d5-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="379d5-112">環境で攻撃表面の縮小を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="379d5-112">To configure attack surface reduction in your environment, follow these steps:</span></span> 

1. <span data-ttu-id="379d5-113">[ハードウェア ベースの分離を有効にMicrosoft Edge。](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="379d5-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="379d5-114">アプリケーション制御を有効にする。</span><span class="sxs-lookup"><span data-stu-id="379d5-114">Enable application control.</span></span> 

   1. <span data-ttu-id="379d5-115">[基本ポリシー] を [Windows] で確認します。</span><span class="sxs-lookup"><span data-stu-id="379d5-115">Review base policies in Windows.</span></span> <span data-ttu-id="379d5-116">基本 [ポリシーの例を参照してください](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。</span><span class="sxs-lookup"><span data-stu-id="379d5-116">See [example base policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="379d5-117">アプリケーション コントロール [の設計ガイドを参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。</span><span class="sxs-lookup"><span data-stu-id="379d5-117">See the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="379d5-118">アプリケーション コントロールの [設計ガイドを参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。</span><span class="sxs-lookup"><span data-stu-id="379d5-118">Refer to the [application control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="379d5-119">[フォルダー アクセスの制御を有効にする](enable-controlled-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="379d5-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="379d5-120">[[ネットワーク保護] をオンにする](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="379d5-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="379d5-121">[エクスプロイト保護を有効にする](enable-exploit-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="379d5-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="379d5-122">[攻撃表面の縮小ルールを構成します](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="379d5-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="379d5-123">ネットワーク ファイアウォールを設定します。</span><span class="sxs-lookup"><span data-stu-id="379d5-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="379d5-124">高度なセキュリティを備Windows Defender ファイアウォール[の概要を確認します](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。</span><span class="sxs-lookup"><span data-stu-id="379d5-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="379d5-125">ファイアウォール ポリシー [Windows Defender ファイアウォールする方法](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)を決定するには、次の設計ガイドを使用します。</span><span class="sxs-lookup"><span data-stu-id="379d5-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="379d5-126">高度な[セキュリティWindows Defender ファイアウォール組織](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)のファイアウォールをセットアップするには、次の展開ガイドを使用します。</span><span class="sxs-lookup"><span data-stu-id="379d5-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span> 

> [!TIP]
> <span data-ttu-id="379d5-127">ほとんどの場合、攻撃表面の縮小機能を構成する場合、次の方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="379d5-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>
> - <span data-ttu-id="379d5-128">Microsoft エンドポイント マネージャー (現在は、Microsoft IntuneとMicrosoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="379d5-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="379d5-129">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="379d5-129">Group Policy</span></span>
> - <span data-ttu-id="379d5-130">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="379d5-130">PowerShell cmdlets</span></span>
