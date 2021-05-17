---
title: WMI をMicrosoft Defender ウイルス対策構成する
description: Wmi スクリプトを使用して Microsoft Defender for Endpoint Microsoft Defender ウイルス対策設定を取得、変更、および更新することで、アプリケーションの構成と管理を行う方法について説明します。
keywords: wmi、スクリプト、Windows 管理インストルメンテーション、構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764065"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="27e68-104">[Windows管理インストルメンテーション (WMI) を使用して、デバイスを構成および管理Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="27e68-104">Use Windows Management Instrumentation (WMI) to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="27e68-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="27e68-105">**Applies to:**</span></span>

- [<span data-ttu-id="27e68-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="27e68-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="27e68-107">Windows管理インストルメンテーション (WMI) は、設定を取得、変更、更新できるスクリプト インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="27e68-107">Windows Management Instrumentation (WMI) is a scripting interface that allows you to retrieve, modify, and update settings.</span></span>

<span data-ttu-id="27e68-108">WMI の詳細については、「システム管理ライブラリ [Microsoft Developer Network」を参照してください](/windows/win32/wmisdk/wmi-start-page)。</span><span class="sxs-lookup"><span data-stu-id="27e68-108">Read more about WMI at the [Microsoft Developer Network System Administration library](/windows/win32/wmisdk/wmi-start-page).</span></span>

<span data-ttu-id="27e68-109">Microsoft Defender ウイルス対策には、グループ ポリシーや他の管理ツールと同じ機能のほとんどを実行するために使用できる、複数の特定の WMI クラスがあります。</span><span class="sxs-lookup"><span data-stu-id="27e68-109">Microsoft Defender Antivirus has a number of specific WMI classes that can be used to perform most of the same functions as Group Policy and other management tools.</span></span> <span data-ttu-id="27e68-110">クラスの多くは [、Defender PowerShell コマンドレットに類似しています](use-powershell-cmdlets-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="27e68-110">Many of the classes are analogous to [Defender PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="27e68-111">[MSDN Windows Defender WMIv2 Provider](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照ライブラリには、ユーザーに使用できる WMI クラスMicrosoft Defender ウイルス対策、サンプル スクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="27e68-111">The [MSDN Windows Defender WMIv2 Provider reference library](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lists the available WMI classes for Microsoft Defender Antivirus, and includes example scripts.</span></span>

<span data-ttu-id="27e68-112">WMI で行われた変更は、変更が展開または行われたエンドポイントのローカル設定に影響します。</span><span class="sxs-lookup"><span data-stu-id="27e68-112">Changes made with WMI will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="27e68-113">つまり、グループ ポリシー、グループ ポリシー、Microsoft Endpoint Configuration Manager、またはMicrosoft Intuneポリシーの展開は、WMI で行われた変更を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="27e68-113">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with WMI.</span></span> 

<span data-ttu-id="27e68-114">ローカル ポリシー [の上書きを使用してローカルで上書きできる設定を構成できます](configure-local-policy-overrides-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="27e68-114">You can [configure which settings can be overridden locally  with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="27e68-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="27e68-115">Related topics</span></span>

- [<span data-ttu-id="27e68-116">管理および構成ツールのリファレンス トピック</span><span class="sxs-lookup"><span data-stu-id="27e68-116">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="27e68-117">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="27e68-117">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)