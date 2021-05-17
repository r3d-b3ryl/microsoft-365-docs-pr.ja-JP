---
title: PowerShell コマンドレットを使用して Microsoft Defender AV を構成および実行する
description: このWindows 10 PowerShell コマンドレットを使用して、スキャンの実行、セキュリティ インテリジェンスの更新、および設定の変更を行Microsoft Defender ウイルス対策。
keywords: scan, コマンドライン, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765301"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="159a9-104">PowerShell コマンドレットを使用して、サーバーの構成とMicrosoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="159a9-104">Use PowerShell cmdlets to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="159a9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="159a9-105">**Applies to:**</span></span>

- [<span data-ttu-id="159a9-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="159a9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="159a9-107">PowerShell を使用して、さまざまな機能を実行Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="159a9-107">You can use PowerShell to perform various functions in Windows Defender.</span></span> <span data-ttu-id="159a9-108">コマンド プロンプトやコマンド ラインと同様に、PowerShell はタスク ベースのコマンド ライン シェルであり、特にシステム管理用に設計されたスクリプト言語です。</span><span class="sxs-lookup"><span data-stu-id="159a9-108">Similar to the command prompt or command line, PowerShell is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="159a9-109">詳細については [、MSDN の PowerShell ハブで確認できます](/previous-versions/msdn10/mt173057(v=msdn.10))。</span><span class="sxs-lookup"><span data-stu-id="159a9-109">You can read more about it at the [PowerShell hub on MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).</span></span>

<span data-ttu-id="159a9-110">コマンドレットとその機能と使用可能なパラメーターの一覧については、「Defender コマンドレット」 [を参照](/powershell/module/defender) してください。</span><span class="sxs-lookup"><span data-stu-id="159a9-110">For a list of the cmdlets and their functions and available parameters, see the [Defender cmdlets](/powershell/module/defender) topic.</span></span>

<span data-ttu-id="159a9-111">PowerShell コマンドレットは、ソフトウェアWindowsグラフィカル ユーザー インターフェイス (GUI) に依存しないサーバー環境で最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="159a9-111">PowerShell cmdlets are most useful in Windows Server environments that don't rely on a graphical user interface (GUI) to configure software.</span></span>

> [!NOTE]
> <span data-ttu-id="159a9-112">PowerShell コマンドレットは[、Microsoft Endpoint Configuration Manager、](/configmgr)グループ ポリシー管理コンソール、または Microsoft Defender ウイルス対策 グループ ポリシー ADMX テンプレート[](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))などの完全なネットワーク ポリシー管理インフラストラクチャの代[わりとして使用する必要があります](https://www.microsoft.com/download/101445)。</span><span class="sxs-lookup"><span data-stu-id="159a9-112">PowerShell cmdlets should not be used as a replacement for a full network policy management infrastructure, such as [Microsoft Endpoint Configuration Manager](/configmgr), [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), or [Microsoft Defender Antivirus Group Policy ADMX templates](https://www.microsoft.com/download/101445).</span></span>

<span data-ttu-id="159a9-113">PowerShell で行われた変更は、変更が展開または行われたエンドポイントのローカル設定に影響します。</span><span class="sxs-lookup"><span data-stu-id="159a9-113">Changes made with PowerShell will affect local settings on the endpoint where the changes are deployed or made.</span></span> <span data-ttu-id="159a9-114">つまり、グループ ポリシー、グループ ポリシー、Microsoft Endpoint Configuration Manager、Microsoft Intuneを使用してポリシーを展開すると、PowerShell で行われた変更が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="159a9-114">This means that deployments of policy with Group Policy, Microsoft Endpoint Configuration Manager, or Microsoft Intune can overwrite changes made with PowerShell.</span></span>

<span data-ttu-id="159a9-115">ローカル ポリシー [の上書きを使用してローカルで上書きできる設定を構成できます](configure-local-policy-overrides-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="159a9-115">You can [configure which settings can be overridden locally with local policy overrides](configure-local-policy-overrides-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="159a9-116">PowerShell は通常、フォルダーの下にインストールされます `%SystemRoot%\system32\WindowsPowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="159a9-116">PowerShell is typically installed under the folder `%SystemRoot%\system32\WindowsPowerShell`.</span></span>

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a><span data-ttu-id="159a9-117">PowerShell Microsoft Defender ウイルス対策を使用する</span><span class="sxs-lookup"><span data-stu-id="159a9-117">Use Microsoft Defender Antivirus PowerShell cmdlets</span></span>

1. <span data-ttu-id="159a9-118">[検索] Windowsに **、「powershell」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="159a9-118">In the Windows search bar, type **powershell**.</span></span>
2. <span data-ttu-id="159a9-119">結果 **Windows PowerShell** を選択してインターフェイスを開きます。</span><span class="sxs-lookup"><span data-stu-id="159a9-119">Select **Windows PowerShell** from the results to open the interface.</span></span>
3. <span data-ttu-id="159a9-120">PowerShell コマンドとパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="159a9-120">Enter the PowerShell command and any parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="159a9-121">管理者モードで PowerShell を開く必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="159a9-121">You may need to open PowerShell in administrator mode.</span></span> <span data-ttu-id="159a9-122">[スタート] メニューのアイテムを右クリックし、[管理者として実行] をクリック **し、アクセス** 許可のプロンプト **で [は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="159a9-122">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span>

<span data-ttu-id="159a9-123">コマンドレットのオンライン ヘルプを開く場合は、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="159a9-123">To open online help for any of the cmdlets type the following:</span></span>

```PowerShell
Get-Help <cmdlet> -Online
```

<span data-ttu-id="159a9-124">ローカルに `-online` キャッシュされたヘルプを取得するには、パラメーターを省略します。</span><span class="sxs-lookup"><span data-stu-id="159a9-124">Omit the `-online` parameter to get locally cached help.</span></span>

## <a name="related-topics"></a><span data-ttu-id="159a9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="159a9-125">Related topics</span></span>

- [<span data-ttu-id="159a9-126">管理および構成ツールのリファレンス トピック</span><span class="sxs-lookup"><span data-stu-id="159a9-126">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="159a9-127">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="159a9-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="159a9-128">Microsoft Defender ウイルス対策コマンドレット</span><span class="sxs-lookup"><span data-stu-id="159a9-128">Microsoft Defender Antivirus Cmdlets</span></span>](/powershell/module/defender)