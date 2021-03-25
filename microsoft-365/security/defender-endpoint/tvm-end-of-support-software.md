---
title: サポート終了のソフトウェアとソフトウェアのバージョンを計画する
description: サポートされなくなった、セキュリティ更新プログラムを受け取らないソフトウェアとソフトウェアのバージョンを検出して計画します。
keywords: 脅威と脆弱性の管理、mdatp tvm セキュリティの推奨事項、サイバーセキュリティの推奨事項、アクション可能なセキュリティの推奨事項
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7a1ee326540ec4baab19a266a4e570fd6a364306
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068700"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="9bedd-104">脅威と脆弱性の管理を使用して、サポート終了のソフトウェアとソフトウェアのバージョンを計画する</span><span class="sxs-lookup"><span data-stu-id="9bedd-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9bedd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9bedd-105">**Applies to:**</span></span>

- [<span data-ttu-id="9bedd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9bedd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9bedd-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="9bedd-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="9bedd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bedd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9bedd-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="9bedd-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9bedd-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="9bedd-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="9bedd-111">ソフトウェアバージョンまたはソフトウェア バージョンのサポート終了 (EOL) は、サポートまたはサービスが終了し、セキュリティ更新プログラムを受け取らなくなるという意味です。</span><span class="sxs-lookup"><span data-stu-id="9bedd-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="9bedd-112">サポートが終了したソフトウェアまたはソフトウェア バージョンを使用する場合は、セキュリティの脆弱性、法的リスク、財務上のリスクに組織を公開します。</span><span class="sxs-lookup"><span data-stu-id="9bedd-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="9bedd-113">セキュリティと IT 管理者が一緒に作業し、最適な結果、コンプライアンス、および健全なネットワーク エコシステムのために組織のソフトウェア インベントリが構成されていることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9bedd-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="9bedd-114">サポートが終了し、サポートされなくなったバージョンを更新したアプリを削除または置き換えるオプションを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bedd-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="9bedd-115">サポート終了日前に計画を作成して実装するのが最善です。</span><span class="sxs-lookup"><span data-stu-id="9bedd-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="9bedd-116">サポートされなくなったソフトウェアまたはソフトウェアのバージョンを検索する</span><span class="sxs-lookup"><span data-stu-id="9bedd-116">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="9bedd-117">[脅威と脆弱性の管理] メニューから、[セキュリティの推奨事項 [**] に移動します**](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="9bedd-117">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="9bedd-118">[フィルター] **パネルに移動** し、[タグ] セクションを探します。</span><span class="sxs-lookup"><span data-stu-id="9bedd-118">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="9bedd-119">1 つ以上の EOS タグ オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9bedd-119">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="9bedd-120">次に **、適用します**。</span><span class="sxs-lookup"><span data-stu-id="9bedd-120">Then **Apply**.</span></span>

    ![EOS ソフトウェア、EOS バージョン、および今後の EOS バージョンを示すスクリーンショット タグ。](images/tvm-eos-tag.png)

3. <span data-ttu-id="9bedd-122">サポートが終了しているソフトウェア、サポート終了のソフトウェア バージョン、またはサポートが終了するバージョンに関連する推奨事項の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bedd-122">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="9bedd-123">これらのタグは、ソフトウェア インベントリ ページ [にも表示](tvm-software-inventory.md) されます。</span><span class="sxs-lookup"><span data-stu-id="9bedd-123">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![EOS タグの推奨事項。](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="9bedd-125">バージョンと日付の一覧</span><span class="sxs-lookup"><span data-stu-id="9bedd-125">List of versions and dates</span></span>

<span data-ttu-id="9bedd-126">サポートが終了したバージョンの一覧を表示するには、またはサポートを終了またはすぐにサポートし、それらの日付を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9bedd-126">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="9bedd-127">サポートが終了したバージョンまたはサポートが近日終了するソフトウェアのセキュリティ推奨事項のフライアウトにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bedd-127">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![バージョン配布リンクのスクリーンショット。](images/eos-upcoming-eos.png)

2. <span data-ttu-id="9bedd-129">バージョン配布 **リンクを選択** して、ソフトウェアのドリルダウン ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9bedd-129">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="9bedd-130">そこでは、タグがサポートの終了またはサポートの今後の終了として識別される、フィルター処理されたバージョンの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9bedd-130">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![サポート ソフトウェアが終了したソフトウェアドリルダウン ページのスクリーンショット。](images/software-drilldown-eos.png)

3. <span data-ttu-id="9bedd-132">開くテーブルのバージョンのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9bedd-132">Select one of the versions in the table to open.</span></span> <span data-ttu-id="9bedd-133">たとえば、バージョン 10.0.18362.1。</span><span class="sxs-lookup"><span data-stu-id="9bedd-133">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="9bedd-134">サポート終了日のフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bedd-134">A flyout will appear with the end of support date.</span></span>

    ![サポート終了日のスクリーンショット。](images/version-eos-date.png)

<span data-ttu-id="9bedd-136">サポート終了の状態により脆弱なソフトウェアとソフトウェアのバージョンを特定したら、それらを更新するか、組織から削除するか決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bedd-136">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="9bedd-137">これにより、組織は脆弱性や高度な永続的な脅威にさらされるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="9bedd-137">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9bedd-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bedd-138">Related topics</span></span>

- [<span data-ttu-id="9bedd-139">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="9bedd-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="9bedd-140">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="9bedd-140">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="9bedd-141">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="9bedd-141">Software inventory</span></span>](tvm-software-inventory.md)
