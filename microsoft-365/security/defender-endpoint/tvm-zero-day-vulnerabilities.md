---
title: ゼロデイの脆弱性を軽減する - 脅威と脆弱性の管理
description: 環境内のゼロデイ脆弱性を特定し、軽減する方法については、脅威と脆弱性の管理。
keywords: Microsoft Defender for Endpoint tvm ゼロデイ脆弱性、tvm、threat & 脆弱性の管理、ゼロデイ、0 日間、0 日間の脆弱性の軽減、脆弱な CVE
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: be508e646a67f01887814a0e72170e438ee86212
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933063"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="e16e7-104">ゼロデイの脆弱性を軽減する - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="e16e7-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e16e7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e16e7-105">**Applies to:**</span></span>

- [<span data-ttu-id="e16e7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e16e7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e16e7-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="e16e7-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e16e7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e16e7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e16e7-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="e16e7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e16e7-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="e16e7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="e16e7-111">ゼロデイの脆弱性とは、公式のパッチやセキュリティ更新プログラムがリリースされていない一般に公開された脆弱性です。</span><span class="sxs-lookup"><span data-stu-id="e16e7-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="e16e7-112">ゼロデイの脆弱性は、多くの場合、重大度レベルが高く、積極的に悪用されます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="e16e7-113">脅威と脆弱性の管理は、情報を持つゼロデイの脆弱性のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="e16e7-114">ゼロデイの脆弱性に関する情報を検索する</span><span class="sxs-lookup"><span data-stu-id="e16e7-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="e16e7-115">ゼロデイの脆弱性が見つかったら、この脆弱性に関する情報は、次のエクスペリエンスを通じてMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="e16e7-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="e16e7-116">脅威と脆弱性の管理ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e16e7-116">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="e16e7-117">"トップ セキュリティのおすすめ" カードで、0 日のタグを含む推奨事項を探します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-117">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![ゼロデイ タグを含むおすすめ情報](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="e16e7-119">"トップ脆弱なソフトウェア" カードでゼロデイ タグを持つトップ ソフトウェアを見つける。</span><span class="sxs-lookup"><span data-stu-id="e16e7-119">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![ゼロデイ タグを使用して、脆弱なソフトウェアを上位に設定します。](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="e16e7-121">[弱点] ページ</span><span class="sxs-lookup"><span data-stu-id="e16e7-121">Weaknesses page</span></span>

<span data-ttu-id="e16e7-122">名前の付いたゼロデイの脆弱性と説明と詳細を探します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-122">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="e16e7-123">この脆弱性に CVE-ID が割り当てられている場合は、CVE 名の横にゼロ日ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-123">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="e16e7-124">この脆弱性に CVE-ID が割り当てられていない場合は、"TVM-XXXX-XXXX" のような内部の一時的な名前で検索されます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-124">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="e16e7-125">名前は、公式の CVE-ID が割り当てられた後に更新されますが、以前の内部名はサイド パネルで検索可能で見つかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e16e7-125">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![弱点ページの CVE-2020-17087 のゼロ日の例。](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="e16e7-127">ソフトウェア インベントリ ページ</span><span class="sxs-lookup"><span data-stu-id="e16e7-127">Software inventory page</span></span>

<span data-ttu-id="e16e7-128">ゼロデイ タグを持つソフトウェアを探します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-128">Look for software with the zero-day tag.</span></span> <span data-ttu-id="e16e7-129">"ゼロ日" タグでフィルター処理して、ゼロデイの脆弱性を持つソフトウェアのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-129">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![ソフトウェア インベントリ ページWindows Server 2016ゼロ日の例。](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="e16e7-131">[ソフトウェア] ページ</span><span class="sxs-lookup"><span data-stu-id="e16e7-131">Software page</span></span>

<span data-ttu-id="e16e7-132">ゼロデイの脆弱性の影響を受けた各ソフトウェアのゼロデイ タグを探します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-132">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![ソフトウェア ページの 0 Windows Server 2016例。](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="e16e7-134">[セキュリティの推奨事項] ページ</span><span class="sxs-lookup"><span data-stu-id="e16e7-134">Security recommendations page</span></span>

<span data-ttu-id="e16e7-135">修復と軽減のオプションに関する明確な提案 (存在する場合の回避策を含む) を表示します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-135">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="e16e7-136">"ゼロ日" タグでフィルター処理して、ゼロデイの脆弱性に対処するセキュリティ推奨事項のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-136">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="e16e7-137">ゼロデイの脆弱性と追加の脆弱性を持つソフトウェアが存在する場合は、すべての脆弱性に関する推奨事項が 1 つ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-137">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![[セキュリティの推奨事項] ページWindows Server 2016 0 日の例を示します。](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="e16e7-139">ゼロデイの脆弱性への対処</span><span class="sxs-lookup"><span data-stu-id="e16e7-139">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="e16e7-140">[セキュリティの推奨事項] ページに移動し、0 日間の推奨事項を選択します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-140">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="e16e7-141">フライアウトが開き、そのソフトウェアのゼロデイとその他の脆弱性に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-141">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="e16e7-142">利用可能な場合は、軽減オプションと回避策へのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="e16e7-142">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="e16e7-143">回避策は、パッチまたはセキュリティ更新プログラムが展開されるまで、このゼロデイの脆弱性によるリスクを軽減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-143">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="e16e7-144">修復オプションを開き、注意の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-144">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="e16e7-145">更新プログラムがまだリリースされていないので、ゼロデイの脆弱性に対して"注意が必要な" 修復オプションをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e16e7-145">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="e16e7-146">実行する特定のアクションが行えなかから、期日を選択できない。</span><span class="sxs-lookup"><span data-stu-id="e16e7-146">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="e16e7-147">修復するこのソフトウェアの古い脆弱性がある場合は、[注意が必要] 修復オプションを上書きし、[更新] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-147">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![セキュリティの推奨事項ページWindows Server 2016のゼロ日のフライアウトの例。](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="e16e7-149">ゼロデイ修復アクティビティの追跡</span><span class="sxs-lookup"><span data-stu-id="e16e7-149">Track zero-day remediation activities</span></span>

<span data-ttu-id="e16e7-150">[修復[脅威と脆弱性の管理] ページに](tvm-remediation.md)移動して、修復アクティビティ アイテムを表示します。</span><span class="sxs-lookup"><span data-stu-id="e16e7-150">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="e16e7-151">[注意が必要] 修復オプションを選択した場合は、監視できる実際のアクションが行われなかから、進行状況バー、チケットの状態、または期限はありません。</span><span class="sxs-lookup"><span data-stu-id="e16e7-151">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="e16e7-152">"ソフトウェアの更新" や "注意が必要" などの修復の種類でフィルター処理して、同じカテゴリ内のすべてのアクティビティ アイテムを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-152">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="e16e7-153">ゼロデイの脆弱性へのパッチ適用</span><span class="sxs-lookup"><span data-stu-id="e16e7-153">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="e16e7-154">0 日間の更新プログラムがリリースされると、推奨事項は "更新" に変更され、その横には "ゼロ日の新しいセキュリティ更新プログラム" という青いラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-154">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="e16e7-155">0 日と見なされなくなるので、0 日タグはすべてのページから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e16e7-155">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![新しいパッチ ラベルを使用して "Microsoft Windows 10 を更新する" に関する推奨事項。](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="e16e7-157">関連記事</span><span class="sxs-lookup"><span data-stu-id="e16e7-157">Related articles</span></span>

- [<span data-ttu-id="e16e7-158">脅威と脆弱性の管理概要</span><span class="sxs-lookup"><span data-stu-id="e16e7-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e16e7-159">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e16e7-159">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="e16e7-160">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="e16e7-160">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="e16e7-161">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="e16e7-161">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="e16e7-162">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="e16e7-162">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
