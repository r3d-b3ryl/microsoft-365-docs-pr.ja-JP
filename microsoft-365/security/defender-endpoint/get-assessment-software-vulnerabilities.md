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
ms.openlocfilehash: ea05d37ebcd0953dd109f524775a55cf8d6b3683
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984966"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="afeba-105">デバイスごとのソフトウェアの脆弱性評価のエクスポート</span><span class="sxs-lookup"><span data-stu-id="afeba-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="afeba-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="afeba-106">**Applies to:**</span></span>

- [<span data-ttu-id="afeba-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="afeba-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="afeba-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afeba-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="afeba-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="afeba-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="afeba-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="afeba-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="afeba-111">すべての既知のソフトウェアの脆弱性と、すべてのデバイスの詳細をデバイスごとに返します。</span><span class="sxs-lookup"><span data-stu-id="afeba-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="afeba-112">さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。</span><span class="sxs-lookup"><span data-stu-id="afeba-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="afeba-113">データの量が非常に多い場合は、次の 2 つの方法で取得できます。</span><span class="sxs-lookup"><span data-stu-id="afeba-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="afeba-114">[ソフトウェアの脆弱性評価 OData のエクスポート](#1-export-software-vulnerabilities-assessment-odata)  API は、OData プロトコルに従って、組織内のすべてのデータを Json 応答として取得します。</span><span class="sxs-lookup"><span data-stu-id="afeba-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="afeba-115">この方法は _、100 K 未満_ のデバイスを持つ小規模な組織に最適です。</span><span class="sxs-lookup"><span data-stu-id="afeba-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="afeba-116">応答がページ分割されたので、応答から \@ odata.nextLink フィールドを使用して次の結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="afeba-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="afeba-117">[ファイルを使用してソフトウェアの脆弱性評価をエクスポートする](#2-export-software-vulnerabilities-assessment-via-files) この API ソリューションを使用すると、大量のデータを高速かつ確実に取得できます。</span><span class="sxs-lookup"><span data-stu-id="afeba-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="afeba-118">Via-files は、100 K を超えるデバイスを持つ大規模な組織に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="afeba-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="afeba-119">この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。</span><span class="sxs-lookup"><span data-stu-id="afeba-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="afeba-120">応答には、すべてのデータをダウンロードする URL が含Azure Storage。</span><span class="sxs-lookup"><span data-stu-id="afeba-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="afeba-121">この API を使用すると、すべてのデータを次のようにAzure Storageダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="afeba-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="afeba-122">API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="afeba-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="afeba-123">ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="afeba-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="afeba-124">[デルタ エクスポート ソフトウェアの脆弱性評価 OData](#3-delta-export-software-vulnerabilities-assessment-odata)  DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId、EventTimestamp の各一意の組み合わせのエントリを含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="afeba-124">[Delta export software vulnerabilities assessment OData](#3-delta-export-software-vulnerabilities-assessment-odata)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="afeba-125">API は、OData プロトコルに従って、組織内のデータを Json 応答として取得します。</span><span class="sxs-lookup"><span data-stu-id="afeba-125">The API pulls data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="afeba-126">応答がページ分割されたので、応答から @odata.nextLink フィールドを使用して次の結果をフェッチできます。</span><span class="sxs-lookup"><span data-stu-id="afeba-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="afeba-127">デバイス別に組織のソフトウェア脆弱性評価のスナップショット全体を取得するために使用される完全なソフトウェア脆弱性評価 (OData) とは異なり、デルタ エクスポート OData API 呼び出しは、選択した日付と現在の日付 ("デルタ" API 呼び出し) の間に発生した変更のみを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="afeba-127">Unlike the full software vulnerabilities assessment (OData) - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="afeba-128">毎回大量のデータを含む完全なエクスポートを取得する代わりに、新規、固定、および更新された脆弱性に関する特定の情報のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="afeba-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="afeba-129">デルタ エクスポート OData API 呼び出しを使用して、「修正された脆弱性の数」など、さまざまな KPI を計算することもできます。</span><span class="sxs-lookup"><span data-stu-id="afeba-129">Delta export OData API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="afeba-130">または "組織に追加された新しい脆弱性の数"</span><span class="sxs-lookup"><span data-stu-id="afeba-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="afeba-131">ソフトウェアの脆弱性に対するデルタ エクスポート OData API 呼び出しは、対象の日付範囲のデータのみを返すので、完全なエクスポートとは _見なされません_。</span><span class="sxs-lookup"><span data-stu-id="afeba-131">Because the Delta export OData API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="afeba-132">収集されるデータ _(OData_ またはファイル _経由)_ は、現在の状態の現在のスナップショットであり、古いデータは含まれておりません。</span><span class="sxs-lookup"><span data-stu-id="afeba-132">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="afeba-133">過去のデータを収集するには、ユーザーがデータを独自のデータ ストレージに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afeba-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="afeba-134">特に示されていない限り、一覧表示されているエクスポート評価方法はすべて、\*\*\*\* 完全なエクスポートと **_デバイス別_**(デバイス単位とも **_呼_** ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="afeba-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="afeba-135">1. ソフトウェア脆弱性評価のエクスポート (OData)</span><span class="sxs-lookup"><span data-stu-id="afeba-135">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="afeba-136">1.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="afeba-136">1.1 API method description</span></span>

<span data-ttu-id="afeba-137">この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="afeba-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="afeba-138">DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID のすべての一意の組み合わせのエントリを含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="afeba-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="afeba-139">制限事項</span><span class="sxs-lookup"><span data-stu-id="afeba-139">Limitations</span></span>

>- <span data-ttu-id="afeba-140">最大ページ サイズは 200,000 です。</span><span class="sxs-lookup"><span data-stu-id="afeba-140">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="afeba-141">この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1000 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="afeba-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="afeba-142">1.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="afeba-142">1.2 Permissions</span></span>

<span data-ttu-id="afeba-143">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="afeba-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="afeba-144">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="afeba-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="afeba-145">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="afeba-145">Permission type</span></span> | <span data-ttu-id="afeba-146">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="afeba-146">Permission</span></span> | <span data-ttu-id="afeba-147">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="afeba-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="afeba-148">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="afeba-148">Application</span></span> | <span data-ttu-id="afeba-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="afeba-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="afeba-150">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="afeba-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="afeba-151">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="afeba-151">Delegated (work or school account)</span></span> | <span data-ttu-id="afeba-152">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="afeba-152">Vulnerability.Read</span></span> | <span data-ttu-id="afeba-153">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="afeba-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="afeba-154">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="afeba-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="afeba-155">1.4 パラメーター</span><span class="sxs-lookup"><span data-stu-id="afeba-155">1.4 Parameters</span></span>

- <span data-ttu-id="afeba-156">pageSize (既定値 = 50,000) – 応答の結果の数</span><span class="sxs-lookup"><span data-stu-id="afeba-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="afeba-157">$top – 返す結果の数 (@odata.nextLink を返すので、すべてのデータを取得しない)</span><span class="sxs-lookup"><span data-stu-id="afeba-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="afeba-158">1.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="afeba-158">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="afeba-159">各レコードは約 1KB のデータです。</span><span class="sxs-lookup"><span data-stu-id="afeba-159">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="afeba-160">正しい pageSize パラメーターを選択する場合は、これを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afeba-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="afeba-161">応答で追加の列が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="afeba-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="afeba-162">これらの列は一時的なもので、削除される場合があります。文書化された列のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="afeba-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="afeba-163">次の表で定義されているプロパティは、プロパティ ID によってアルファベット順に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="afeba-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="afeba-164">この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="afeba-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="afeba-165">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="afeba-165">Property (ID)</span></span> | <span data-ttu-id="afeba-166">データ型</span><span class="sxs-lookup"><span data-stu-id="afeba-166">Data type</span></span> | <span data-ttu-id="afeba-167">説明</span><span class="sxs-lookup"><span data-stu-id="afeba-167">Description</span></span> | <span data-ttu-id="afeba-168">返される値の例</span><span class="sxs-lookup"><span data-stu-id="afeba-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="afeba-169">CveId</span><span class="sxs-lookup"><span data-stu-id="afeba-169">CveId</span></span> | <span data-ttu-id="afeba-170">string</span><span class="sxs-lookup"><span data-stu-id="afeba-170">string</span></span> | <span data-ttu-id="afeba-171">共通の脆弱性と露出 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="afeba-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="afeba-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="afeba-172">CVE-2020-15992</span></span>
<span data-ttu-id="afeba-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="afeba-173">CvssScore</span></span> | <span data-ttu-id="afeba-174">string</span><span class="sxs-lookup"><span data-stu-id="afeba-174">string</span></span> | <span data-ttu-id="afeba-175">CVE の CVSS スコア。</span><span class="sxs-lookup"><span data-stu-id="afeba-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="afeba-176">6.2</span><span class="sxs-lookup"><span data-stu-id="afeba-176">6.2</span></span>
<span data-ttu-id="afeba-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="afeba-177">DeviceId</span></span> | <span data-ttu-id="afeba-178">string</span><span class="sxs-lookup"><span data-stu-id="afeba-178">string</span></span> | <span data-ttu-id="afeba-179">サービス内のデバイスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="afeba-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="afeba-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="afeba-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="afeba-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="afeba-181">DeviceName</span></span> | <span data-ttu-id="afeba-182">string</span><span class="sxs-lookup"><span data-stu-id="afeba-182">string</span></span> | <span data-ttu-id="afeba-183">デバイスの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="afeba-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="afeba-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="afeba-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="afeba-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="afeba-185">DiskPaths</span></span>  | <span data-ttu-id="afeba-186">配列 \[ 文字列\]</span><span class="sxs-lookup"><span data-stu-id="afeba-186">Array\[string\]</span></span> | <span data-ttu-id="afeba-187">製品がデバイスにインストールされていることを示すディスク証拠。</span><span class="sxs-lookup"><span data-stu-id="afeba-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="afeba-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="afeba-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="afeba-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="afeba-189">ExploitabilityLevel</span></span> | <span data-ttu-id="afeba-190">string</span><span class="sxs-lookup"><span data-stu-id="afeba-190">string</span></span> | <span data-ttu-id="afeba-191">この脆弱性の悪用レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="afeba-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="afeba-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="afeba-192">ExploitIsInKit</span></span>
<span data-ttu-id="afeba-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="afeba-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="afeba-194">string</span><span class="sxs-lookup"><span data-stu-id="afeba-194">string</span></span> | <span data-ttu-id="afeba-195">この製品の CVE がデバイスで初めて表示された場合。</span><span class="sxs-lookup"><span data-stu-id="afeba-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="afeba-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="afeba-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="afeba-197">ID</span><span class="sxs-lookup"><span data-stu-id="afeba-197">Id</span></span> | <span data-ttu-id="afeba-198">string</span><span class="sxs-lookup"><span data-stu-id="afeba-198">string</span></span> | <span data-ttu-id="afeba-199">レコードの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="afeba-199">Unique identifier for the record.</span></span> | <span data-ttu-id="afeba-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="afeba-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="afeba-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="afeba-201">LastSeenTimestamp</span></span> | <span data-ttu-id="afeba-202">string</span><span class="sxs-lookup"><span data-stu-id="afeba-202">string</span></span> | <span data-ttu-id="afeba-203">デバイスで CVE が最後に表示された時刻。</span><span class="sxs-lookup"><span data-stu-id="afeba-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="afeba-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="afeba-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="afeba-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="afeba-205">OSPlatform</span></span> | <span data-ttu-id="afeba-206">string</span><span class="sxs-lookup"><span data-stu-id="afeba-206">string</span></span> | <span data-ttu-id="afeba-207">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="afeba-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="afeba-208">このプロパティは、同じファミリ内のバリエーションを含む特定のオペレーティング システム (Windows 10 7 などWindowsします。</span><span class="sxs-lookup"><span data-stu-id="afeba-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="afeba-209">詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afeba-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="afeba-210">Windows10</span><span class="sxs-lookup"><span data-stu-id="afeba-210">Windows10</span></span>
<span data-ttu-id="afeba-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="afeba-211">RbacGroupName</span></span>  | <span data-ttu-id="afeba-212">string</span><span class="sxs-lookup"><span data-stu-id="afeba-212">string</span></span> | <span data-ttu-id="afeba-213">役割ベースのアクセス制御 (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="afeba-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="afeba-214">このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。</span><span class="sxs-lookup"><span data-stu-id="afeba-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="afeba-215">組織に RBAC グループが含まれている場合、値は "None" になります。</span><span class="sxs-lookup"><span data-stu-id="afeba-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="afeba-216">Servers</span><span class="sxs-lookup"><span data-stu-id="afeba-216">Servers</span></span>
<span data-ttu-id="afeba-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="afeba-217">RecommendationReference</span></span> | <span data-ttu-id="afeba-218">string</span><span class="sxs-lookup"><span data-stu-id="afeba-218">string</span></span> | <span data-ttu-id="afeba-219">このソフトウェアに関連する推奨事項 ID への参照。</span><span class="sxs-lookup"><span data-stu-id="afeba-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="afeba-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="afeba-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="afeba-221">RecommendedSecurityUpdate (オプション)</span><span class="sxs-lookup"><span data-stu-id="afeba-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="afeba-222">string</span><span class="sxs-lookup"><span data-stu-id="afeba-222">string</span></span> | <span data-ttu-id="afeba-223">ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。</span><span class="sxs-lookup"><span data-stu-id="afeba-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="afeba-224">2020 年 4 月のセキュリティ更新プログラム</span><span class="sxs-lookup"><span data-stu-id="afeba-224">April 2020 Security Updates</span></span>
<span data-ttu-id="afeba-225">RecommendedSecurityUpdateId (オプション)</span><span class="sxs-lookup"><span data-stu-id="afeba-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="afeba-226">string</span><span class="sxs-lookup"><span data-stu-id="afeba-226">string</span></span> | <span data-ttu-id="afeba-227">対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子</span><span class="sxs-lookup"><span data-stu-id="afeba-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="afeba-228">4550961</span><span class="sxs-lookup"><span data-stu-id="afeba-228">4550961</span></span>
<span data-ttu-id="afeba-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="afeba-229">RegistryPaths</span></span>  | <span data-ttu-id="afeba-230">配列 \[ 文字列\]</span><span class="sxs-lookup"><span data-stu-id="afeba-230">Array\[string\]</span></span> | <span data-ttu-id="afeba-231">製品がデバイスにインストールされていることを示すレジストリ証拠。</span><span class="sxs-lookup"><span data-stu-id="afeba-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="afeba-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight"</span><span class="sxs-lookup"><span data-stu-id="afeba-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="afeba-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="afeba-233">SoftwareName</span></span> | <span data-ttu-id="afeba-234">string</span><span class="sxs-lookup"><span data-stu-id="afeba-234">string</span></span> | <span data-ttu-id="afeba-235">ソフトウェア製品の名前。</span><span class="sxs-lookup"><span data-stu-id="afeba-235">Name of the software product.</span></span> | <span data-ttu-id="afeba-236">クロム</span><span class="sxs-lookup"><span data-stu-id="afeba-236">chrome</span></span>
<span data-ttu-id="afeba-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="afeba-237">SoftwareVendor</span></span> | <span data-ttu-id="afeba-238">string</span><span class="sxs-lookup"><span data-stu-id="afeba-238">string</span></span> | <span data-ttu-id="afeba-239">ソフトウェア ベンダーの名前。</span><span class="sxs-lookup"><span data-stu-id="afeba-239">Name of the software vendor.</span></span> | <span data-ttu-id="afeba-240">google</span><span class="sxs-lookup"><span data-stu-id="afeba-240">google</span></span>
<span data-ttu-id="afeba-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="afeba-241">SoftwareVersion</span></span> | <span data-ttu-id="afeba-242">string</span><span class="sxs-lookup"><span data-stu-id="afeba-242">string</span></span> | <span data-ttu-id="afeba-243">ソフトウェア製品のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="afeba-243">Version number of the software product.</span></span> | <span data-ttu-id="afeba-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="afeba-244">81.0.4044.138</span></span>
<span data-ttu-id="afeba-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="afeba-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="afeba-246">string</span><span class="sxs-lookup"><span data-stu-id="afeba-246">string</span></span> | <span data-ttu-id="afeba-247">CVSS スコアに基づくセキュリティ脆弱性に割り当てられた重大度レベルと、脅威の状況の影響を受ける動的要因。</span><span class="sxs-lookup"><span data-stu-id="afeba-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="afeba-248">中</span><span class="sxs-lookup"><span data-stu-id="afeba-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="afeba-249">1.6 例</span><span class="sxs-lookup"><span data-stu-id="afeba-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="afeba-250">1.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="afeba-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="afeba-251">1.6.2 応答の例</span><span class="sxs-lookup"><span data-stu-id="afeba-251">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="afeba-252">2. ソフトウェアの脆弱性評価をエクスポートする (ファイル経由)</span><span class="sxs-lookup"><span data-stu-id="afeba-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="afeba-253">2.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="afeba-253">2.1 API method description</span></span>

<span data-ttu-id="afeba-254">この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="afeba-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="afeba-255">DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID のすべての一意の組み合わせのエントリを含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="afeba-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="afeba-256">2.1.2 制限事項</span><span class="sxs-lookup"><span data-stu-id="afeba-256">2.1.2 Limitations</span></span>

<span data-ttu-id="afeba-257">この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="afeba-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="afeba-258">2.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="afeba-258">2.2 Permissions</span></span>

<span data-ttu-id="afeba-259">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="afeba-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="afeba-260">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="afeba-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="afeba-261">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="afeba-261">Permission type</span></span> | <span data-ttu-id="afeba-262">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="afeba-262">Permission</span></span> | <span data-ttu-id="afeba-263">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="afeba-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="afeba-264">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="afeba-264">Application</span></span> | <span data-ttu-id="afeba-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="afeba-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="afeba-266">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="afeba-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="afeba-267">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="afeba-267">Delegated (work or school account)</span></span> | <span data-ttu-id="afeba-268">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="afeba-268">Vulnerability.Read</span></span> | <span data-ttu-id="afeba-269">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="afeba-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="afeba-270">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="afeba-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="afeba-271">2.4 パラメーター</span><span class="sxs-lookup"><span data-stu-id="afeba-271">2.4 Parameters</span></span>

- <span data-ttu-id="afeba-272">sasValidHours – ダウンロード URL が有効になる時間数 (最大 24 時間)</span><span class="sxs-lookup"><span data-stu-id="afeba-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="afeba-273">2.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="afeba-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="afeba-274">ファイルは、複数行 Json 形式& gzip 圧縮ファイルです。</span><span class="sxs-lookup"><span data-stu-id="afeba-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="afeba-275">ダウンロード URL は 3 時間のみ有効です。それ以外の場合は、パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="afeba-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="afeba-276">データの最大ダウンロード速度を得る場合は、データが存在するのと同じ Azure 地域からダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="afeba-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="afeba-277">各レコードは約 1KB のデータです。</span><span class="sxs-lookup"><span data-stu-id="afeba-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="afeba-278">正しい pageSize パラメーターを選択する場合は、これを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afeba-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="afeba-279">応答で追加の列が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="afeba-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="afeba-280">これらの列は一時的なもので、削除される場合があります。文書化された列のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="afeba-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="afeba-281">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="afeba-281">Property (ID)</span></span> | <span data-ttu-id="afeba-282">データ型</span><span class="sxs-lookup"><span data-stu-id="afeba-282">Data type</span></span> | <span data-ttu-id="afeba-283">説明</span><span class="sxs-lookup"><span data-stu-id="afeba-283">Description</span></span> | <span data-ttu-id="afeba-284">返される値の例</span><span class="sxs-lookup"><span data-stu-id="afeba-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="afeba-285">ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="afeba-285">Export files</span></span> | <span data-ttu-id="afeba-286">配列 \[ 文字列\]</span><span class="sxs-lookup"><span data-stu-id="afeba-286">array\[string\]</span></span>  | <span data-ttu-id="afeba-287">組織の現在のスナップショットを保持するファイルのダウンロード URL の一覧。</span><span class="sxs-lookup"><span data-stu-id="afeba-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="afeba-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="afeba-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="afeba-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="afeba-289">GeneratedTime</span></span> | <span data-ttu-id="afeba-290">string</span><span class="sxs-lookup"><span data-stu-id="afeba-290">string</span></span> | <span data-ttu-id="afeba-291">エクスポートが生成された時刻。</span><span class="sxs-lookup"><span data-stu-id="afeba-291">The time that the export was generated.</span></span> | <span data-ttu-id="afeba-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="afeba-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="afeba-293">2.6 例</span><span class="sxs-lookup"><span data-stu-id="afeba-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="afeba-294">2.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="afeba-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="afeba-295">2.6.2 応答例</span><span class="sxs-lookup"><span data-stu-id="afeba-295">2.6.2 Response example</span></span>

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

## <a name="3-delta-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="afeba-296">3. デルタ エクスポート ソフトウェアの脆弱性評価 (OData)</span><span class="sxs-lookup"><span data-stu-id="afeba-296">3. Delta export software vulnerabilities assessment (OData)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="afeba-297">3.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="afeba-297">3.1 API method description</span></span>

<span data-ttu-id="afeba-298">DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId のすべての一意の組み合わせのエントリを含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="afeba-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="afeba-299">API は、OData プロトコルに従って、組織内のデータを Json 応答として取得します。</span><span class="sxs-lookup"><span data-stu-id="afeba-299">The API pulls data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="afeba-300">応答がページ分割されたので、応答から @odata.nextLink フィールドを使用して次の結果をフェッチできます。</span><span class="sxs-lookup"><span data-stu-id="afeba-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="afeba-301">デバイス別に組織のソフトウェア脆弱性評価のスナップショット全体を取得するために使用される完全なソフトウェア脆弱性評価 (OData) とは異なり、デルタ エクスポート OData API 呼び出しは、選択した日付と現在の日付 ("デルタ" API 呼び出し) の間に発生した変更のみを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="afeba-301">Unlike the full software vulnerabilities assessment (OData) - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export  OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="afeba-302">毎回大量のデータを含む完全なエクスポートを取得する代わりに、新規、固定、および更新された脆弱性に関する特定の情報のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="afeba-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="afeba-303">デルタ エクスポート OData API 呼び出しを使用して、「修正された脆弱性の数」など、さまざまな KPI を計算することもできます。</span><span class="sxs-lookup"><span data-stu-id="afeba-303">Delta export OData API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="afeba-304">または "組織に追加された新しい脆弱性の数"</span><span class="sxs-lookup"><span data-stu-id="afeba-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="afeba-305">デバイス API 呼び出しによる完全なエクスポート ソフトウェアの脆弱性評価を少なくとも週に 1 回使用することを強くお勧めします。この追加のエクスポート ソフトウェアの脆弱性は、デバイス (デルタ) API 呼び出しによって他のすべての日に変更されます。</span><span class="sxs-lookup"><span data-stu-id="afeba-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="afeba-306">他の Assessments OData API とは異なり、"デルタ エクスポート" は完全なエクスポートではありません。</span><span class="sxs-lookup"><span data-stu-id="afeba-306">Unlike the other Assessments OData API, the “delta export” is not a full export.</span></span> <span data-ttu-id="afeba-307">デルタ エクスポートには、選択した日付と現在の日付 ("デルタ" API 呼び出し) の間に発生した変更だけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="afeba-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="limitations"></a><span data-ttu-id="afeba-308">制限事項</span><span class="sxs-lookup"><span data-stu-id="afeba-308">Limitations</span></span>

- <span data-ttu-id="afeba-309">最大ページ サイズは 200,000 です。</span><span class="sxs-lookup"><span data-stu-id="afeba-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="afeba-310">sinceTime パラメーターの最大日数は 14 日です。</span><span class="sxs-lookup"><span data-stu-id="afeba-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="afeba-311">この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1000 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="afeba-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="afeba-312">3.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="afeba-312">3.2 Permissions</span></span>

<span data-ttu-id="afeba-313">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="afeba-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="afeba-314">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="afeba-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="afeba-315">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="afeba-315">Permission type</span></span> | <span data-ttu-id="afeba-316">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="afeba-316">Permission</span></span> | <span data-ttu-id="afeba-317">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="afeba-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="afeba-318">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="afeba-318">Application</span></span> | <span data-ttu-id="afeba-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="afeba-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="afeba-320">'脅威と脆弱性管理の脆弱性情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="afeba-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="afeba-321">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="afeba-321">Delegated (work or school account)</span></span> | <span data-ttu-id="afeba-322">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="afeba-322">Vulnerability.Read</span></span> | <span data-ttu-id="afeba-323">'脅威と脆弱性管理の脆弱性情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="afeba-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="afeba-324">3.3 URL</span><span class="sxs-lookup"><span data-stu-id="afeba-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="afeba-325">3.4 パラメーター</span><span class="sxs-lookup"><span data-stu-id="afeba-325">3.4 Parameters</span></span>

- <span data-ttu-id="afeba-326">sinceTime (必須) – 選択した時刻と今日の間のデータ。</span><span class="sxs-lookup"><span data-stu-id="afeba-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="afeba-327">pageSize (既定値 = 50,000) – 応答の結果の数</span><span class="sxs-lookup"><span data-stu-id="afeba-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="afeba-328">$top – 返す結果の数 (@odata.nextLink を返すので、すべてのデータを取得しない)</span><span class="sxs-lookup"><span data-stu-id="afeba-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="afeba-329">3.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="afeba-329">3.5 Properties</span></span>

<span data-ttu-id="afeba-330">返される各レコードには、デバイス OData API による完全なエクスポート ソフトウェア脆弱性評価のすべてのデータと  _**、EventTimestamp**_ と Status の 2 つの追加フィールドが含 _**まれます**_。</span><span class="sxs-lookup"><span data-stu-id="afeba-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device OData API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
><span data-ttu-id="afeba-331">-一部の追加の列が応答で返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="afeba-331">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="afeba-332">これらの列は一時的なもので、削除される可能性があります。文書化された列のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="afeba-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
><span data-ttu-id="afeba-333">-次の表で定義されているプロパティは、プロパティ ID によってアルファベット順に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="afeba-333">-The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="afeba-334">この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="afeba-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br>

<span data-ttu-id="afeba-335">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="afeba-335">Property (ID)</span></span> | <span data-ttu-id="afeba-336">データ型</span><span class="sxs-lookup"><span data-stu-id="afeba-336">Data type</span></span> | <span data-ttu-id="afeba-337">説明</span><span class="sxs-lookup"><span data-stu-id="afeba-337">Description</span></span> | <span data-ttu-id="afeba-338">返される値の例</span><span class="sxs-lookup"><span data-stu-id="afeba-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="afeba-339">CveId</span><span class="sxs-lookup"><span data-stu-id="afeba-339">CveId</span></span> | <span data-ttu-id="afeba-340">string</span><span class="sxs-lookup"><span data-stu-id="afeba-340">string</span></span> | <span data-ttu-id="afeba-341">共通の脆弱性と露出 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="afeba-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="afeba-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="afeba-342">CVE-2020-15992</span></span>  
<span data-ttu-id="afeba-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="afeba-343">CvssScore</span></span> | <span data-ttu-id="afeba-344">string</span><span class="sxs-lookup"><span data-stu-id="afeba-344">string</span></span> | <span data-ttu-id="afeba-345">CVE の CVSS スコア。</span><span class="sxs-lookup"><span data-stu-id="afeba-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="afeba-346">6.2</span><span class="sxs-lookup"><span data-stu-id="afeba-346">6.2</span></span>  
<span data-ttu-id="afeba-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="afeba-347">DeviceId</span></span> | <span data-ttu-id="afeba-348">string</span><span class="sxs-lookup"><span data-stu-id="afeba-348">string</span></span> | <span data-ttu-id="afeba-349">サービス内のデバイスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="afeba-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="afeba-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="afeba-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="afeba-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="afeba-351">DeviceName</span></span> | <span data-ttu-id="afeba-352">string</span><span class="sxs-lookup"><span data-stu-id="afeba-352">string</span></span> | <span data-ttu-id="afeba-353">デバイスの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="afeba-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="afeba-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="afeba-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="afeba-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="afeba-355">DiskPaths</span></span> | <span data-ttu-id="afeba-356">Array[string]</span><span class="sxs-lookup"><span data-stu-id="afeba-356">Array[string]</span></span> | <span data-ttu-id="afeba-357">製品がデバイスにインストールされていることを示すディスク証拠。</span><span class="sxs-lookup"><span data-stu-id="afeba-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="afeba-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="afeba-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="afeba-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="afeba-359">EventTimestamp</span></span> | <span data-ttu-id="afeba-360">String</span><span class="sxs-lookup"><span data-stu-id="afeba-360">String</span></span> | <span data-ttu-id="afeba-361">このデルタ イベントが見つかった時刻。</span><span class="sxs-lookup"><span data-stu-id="afeba-361">The time this delta event was found.</span></span> | <span data-ttu-id="afeba-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="afeba-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="afeba-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="afeba-363">ExploitabilityLevel</span></span> | <span data-ttu-id="afeba-364">string</span><span class="sxs-lookup"><span data-stu-id="afeba-364">string</span></span> | <span data-ttu-id="afeba-365">この脆弱性の悪用レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="afeba-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="afeba-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="afeba-366">ExploitIsInKit</span></span>  
<span data-ttu-id="afeba-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="afeba-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="afeba-368">string</span><span class="sxs-lookup"><span data-stu-id="afeba-368">string</span></span> | <span data-ttu-id="afeba-369">この製品の CVE がデバイスで初めて表示された場合。</span><span class="sxs-lookup"><span data-stu-id="afeba-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="afeba-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="afeba-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="afeba-371">ID</span><span class="sxs-lookup"><span data-stu-id="afeba-371">Id</span></span> | <span data-ttu-id="afeba-372">string</span><span class="sxs-lookup"><span data-stu-id="afeba-372">string</span></span> | <span data-ttu-id="afeba-373">レコードの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="afeba-373">Unique identifier for the record.</span></span> | <span data-ttu-id="afeba-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="afeba-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="afeba-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="afeba-375">LastSeenTimestamp</span></span> | <span data-ttu-id="afeba-376">string</span><span class="sxs-lookup"><span data-stu-id="afeba-376">string</span></span> | <span data-ttu-id="afeba-377">デバイスで CVE が最後に表示された時刻。</span><span class="sxs-lookup"><span data-stu-id="afeba-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="afeba-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="afeba-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="afeba-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="afeba-379">OSPlatform</span></span> | <span data-ttu-id="afeba-380">string</span><span class="sxs-lookup"><span data-stu-id="afeba-380">string</span></span> | <span data-ttu-id="afeba-381">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="afeba-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="afeba-382">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="afeba-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="afeba-383">詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afeba-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="afeba-384">Windows10</span><span class="sxs-lookup"><span data-stu-id="afeba-384">Windows10</span></span>  
<span data-ttu-id="afeba-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="afeba-385">RbacGroupName</span></span> | <span data-ttu-id="afeba-386">string</span><span class="sxs-lookup"><span data-stu-id="afeba-386">string</span></span> | <span data-ttu-id="afeba-387">役割ベースのアクセス制御 (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="afeba-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="afeba-388">このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。</span><span class="sxs-lookup"><span data-stu-id="afeba-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="afeba-389">組織に RBAC グループが含まれている場合、値は "None" になります。</span><span class="sxs-lookup"><span data-stu-id="afeba-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="afeba-390">Servers</span><span class="sxs-lookup"><span data-stu-id="afeba-390">Servers</span></span>  
<span data-ttu-id="afeba-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="afeba-391">RecommendationReference</span></span> | <span data-ttu-id="afeba-392">string</span><span class="sxs-lookup"><span data-stu-id="afeba-392">string</span></span> | <span data-ttu-id="afeba-393">このソフトウェアに関連する推奨事項 ID への参照。</span><span class="sxs-lookup"><span data-stu-id="afeba-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="afeba-394">va-microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="afeba-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="afeba-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="afeba-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="afeba-396">string</span><span class="sxs-lookup"><span data-stu-id="afeba-396">string</span></span> | <span data-ttu-id="afeba-397">ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。</span><span class="sxs-lookup"><span data-stu-id="afeba-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="afeba-398">2020 年 4 月のセキュリティ更新プログラム</span><span class="sxs-lookup"><span data-stu-id="afeba-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="afeba-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="afeba-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="afeba-400">string</span><span class="sxs-lookup"><span data-stu-id="afeba-400">string</span></span> | <span data-ttu-id="afeba-401">対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子</span><span class="sxs-lookup"><span data-stu-id="afeba-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="afeba-402">4550961</span><span class="sxs-lookup"><span data-stu-id="afeba-402">4550961</span></span>  
<span data-ttu-id="afeba-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="afeba-403">RegistryPaths</span></span>  | <span data-ttu-id="afeba-404">Array[string]</span><span class="sxs-lookup"><span data-stu-id="afeba-404">Array[string]</span></span> | <span data-ttu-id="afeba-405">製品がデバイスにインストールされていることを示すレジストリ証拠。</span><span class="sxs-lookup"><span data-stu-id="afeba-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="afeba-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome"</span><span class="sxs-lookup"><span data-stu-id="afeba-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="afeba-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="afeba-407">SoftwareName</span></span> | <span data-ttu-id="afeba-408">string</span><span class="sxs-lookup"><span data-stu-id="afeba-408">string</span></span> | <span data-ttu-id="afeba-409">ソフトウェア製品の名前。</span><span class="sxs-lookup"><span data-stu-id="afeba-409">Name of the software product.</span></span> | <span data-ttu-id="afeba-410">クロム</span><span class="sxs-lookup"><span data-stu-id="afeba-410">chrome</span></span>  
<span data-ttu-id="afeba-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="afeba-411">SoftwareVendor</span></span> | <span data-ttu-id="afeba-412">string</span><span class="sxs-lookup"><span data-stu-id="afeba-412">string</span></span> | <span data-ttu-id="afeba-413">ソフトウェア ベンダーの名前。</span><span class="sxs-lookup"><span data-stu-id="afeba-413">Name of the software vendor.</span></span> | <span data-ttu-id="afeba-414">google</span><span class="sxs-lookup"><span data-stu-id="afeba-414">google</span></span>  
<span data-ttu-id="afeba-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="afeba-415">SoftwareVersion</span></span> | <span data-ttu-id="afeba-416">string</span><span class="sxs-lookup"><span data-stu-id="afeba-416">string</span></span> | <span data-ttu-id="afeba-417">ソフトウェア製品のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="afeba-417">Version number of the software product.</span></span> | <span data-ttu-id="afeba-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="afeba-418">81.0.4044.138</span></span>  
<span data-ttu-id="afeba-419">状態</span><span class="sxs-lookup"><span data-stu-id="afeba-419">Status</span></span> | <span data-ttu-id="afeba-420">String</span><span class="sxs-lookup"><span data-stu-id="afeba-420">String</span></span> | <span data-ttu-id="afeba-421">**New**  (デバイスに導入された新しい脆弱性の場合) (1)**修正** 済み (この脆弱性がデバイス上に存在しなくなった場合、これは修復   されたという意味です)。</span><span class="sxs-lookup"><span data-stu-id="afeba-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="afeba-422">(2) **更新**  (デバイスの脆弱性が変更された場合)。</span><span class="sxs-lookup"><span data-stu-id="afeba-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="afeba-423">変更の可能性は、CVSS スコア、悪用可能性レベル、重大度レベル、DiskPaths、RegistryPaths、RecommendedSecurityUpdate などです。</span><span class="sxs-lookup"><span data-stu-id="afeba-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="afeba-424">Fixed</span><span class="sxs-lookup"><span data-stu-id="afeba-424">Fixed</span></span>
<span data-ttu-id="afeba-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="afeba-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="afeba-426">string</span><span class="sxs-lookup"><span data-stu-id="afeba-426">string</span></span> | <span data-ttu-id="afeba-427">CVSS スコアに基づくセキュリティ脆弱性に割り当てられた重大度レベルと、脅威の状況の影響を受ける動的要因。</span><span class="sxs-lookup"><span data-stu-id="afeba-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="afeba-428">中</span><span class="sxs-lookup"><span data-stu-id="afeba-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="afeba-429">明確化</span><span class="sxs-lookup"><span data-stu-id="afeba-429">Clarifications</span></span>

- <span data-ttu-id="afeba-430">ソフトウェアがバージョン 1.0 からバージョン 2.0 に更新され、両方のバージョンが CVE-A に公開されている場合、次の 2 つの個別のイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afeba-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   <span data-ttu-id="afeba-431">a.</span><span class="sxs-lookup"><span data-stu-id="afeba-431">a.</span></span> <span data-ttu-id="afeba-432">修正済み – バージョン 1.0 の CVE-A が修正されました</span><span class="sxs-lookup"><span data-stu-id="afeba-432">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   <span data-ttu-id="afeba-433">b.</span><span class="sxs-lookup"><span data-stu-id="afeba-433">b.</span></span> <span data-ttu-id="afeba-434">New – バージョン 2.0 の CVE-A が追加されました</span><span class="sxs-lookup"><span data-stu-id="afeba-434">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="afeba-435">バージョン 1.0 のソフトウェアで特定の時点 (たとえば、1 月 10 日) に特定の脆弱性 (CVE-A など) が最初に見られた場合、数日後に同じ CVE-A に公開されているバージョン 2.0 に更新された場合、次の 2 つの分離イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="afeba-435">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   <span data-ttu-id="afeba-436">a.</span><span class="sxs-lookup"><span data-stu-id="afeba-436">a.</span></span> <span data-ttu-id="afeba-437">修正済み – CVE-X、FirstSeenTimestamp 1 月 10 日バージョン 1,0。</span><span class="sxs-lookup"><span data-stu-id="afeba-437">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   <span data-ttu-id="afeba-438">b.</span><span class="sxs-lookup"><span data-stu-id="afeba-438">b.</span></span> <span data-ttu-id="afeba-439">New – CVE-X、FirstSeenTimestamp 1 月 10 日バージョン 2.0。</span><span class="sxs-lookup"><span data-stu-id="afeba-439">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="afeba-440">3.6 例</span><span class="sxs-lookup"><span data-stu-id="afeba-440">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="afeba-441">3.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="afeba-441">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="afeba-442">3.6.2 応答例</span><span class="sxs-lookup"><span data-stu-id="afeba-442">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="afeba-443">関連項目</span><span class="sxs-lookup"><span data-stu-id="afeba-443">See also</span></span>

- [<span data-ttu-id="afeba-444">デバイスごとの評価方法とプロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="afeba-444">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="afeba-445">デバイスごとのセキュリティで保護された構成評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="afeba-445">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="afeba-446">デバイスごとのソフトウェア インベントリ評価のエクスポート</span><span class="sxs-lookup"><span data-stu-id="afeba-446">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="afeba-447">その他の関連</span><span class="sxs-lookup"><span data-stu-id="afeba-447">Other related</span></span>

- [<span data-ttu-id="afeba-448">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="afeba-448">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="afeba-449">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="afeba-449">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
