---
title: Microsoft Defender ウイルス対策を展開して有効にする
description: ユーザー Microsoft Defender ウイルス対策、グループ ポリシー、PowerShell コマンドレット、または WMI をMicrosoft Intune、Microsoft Endpoint Configuration Managerエンドポイントを保護する方法を展開します。
keywords: 展開、有効化、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a847e65adb0402d4c5f98e19424677ccdc1011da
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925745"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="1913d-104">Microsoft Defender ウイルス対策を展開して有効にする</span><span class="sxs-lookup"><span data-stu-id="1913d-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1913d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1913d-105">**Applies to:**</span></span>

- [<span data-ttu-id="1913d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1913d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1913d-107">使用している管理ツールによっては、保護を具体的に有効または構成する必要Microsoft Defender ウイルス対策があります。</span><span class="sxs-lookup"><span data-stu-id="1913d-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="1913d-108">[Microsoft Intune、Microsoft Endpoint Configuration Manager、](deploy-manage-report-microsoft-defender-antivirus.md#ref2)グループ ポリシー、Active Directory、Microsoft Azure、PowerShell コマンドレット、Windows 管理命令 (WMI) による保護を有効にする方法については、「Microsoft Defender ウイルス対策 の展開、管理、およびレポート」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1913d-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="1913d-109">一部のシナリオでは、仮想デスクトップ インフラストラクチャ (VDI) 環境など、Microsoft Defender ウイルス対策保護を正常に展開または構成する方法に関するガイダンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1913d-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="1913d-110">このセクションの残りの記事では、VDI またはリモート デスクトップ サービス[(RDS)](deployment-vdi-microsoft-defender-antivirus.md)環境で仮想マシン (VM) で Microsoft Defender ウイルス対策 をセットアップするためのエンド to エンドのアドバイスとベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1913d-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="1913d-111">関連資料</span><span class="sxs-lookup"><span data-stu-id="1913d-111">Related articles</span></span>

- [<span data-ttu-id="1913d-112">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="1913d-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="1913d-113">更新プログラムの展開、管理、およびレポートの作成Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="1913d-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1913d-114">仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド</span><span class="sxs-lookup"><span data-stu-id="1913d-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)