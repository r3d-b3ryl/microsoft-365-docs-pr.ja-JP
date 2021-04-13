---
title: Microsoft Defender ウイルス対策クラウド ブロックのタイムアウト期間を構成する
description: Microsoft Defender Antivirus がクラウドの決定を待っている間にファイルの実行をブロックする時間を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、タイムアウト、ブロック、期間、秒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691062"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="58dba-104">クラウド ブロックのタイムアウト期間を構成する</span><span class="sxs-lookup"><span data-stu-id="58dba-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="58dba-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="58dba-105">**Applies to:**</span></span>

- [<span data-ttu-id="58dba-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="58dba-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="58dba-107">Microsoft Defender ウイルス対策が疑わしいファイルを検出すると、Microsoft Defender ウイルス対策クラウド サービスのクエリ中にファイルが [実行されるのを防ぐ可能性があります](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="58dba-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="58dba-108">ファイルがブロックされる [既定の期間](configure-block-at-first-sight-microsoft-defender-antivirus.md) は 10 秒です。</span><span class="sxs-lookup"><span data-stu-id="58dba-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="58dba-109">ファイルの実行が許可される前に待機する追加の期間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="58dba-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="58dba-110">これにより、Microsoft Defender ウイルス対策クラウド サービスから適切な判断を受け取るのに十分な時間が確保されます。</span><span class="sxs-lookup"><span data-stu-id="58dba-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="58dba-111">拡張クラウド ブロック タイムアウトを使用するための前提条件</span><span class="sxs-lookup"><span data-stu-id="58dba-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="58dba-112">[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md) し、その前提条件を有効にしてから、延長タイムアウト期間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58dba-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="58dba-113">延長タイムアウト期間を指定する</span><span class="sxs-lookup"><span data-stu-id="58dba-113">Specify the extended timeout period</span></span>

<span data-ttu-id="58dba-114">グループ ポリシーを使用して、クラウド チェックの延長タイムアウトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="58dba-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="58dba-115">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="58dba-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="58dba-116">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="58dba-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="58dba-117">ツリーを Microsoft Defender Antivirus > **MpEngine >展開する**</span><span class="sxs-lookup"><span data-stu-id="58dba-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="58dba-118">[拡張クラウド チェック **の構成] をダブルクリックし** 、オプションが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="58dba-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="58dba-119">クラウドの決定を待っている間にファイルが実行されるのを防ぐための追加の時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="58dba-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="58dba-120">1 秒から 50 秒の追加時間を秒で指定できます。</span><span class="sxs-lookup"><span data-stu-id="58dba-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="58dba-121">この時間は、既定の 10 秒に追加されます。</span><span class="sxs-lookup"><span data-stu-id="58dba-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="58dba-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58dba-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="58dba-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="58dba-123">Related topics</span></span>

- [<span data-ttu-id="58dba-124">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="58dba-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="58dba-125">クラウドによる保護を通じて次世代のウイルス対策テクノロジを使用する</span><span class="sxs-lookup"><span data-stu-id="58dba-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="58dba-126">ブロックを一目で構成する</span><span class="sxs-lookup"><span data-stu-id="58dba-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="58dba-127">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="58dba-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)