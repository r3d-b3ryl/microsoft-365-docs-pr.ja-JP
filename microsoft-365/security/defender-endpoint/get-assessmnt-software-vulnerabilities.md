---
title: デバイスごとのソフトウェアの脆弱性評価のエクスポート
description: API 応答はデバイスごとに実行され、公開されているデバイスにインストールされている脆弱なソフトウェアと、これらのソフトウェア製品の既知の脆弱性が含まれる。 このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。
keywords: api、apis、エクスポート評価、デバイスごとの評価、脆弱性評価レポート、デバイスの脆弱性評価、デバイスの脆弱性レポート、セキュリティで保護された構成評価、セキュリティで保護された構成レポート、ソフトウェアの脆弱性評価、ソフトウェアの脆弱性レポート、コンピューターによる脆弱性レポート、
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778356"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="9592c-105">デバイスごとのソフトウェアの脆弱性評価のエクスポート</span><span class="sxs-lookup"><span data-stu-id="9592c-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9592c-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9592c-106">**Applies to:**</span></span>

- [<span data-ttu-id="9592c-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9592c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9592c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9592c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9592c-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="9592c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9592c-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="9592c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="9592c-111">すべての既知のソフトウェアの脆弱性と、すべてのデバイスの詳細をデバイスごとに返します。</span><span class="sxs-lookup"><span data-stu-id="9592c-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="9592c-112">さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。</span><span class="sxs-lookup"><span data-stu-id="9592c-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="9592c-113">データの量が非常に多い場合は、次の 2 つの方法で取得できます。</span><span class="sxs-lookup"><span data-stu-id="9592c-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="9592c-114">[ソフトウェアの脆弱性評価 OData のエクスポート](#1-export-software-vulnerabilities-assessment-odata)  API は、OData プロトコルに従って、組織内のすべてのデータを Json 応答として取得します。</span><span class="sxs-lookup"><span data-stu-id="9592c-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="9592c-115">この方法は _、100 K 未満_ のデバイスを持つ小規模な組織に最適です。</span><span class="sxs-lookup"><span data-stu-id="9592c-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="9592c-116">応答がページ分割されたので、応答から \@ odata.nextLink フィールドを使用して次の結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9592c-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="9592c-117">[ファイルを使用してソフトウェアの脆弱性評価をエクスポートする](#2-export-software-vulnerabilities-assessment-via-files) この API ソリューションを使用すると、大量のデータを高速かつ確実に取得できます。</span><span class="sxs-lookup"><span data-stu-id="9592c-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="9592c-118">そのため、100 K を超えるデバイスを使用する大規模な組織に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9592c-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="9592c-119">この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。</span><span class="sxs-lookup"><span data-stu-id="9592c-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="9592c-120">応答には、すべてのデータをダウンロードする URL が含Azure Storage。</span><span class="sxs-lookup"><span data-stu-id="9592c-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="9592c-121">この API を使用すると、すべてのデータを次のようにAzure Storageダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="9592c-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="9592c-122">API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9592c-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="9592c-123">ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="9592c-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="9592c-124">収集されるデータ _(OData_ またはファイル _経由)_ は、現在の状態の現在のスナップショットであり、古いデータは含まれておりません。</span><span class="sxs-lookup"><span data-stu-id="9592c-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="9592c-125">過去のデータを収集するには、ユーザーがデータを独自のデータ ストレージに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9592c-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="9592c-126">特に示されていない限り、一覧表示されているエクスポート評価方法はすべて、\*\*\*\* 完全なエクスポートと **_デバイス別_**(デバイス単位とも **_呼_** ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="9592c-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="9592c-127">1. ソフトウェア脆弱性評価のエクスポート (OData)</span><span class="sxs-lookup"><span data-stu-id="9592c-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="9592c-128">1.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="9592c-128">1.1 API method description</span></span>

<span data-ttu-id="9592c-129">この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="9592c-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="9592c-130">DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID のすべての一意の組み合わせのエントリを含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="9592c-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="9592c-131">制限事項</span><span class="sxs-lookup"><span data-stu-id="9592c-131">Limitations</span></span>

>- <span data-ttu-id="9592c-132">最大ページ サイズは 200,000 です。</span><span class="sxs-lookup"><span data-stu-id="9592c-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="9592c-133">この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1000 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="9592c-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="9592c-134">1.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9592c-134">1.2 Permissions</span></span>

<span data-ttu-id="9592c-135">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="9592c-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9592c-136">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9592c-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="9592c-137">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="9592c-137">Permission type</span></span> | <span data-ttu-id="9592c-138">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9592c-138">Permission</span></span> | <span data-ttu-id="9592c-139">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="9592c-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="9592c-140">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9592c-140">Application</span></span> | <span data-ttu-id="9592c-141">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="9592c-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="9592c-142">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="9592c-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="9592c-143">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="9592c-143">Delegated (work or school account)</span></span> | <span data-ttu-id="9592c-144">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="9592c-144">Vulnerability.Read</span></span> | <span data-ttu-id="9592c-145">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="9592c-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="9592c-146">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="9592c-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="9592c-147">1.4 パラメーター</span><span class="sxs-lookup"><span data-stu-id="9592c-147">1.4 Parameters</span></span>

- <span data-ttu-id="9592c-148">pageSize (既定値 = 50,000) – 応答の結果の数</span><span class="sxs-lookup"><span data-stu-id="9592c-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="9592c-149">$top – 返す結果の数 (@odata.nextLink を返すので、すべてのデータを取得しない)</span><span class="sxs-lookup"><span data-stu-id="9592c-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="9592c-150">1.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="9592c-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="9592c-151">各レコードは約 1KB のデータです。</span><span class="sxs-lookup"><span data-stu-id="9592c-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="9592c-152">正しい pageSize パラメーターを選択する場合は、これを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9592c-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="9592c-153">応答で追加の列が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9592c-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="9592c-154">これらの列は一時的なもので、削除される場合があります。文書化された列のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9592c-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="9592c-155">次の表で定義されているプロパティは、プロパティ ID によってアルファベット順に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9592c-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="9592c-156">この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="9592c-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="9592c-157">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="9592c-157">Property (ID)</span></span> | <span data-ttu-id="9592c-158">データ型</span><span class="sxs-lookup"><span data-stu-id="9592c-158">Data type</span></span> | <span data-ttu-id="9592c-159">説明</span><span class="sxs-lookup"><span data-stu-id="9592c-159">Description</span></span> | <span data-ttu-id="9592c-160">返される値の例</span><span class="sxs-lookup"><span data-stu-id="9592c-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="9592c-161">CveId</span><span class="sxs-lookup"><span data-stu-id="9592c-161">CveId</span></span> | <span data-ttu-id="9592c-162">string</span><span class="sxs-lookup"><span data-stu-id="9592c-162">string</span></span> | <span data-ttu-id="9592c-163">共通の脆弱性と露出 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="9592c-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="9592c-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="9592c-164">CVE-2020-15992</span></span>
<span data-ttu-id="9592c-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="9592c-165">CvssScore</span></span> | <span data-ttu-id="9592c-166">string</span><span class="sxs-lookup"><span data-stu-id="9592c-166">string</span></span> | <span data-ttu-id="9592c-167">CVE の CVSS スコア。</span><span class="sxs-lookup"><span data-stu-id="9592c-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="9592c-168">6.2</span><span class="sxs-lookup"><span data-stu-id="9592c-168">6.2</span></span>
<span data-ttu-id="9592c-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="9592c-169">DeviceId</span></span> | <span data-ttu-id="9592c-170">string</span><span class="sxs-lookup"><span data-stu-id="9592c-170">string</span></span> | <span data-ttu-id="9592c-171">サービス内のデバイスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="9592c-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="9592c-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="9592c-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="9592c-173">DeviceName</span><span class="sxs-lookup"><span data-stu-id="9592c-173">DeviceName</span></span> | <span data-ttu-id="9592c-174">string</span><span class="sxs-lookup"><span data-stu-id="9592c-174">string</span></span> | <span data-ttu-id="9592c-175">デバイスの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="9592c-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="9592c-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9592c-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="9592c-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="9592c-177">DiskPaths</span></span>  | <span data-ttu-id="9592c-178">配列 \[ 文字列\]</span><span class="sxs-lookup"><span data-stu-id="9592c-178">Array\[string\]</span></span> | <span data-ttu-id="9592c-179">製品がデバイスにインストールされていることを示すディスク証拠。</span><span class="sxs-lookup"><span data-stu-id="9592c-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="9592c-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="9592c-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="9592c-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="9592c-181">ExploitabilityLevel</span></span> | <span data-ttu-id="9592c-182">string</span><span class="sxs-lookup"><span data-stu-id="9592c-182">string</span></span> | <span data-ttu-id="9592c-183">この脆弱性の悪用レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="9592c-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="9592c-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="9592c-184">ExploitIsInKit</span></span>
<span data-ttu-id="9592c-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="9592c-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="9592c-186">string</span><span class="sxs-lookup"><span data-stu-id="9592c-186">string</span></span> | <span data-ttu-id="9592c-187">この製品の CVE がデバイスで初めて表示された場合。</span><span class="sxs-lookup"><span data-stu-id="9592c-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="9592c-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="9592c-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="9592c-189">ID</span><span class="sxs-lookup"><span data-stu-id="9592c-189">Id</span></span> | <span data-ttu-id="9592c-190">string</span><span class="sxs-lookup"><span data-stu-id="9592c-190">string</span></span> | <span data-ttu-id="9592c-191">レコードの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="9592c-191">Unique identifier for the record.</span></span> | <span data-ttu-id="9592c-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="9592c-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="9592c-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="9592c-193">LastSeenTimestamp</span></span> | <span data-ttu-id="9592c-194">string</span><span class="sxs-lookup"><span data-stu-id="9592c-194">string</span></span> | <span data-ttu-id="9592c-195">デバイスで CVE が最後に表示された時刻。</span><span class="sxs-lookup"><span data-stu-id="9592c-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="9592c-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="9592c-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="9592c-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="9592c-197">OSPlatform</span></span> | <span data-ttu-id="9592c-198">string</span><span class="sxs-lookup"><span data-stu-id="9592c-198">string</span></span> | <span data-ttu-id="9592c-199">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="9592c-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="9592c-200">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="9592c-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="9592c-201">詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9592c-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="9592c-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="9592c-202">Windows10</span></span>
<span data-ttu-id="9592c-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="9592c-203">RbacGroupName</span></span>  | <span data-ttu-id="9592c-204">string</span><span class="sxs-lookup"><span data-stu-id="9592c-204">string</span></span> | <span data-ttu-id="9592c-205">役割ベースのアクセス制御 (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="9592c-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="9592c-206">このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。</span><span class="sxs-lookup"><span data-stu-id="9592c-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="9592c-207">組織に RBAC グループが含まれている場合、値は "None" になります。</span><span class="sxs-lookup"><span data-stu-id="9592c-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="9592c-208">Servers</span><span class="sxs-lookup"><span data-stu-id="9592c-208">Servers</span></span>
<span data-ttu-id="9592c-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="9592c-209">RecommendationReference</span></span> | <span data-ttu-id="9592c-210">string</span><span class="sxs-lookup"><span data-stu-id="9592c-210">string</span></span> | <span data-ttu-id="9592c-211">このソフトウェアに関連する推奨事項 ID への参照。</span><span class="sxs-lookup"><span data-stu-id="9592c-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="9592c-212">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="9592c-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="9592c-213">RecommendedSecurityUpdate (オプション)</span><span class="sxs-lookup"><span data-stu-id="9592c-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="9592c-214">string</span><span class="sxs-lookup"><span data-stu-id="9592c-214">string</span></span> | <span data-ttu-id="9592c-215">ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。</span><span class="sxs-lookup"><span data-stu-id="9592c-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="9592c-216">2020 年 4 月のセキュリティ更新プログラム</span><span class="sxs-lookup"><span data-stu-id="9592c-216">April 2020 Security Updates</span></span>
<span data-ttu-id="9592c-217">RecommendedSecurityUpdateId (オプション)</span><span class="sxs-lookup"><span data-stu-id="9592c-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="9592c-218">string</span><span class="sxs-lookup"><span data-stu-id="9592c-218">string</span></span> | <span data-ttu-id="9592c-219">対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子</span><span class="sxs-lookup"><span data-stu-id="9592c-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="9592c-220">4550961</span><span class="sxs-lookup"><span data-stu-id="9592c-220">4550961</span></span>
<span data-ttu-id="9592c-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="9592c-221">RegistryPaths</span></span>  | <span data-ttu-id="9592c-222">配列 \[ 文字列\]</span><span class="sxs-lookup"><span data-stu-id="9592c-222">Array\[string\]</span></span> | <span data-ttu-id="9592c-223">製品がデバイスにインストールされていることを示すレジストリ証拠。</span><span class="sxs-lookup"><span data-stu-id="9592c-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="9592c-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight"</span><span class="sxs-lookup"><span data-stu-id="9592c-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="9592c-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="9592c-225">SoftwareName</span></span> | <span data-ttu-id="9592c-226">string</span><span class="sxs-lookup"><span data-stu-id="9592c-226">string</span></span> | <span data-ttu-id="9592c-227">ソフトウェア製品の名前。</span><span class="sxs-lookup"><span data-stu-id="9592c-227">Name of the software product.</span></span> | <span data-ttu-id="9592c-228">クロム</span><span class="sxs-lookup"><span data-stu-id="9592c-228">chrome</span></span>
<span data-ttu-id="9592c-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="9592c-229">SoftwareVendor</span></span> | <span data-ttu-id="9592c-230">string</span><span class="sxs-lookup"><span data-stu-id="9592c-230">string</span></span> | <span data-ttu-id="9592c-231">ソフトウェア ベンダーの名前。</span><span class="sxs-lookup"><span data-stu-id="9592c-231">Name of the software vendor.</span></span> | <span data-ttu-id="9592c-232">google</span><span class="sxs-lookup"><span data-stu-id="9592c-232">google</span></span>
<span data-ttu-id="9592c-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="9592c-233">SoftwareVersion</span></span> | <span data-ttu-id="9592c-234">string</span><span class="sxs-lookup"><span data-stu-id="9592c-234">string</span></span> | <span data-ttu-id="9592c-235">ソフトウェア製品のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="9592c-235">Version number of the software product.</span></span> | <span data-ttu-id="9592c-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="9592c-236">81.0.4044.138</span></span>
<span data-ttu-id="9592c-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="9592c-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="9592c-238">string</span><span class="sxs-lookup"><span data-stu-id="9592c-238">string</span></span> | <span data-ttu-id="9592c-239">CVSS スコアに基づくセキュリティ脆弱性に割り当てられた重大度レベルと、脅威の状況の影響を受ける動的要因。</span><span class="sxs-lookup"><span data-stu-id="9592c-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="9592c-240">中</span><span class="sxs-lookup"><span data-stu-id="9592c-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="9592c-241">1.6 例</span><span class="sxs-lookup"><span data-stu-id="9592c-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="9592c-242">1.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="9592c-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="9592c-243">1.6.2 応答の例</span><span class="sxs-lookup"><span data-stu-id="9592c-243">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="9592c-244">2. ソフトウェアの脆弱性評価をエクスポートする (ファイル経由)</span><span class="sxs-lookup"><span data-stu-id="9592c-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="9592c-245">2.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="9592c-245">2.1 API method description</span></span>

<span data-ttu-id="9592c-246">この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="9592c-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="9592c-247">DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID のすべての一意の組み合わせのエントリを含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="9592c-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="9592c-248">2.1.2 制限事項</span><span class="sxs-lookup"><span data-stu-id="9592c-248">2.1.2 Limitations</span></span>

<span data-ttu-id="9592c-249">この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="9592c-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="9592c-250">2.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9592c-250">2.2 Permissions</span></span>

<span data-ttu-id="9592c-251">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="9592c-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9592c-252">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="9592c-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="9592c-253">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="9592c-253">Permission type</span></span> | <span data-ttu-id="9592c-254">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9592c-254">Permission</span></span> | <span data-ttu-id="9592c-255">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="9592c-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="9592c-256">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9592c-256">Application</span></span> | <span data-ttu-id="9592c-257">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="9592c-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="9592c-258">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="9592c-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="9592c-259">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="9592c-259">Delegated (work or school account)</span></span> | <span data-ttu-id="9592c-260">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="9592c-260">Vulnerability.Read</span></span> | <span data-ttu-id="9592c-261">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="9592c-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="9592c-262">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="9592c-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="9592c-263">2.4 パラメーター</span><span class="sxs-lookup"><span data-stu-id="9592c-263">2.4 Parameters</span></span>

- <span data-ttu-id="9592c-264">sasValidHours – ダウンロード URL が有効になる時間数 (最大 24 時間)</span><span class="sxs-lookup"><span data-stu-id="9592c-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="9592c-265">2.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="9592c-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="9592c-266">ファイルは、複数行 Json 形式& gzip 圧縮ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9592c-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="9592c-267">ダウンロード URL は 3 時間のみ有効です。それ以外の場合は、パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9592c-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="9592c-268">データの最大ダウンロード速度を得る場合は、データが存在するのと同じ Azure 地域からダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="9592c-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="9592c-269">各レコードは約 1KB のデータです。</span><span class="sxs-lookup"><span data-stu-id="9592c-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="9592c-270">正しい pageSize パラメーターを選択する場合は、これを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9592c-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="9592c-271">応答で追加の列が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9592c-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="9592c-272">これらの列は一時的なもので、削除される場合があります。文書化された列のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9592c-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="9592c-273">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="9592c-273">Property (ID)</span></span> | <span data-ttu-id="9592c-274">データ型</span><span class="sxs-lookup"><span data-stu-id="9592c-274">Data type</span></span> | <span data-ttu-id="9592c-275">説明</span><span class="sxs-lookup"><span data-stu-id="9592c-275">Description</span></span> | <span data-ttu-id="9592c-276">返される値の例</span><span class="sxs-lookup"><span data-stu-id="9592c-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="9592c-277">ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="9592c-277">Export files</span></span> | <span data-ttu-id="9592c-278">配列 \[ 文字列\]</span><span class="sxs-lookup"><span data-stu-id="9592c-278">array\[string\]</span></span>  | <span data-ttu-id="9592c-279">組織の現在のスナップショットを保持するファイルのダウンロード URL の一覧。</span><span class="sxs-lookup"><span data-stu-id="9592c-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="9592c-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="9592c-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="9592c-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="9592c-281">GeneratedTime</span></span> | <span data-ttu-id="9592c-282">string</span><span class="sxs-lookup"><span data-stu-id="9592c-282">string</span></span> | <span data-ttu-id="9592c-283">エクスポートが生成された時刻。</span><span class="sxs-lookup"><span data-stu-id="9592c-283">The time that the export was generated.</span></span> | <span data-ttu-id="9592c-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="9592c-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="9592c-285">2.6 例</span><span class="sxs-lookup"><span data-stu-id="9592c-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="9592c-286">2.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="9592c-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="9592c-287">2.6.2 応答例</span><span class="sxs-lookup"><span data-stu-id="9592c-287">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="9592c-288">関連項目</span><span class="sxs-lookup"><span data-stu-id="9592c-288">See also</span></span>

- [<span data-ttu-id="9592c-289">デバイスごとの評価方法とプロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="9592c-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="9592c-290">デバイスごとのセキュリティで保護された構成評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="9592c-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="9592c-291">デバイスごとのソフトウェア インベントリ評価のエクスポート</span><span class="sxs-lookup"><span data-stu-id="9592c-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="9592c-292">その他の関連</span><span class="sxs-lookup"><span data-stu-id="9592c-292">Other related</span></span>

- [<span data-ttu-id="9592c-293">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="9592c-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="9592c-294">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="9592c-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
