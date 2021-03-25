---
title: Microsoft Defender ATP for Mac のインストールに関する問題のトラブルシューティング
description: Microsoft Defender ATP for Mac のインストールに関する問題のトラブルシューティングを行います。
keywords: microsoft, defender, atp, mac, install
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 888bffdb85adeb7af58504439c1c31c7232cd73b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187627"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="15fd5-104">Microsoft Defender for Endpoint for Mac のインストールに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="15fd5-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="15fd5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="15fd5-105">**Applies to:**</span></span>

- [<span data-ttu-id="15fd5-106">Microsoft Defender for Endpoint for Mac</span><span class="sxs-lookup"><span data-stu-id="15fd5-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="15fd5-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="15fd5-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="15fd5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15fd5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="15fd5-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="15fd5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="15fd5-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="15fd5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="15fd5-111">インストールに失敗しました</span><span class="sxs-lookup"><span data-stu-id="15fd5-111">Installation failed</span></span>

<span data-ttu-id="15fd5-112">手動インストールの場合、インストール ウィザードの [概要] ページには、「インストール中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="15fd5-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="15fd5-113">インストーラーでエラーが発生し、インストールに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="15fd5-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="15fd5-114">ソフトウェア製造元にお問い合わせください。"</span><span class="sxs-lookup"><span data-stu-id="15fd5-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="15fd5-115">MDM の展開では、一般的なインストールエラーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="15fd5-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="15fd5-116">エンド ユーザーに正確なエラーは表示されませんが、インストールの進行状況を示すログ ファイルを保持します `/Library/Logs/Microsoft/mdatp/install.log` 。</span><span class="sxs-lookup"><span data-stu-id="15fd5-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="15fd5-117">このログ ファイルには、各インストール セッションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="15fd5-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="15fd5-118">最後のインストール `sed` セッションのみを出力するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="15fd5-118">You can use `sed` to output the last installation session only:</span></span>

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

<span data-ttu-id="15fd5-119">この例では、実際の理由の先頭に . が付く `[ERROR]` 。</span><span class="sxs-lookup"><span data-stu-id="15fd5-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="15fd5-120">これらのバージョン間のダウングレードがサポートされていないため、インストールに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="15fd5-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="15fd5-121">MDATP インストール ログが見つからないか更新されない</span><span class="sxs-lookup"><span data-stu-id="15fd5-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="15fd5-122">まれに、インストールは MDATP の /Library/Logs/Microsoft/mdatp/install.log ファイルにトレースを残しません。</span><span class="sxs-lookup"><span data-stu-id="15fd5-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="15fd5-123">macOS ログを照会することで、インストールが発生したことを確認し、考えられるエラーを分析できます (これは、クライアント UI がない場合、MDM の展開に役立ちます)。</span><span class="sxs-lookup"><span data-stu-id="15fd5-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="15fd5-124">細いタイム ウィンドウを使用してクエリを実行し、膨大な量の情報が含むので、ログ プロセス名でフィルター処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15fd5-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```